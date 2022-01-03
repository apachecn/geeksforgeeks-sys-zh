# 卡珊德拉中按键的作用

> 原文:[https://www.geeksforgeeks.org/role-of-keys-in-cassandra/](https://www.geeksforgeeks.org/role-of-keys-in-cassandra/)

在本文中，我们将讨论为什么键很重要，它们是如何工作的，以及它们与关系数据库的不同之处。基本上，键用于将数据分组和组织成数据库中的列和行，所以让我们来看看。

[Cassandra](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)

```
1. Simple Primary key
2. Composite key
3. Using a compound primary key 
```

让我们逐一讨论分区键的概念。

**1。简单主键:**
在基本主键中，一列使用列名作为分区键。在这种情况下，主键仅由分区键组成。从表中检索数据时，只能指定主键。

```
CREATE KEYSPACE Employee
WITH REPLICATION = { 'class' : 'SimpleStrategy', 
                     'replication_factor' : 1 };
```

```
USE Employee;
```

```
CREATE TABLE Employee_info ( 
Employee_id UUID PRIMARY KEY, 
Emp_name text, 
Emp_domain text 
);

```

**2。组合键:**
在 Cassandra 组合键分区中，我们可以借助组合键对更多已排序的行进行使用。我们举个例子来了解一下。下面给定的雇员名是主键的一部分，主键被称为雇员信息表的复合分区键。

```
CREATE TABLE Employee_info
(
Employee_id int,
Employee_name text,
Employee_domain text,
Employee_add text
PRIMARY KEY ((Emplyee_id, Employee_name), Employee_domain) 
); 
```

在上面给定的表中，雇员标识和雇员名称用于复合分区键。这里主键中的 Employee_domain 额外列返回排序结果。让我们来看一个集群列更有帮助的场景。

```
INSERT INTO Employee_info(Employee_id, Employee_name, 
                           Employee_domain, Employee_add) 
        VALUES (1, ‘Ashish’, ‘A’, ‘Delhi’);
INSERT INTO Employee_info(Employee_id, Employee_name, 
                          Employee_domain, Employee_add) 
       VALUES (1, ‘Ashish’, ‘B’, ‘Mumbai’);
INSERT INTO Employee_info(Employee_id, Employee_name, 
                          Employee_domain, Employee_add ) 
       VALUES (2, ‘Ashish’, ‘C’, ‘Hyd’); 
```

```
Select * 
from Employee_info; 
```

**输出:**

<center>

| 员工 id | 员工姓名 | 员工 _ 域 | 员工 _ 添加 |
| --- | --- | --- | --- |
| one | Ashish | A | 德里 |
| one | Ashish | B | 孟买 |
| Two | Ashish | C | 水合 |

</center>

**3。使用复合主键:**
使用复合主键创建多个列，可用于查询和返回排序结果。
我们举一个 Employee_info 表的例子，我们将对数据进行去规范化。若要创建具有复合主键的表，请使用两列或更多列作为主键。
让我们举一个例子，它使用一个带有聚类顺序的附加子句来按降序排列 Employee_points。

```
CREATE TABLE Employee.Employee_info ( 
Employee_name text, 
Employee_points int, 
Employee_id UUID,  
PRIMARY KEY (Employee_name, Employee_points)
); 
```

让我们举一个例子，它使用一个额外的带有聚类顺序的子句来按降序对 Employee_points 进行排序。

```
CREATE TABLE Employee.Employee_info ( 
Employee_name text, 
Employee_points int, 
Employee_id int,  
PRIMARY KEY (Employee_name, Employee_points)
) WITH CLUSTERING ORDER BY (Employee_points DESC); 
```

现在，让我们将数据插入到 Employee_info 表中，并对其使用以下 CQL 查询。

```
INSERT INTO Employee_info (Employee_name, Employee_points, 
                                               Employee_id) 
        VALUES (‘Ashish’, 90, 1);
INSERT INTO Employee_info (Employee_name, Employee_points, 
                                          Employee_id ) 
       VALUES (‘Rana’, 95, 2);
INSERT INTO Employee_info(Employee_name, Employee_points, 
                                         Employee_id) 
       VALUES (‘Ashish’, 85, 3); 
```

```
Select * 
from Employee_info; 
```

**输出:**

<center>

| 员工姓名 | 员工积分 | 员工 id |
| --- | --- | --- |
| 中国林蛙 | Ninety-five | Two |
| Ashish | Ninety | one |
| Ashish | eighty-five | three |

</center>