# 删除 MS SQL Server 中的语句

> 原文:[https://www . geesforgeks . org/delete-statement-in-ms-SQL-server/](https://www.geeksforgeeks.org/delete-statement-in-ms-sql-server/)

数据库包含许多按顺序存储数据的表。要删除这些行，用户需要使用 delete 语句。

**1。删除单个记录:**

**语法–**

```
DELETE FROM table_name 
WHERE condition; 
```

**注意–**
从表中删除记录时要小心。请注意，DELETE 语句中的 WHERE 子句。此位置指定需要删除哪些记录。如果排除 WHERE 子句，表中的所有记录都将被删除。

**示例–**
一个名为 Student 的表中插入了多个值，我们需要删除一些值。

<center>**Table –** Student

| 学生姓名 | 罗龙 | 城市 |
| --- | --- | --- |
| 字母表 | one | 斋浦尔 |
| 极好的 | Two | 德里 |
| JKL | three | 无聊死了 |
| XYZ | four | 德里 |

</center>

以下 SQL 语句从“学生”表中删除了一行，该行的学生名为“ABC”。

```
DELETE FROM student 
WHERE StudentName = 'ABC';
```

**输出–**

```
(1 row(s) affected)
```

为了检查该值是否被实际删除，查询如下:

```
select * 
from student;
```

**输出–**

<center>

| 学生姓名 | 罗龙 | 城市 |
| --- | --- | --- |
| 极好的 | Two | 德里 |
| JKL | three | 无聊死了 |
| XYZ | four | 德里 |

**2。删除所有记录:**
可以在不删除表的情况下删除表中的所有行。这意味着表结构、属性和索引将保持不变。

**语法–**

```
DELETE FROM table_name;
```

**示例–**
以下 SQL 语句删除“学生”表中的所有行，但不删除该表。

```
DELETE FROM student;
```

**输出–**

```
(3 row(s) affected)
```

为了检查该值是否被实际删除，查询如下:

```
select * 
from student;
```

<center>

| 学生姓名 | 罗龙 | 城市 |
| --- | --- | --- |

</center>

</center>