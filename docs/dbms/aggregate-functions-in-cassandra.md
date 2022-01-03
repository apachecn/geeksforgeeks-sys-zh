# 卡珊德拉中的聚合函数

> 原文:[https://www . geesforgeks . org/aggregate-functions-in-Cassandra/](https://www.geeksforgeeks.org/aggregate-functions-in-cassandra/)

在本文中，我们将讨论[卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)中的聚合函数，它可以用于各种目的，例如计数、求最小值和最大值、求和等。

**聚合函数:**

```
1. Count
2. Max and Min
3. Sum 
4. Avg 
```

在 Cassandra 中，这些聚合函数是预定义的或内置的函数。Cassandra 中的聚合函数处理一组行。聚合函数接收每行的值，然后为整个集合返回一个值。如果将普通列、标量函数、UDT 字段、写时间或生存时间与聚合函数一起选择，则为它们返回的值将是与查询匹配的第一行的值。

让我们用例子来讨论一下:

要创建键空间，请使用以下 CQL 查询。

```
CREATE KEYSPACE test1 with replication =
{‘class’ : ‘SimpleStrategy’, ‘replication_factor’ : 1} ; 
```

为了使用 test1 键空间，使用了下面的 CQL 查询。

```
USE test1; 
```

要创建该表，请使用以下 CQL 查询。

```
CREATE TABLE Emp_record
 (
  E_id int PRIMARY KEY,
  E_score int,
  E_name text,
  E_city text
 ); 
```

为了将这些值插入表 Emp_record，使用了以下 CQL 查询。

```
INSERT INTO Emp_record(E_id, E_score, E_name, E_city) 
       values (101, 85, ‘ashish’, ’Noida’);
INSERT INTO Emp_record(E_id, E_score, E_name, E_city) 
       values (102, 90, ‘ankur’, ’meerut’);
INSERT INTO Emp_record(E_id, E_score, E_name, E_city) 
       values (103, 99, ‘shivang’, ’gurugram’);
INSERT INTO Emp_record(E_id, E_score, E_name, E_city) 
       values (104, 85, ‘abi’, ’meerut’);
INSERT INTO Emp_record(E_id, E_score, E_city) 
       values (105, 95, ’mumbai’); 
```

要查看输出，请使用以下 CQL 查询。

```
Select * 
from Emp_record; 
```

<center>

| E_id | 护送 | 电子名称 | E_city |
| --- | --- | --- | --- |
| One hundred and one | eighty-five | Ashish | 无聊死了 |
| One hundred and two | Ninety | 安库尔·夏尔马 | 米鲁特 |
| One hundred and three | Ninety-five | 希万 | 我很自豪 |
| One hundred and four | eighty-five | 亚比谢克·拉纳 | 米鲁特 |
| One hundred and five | Ninety-five | 空 | 孟买 |

</center>

**1。count:**
count 函数用于统计查询返回的行数。

**示例:**

```
SELECT COUNT(*) 
FROM Emp_record; 
```

或者，为了得到相同的结果，我们可以使用 COUNT(1)。

```
SELECT COUNT(1) 
FROM Emp_record; 
```

**输出:**

```
5 
```

它也可以用来计算给定列的非空值。

**示例:**

```
SELECT COUNT(E_name) 
FROM Emp_record; 
```

**输出:**

```
4 
```

**2。最大值和最小值:**
最大值函数用于计算给定列的查询返回的最大值。
Min 函数用于计算给定列的查询返回的最小值。

*   **Example-1:**

    ```
    SELECT MIN(E_score) 
    FROM Emp_record; 
    ```

    **输出:**

    ```
    85 
    ```

*   **Example-2:**

    ```
    SELECT MAX(E_score) 
    FROM Emp_record; 
    ```

    **输出:**

    ```
    95 
    ```

**3。sum:**
sum 函数是一个聚合函数，可用于对给定列的查询返回的所有值进行求和。

**示例:**

```
SELECT SUM(E_score) 
FROM Emp_record; 
```

**输出:**

```
450 
```

**4。avg:**
avg 函数是一个聚合函数，可用于计算给定列的查询返回的所有值的平均值。

**示例:**

```
SELECT AVG(E_score) 
FROM Emp_record; 
```

**输出:**

```
90 
```