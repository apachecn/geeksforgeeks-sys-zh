# MS SQL Server 中的自连接和交叉连接

> 原文:[https://www . geesforgeks . org/self-join-and-cross-join-in-ms-SQL-server/](https://www.geeksforgeeks.org/self-join-and-cross-join-in-ms-sql-server/)

先决条件–[MS SQL Server 简介](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/)

**1。**
自连接允许我们自己连接一个表。当用户想要比较同一表中的数据(行)时，这很有用。

**语法–**

```
select 
select_list
from T t1 [Inner|Left] Join on T t2 
on join_predicate.
```

这里 T 指的是我们用来比较的表，它被引用了两次。为了避免错误和混淆，t1 和 t2 与 T 一起用于比较同一表中的两行。内部连接或左连接用于自连接以避免错误。

**2。交叉连接:**
交叉连接允许我们连接两个表的每一行。它类似于连接所有行的笛卡尔乘积。

**语法–**

```
select 
select_list 
from T1 cross join T2
```

**示例–**
学生和课程表是从大学数据库中选取的。

<center>**Table –** Student

| 名字 | 年龄 | 罗龙 |
| 爱莎 | Nineteen | One hundred and eleven |
| 玛雅人 | Eighteen | One hundred and twelve |
| 奈纳 | Eighteen | One hundred and thirteen |

</center>

<center>**Table –** Course

| 名字 | 罗龙 | 课程 |
| 爱莎 | One hundred and eleven | 中学生毕业考试 |
| 玛雅人 | One hundred and twelve | 东方马脑脊髓炎 |
| 奈纳 | One hundred and thirteen | 欧洲经济委员会 |

</center>

**1。自连接:**
应用自连接，结果集如下表所示。

```
select n1.name, n2.name 
from Student n1 inner join Student n2 
on rollno n1 = rollno n2
```

<center>

| 空 | 空 |

</center>

**2。交叉连接:**
应用交叉连接，结果集为第四个表。

```
select *
from Student cross join Course
```

<center>

| 名字 | 年龄 | 罗龙 | 名字 | 罗龙 | 课程 |
| 爱莎 | Nineteen | One hundred and eleven | 爱莎 | One hundred and eleven | 中学生毕业考试 |
| 玛雅人 | Eighteen | One hundred and twelve | 玛雅人 | One hundred and twelve | 东方马脑脊髓炎 |
| 奈纳 | Eighteen | One hundred and thirteen | 奈纳 | One hundred and thirteen | 欧洲经济委员会 |

</center>

**附加文章–**

*   [MS SQL Server 中的完全连接和内部连接](https://www.geeksforgeeks.org/full-join-and-inner-join-in-ms-sql-server/)
*   [MS SQL Server 中的左连接和右连接](https://www.geeksforgeeks.org/left-join-and-right-join-in-ms-sql-server/)