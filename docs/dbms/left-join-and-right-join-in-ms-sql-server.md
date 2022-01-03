# MS SQL Server 中的左连接和右连接

> 原文:[https://www . geesforgeks . org/left-join-and-right-join-in-ms-SQL-server/](https://www.geeksforgeeks.org/left-join-and-right-join-in-ms-sql-server/)

**先决条件–**[微软 SQL Server 简介](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/)

**1。左连接:**
一个连接只组合了两个表的集合。当用户只想提取左表的数据时，使用左连接。左连接不仅组合了左表的行，还组合了与右表匹配的行。

**语法–**

```
select select_list 
from table1 left join table2 on join_predicate
                 (OR)
select * 
from table1 right join table2

```

**2。右连接:**
右连接结合了右表的数据和与两个表匹配的行。

**语法–**

```
select select_list 
from table1 right join table2 on join_predicate
                 (OR)
select * 
from table1 right join table2

```

**例–**
第一个表是课程表，被认为是左表，第二个表是学生表，被认为是右表。

<center>**Table –** Course</center>

<center>

| 名字 | 课程 | 年龄 |
| 爱莎 | 中学生毕业考试 | Nineteen |
| Vani | 欧洲经济委员会 | Eighteen |
| 迈纳 | 东方马脑脊髓炎 | Eighteen |

</center>

<center>**Table –** Student</center>

<center>

| 名字 | 罗龙 | 年龄 |
| 爱莎 | One hundred and eleven | Nineteen |
| Vani | One hundred and twelve | Eighteen |
| 迈纳 | One hundred and thirteen | Eighteen |

</center>

**1。左连接:**
左连接应用于“课程”和“学生”表，下表是结果集。

```
select name, course 
from c.course left join s.student on c.age = s.age 
```

<center>

| 名字 | 课程 | 名字 | 课程 |
| 爱莎 | 中学生毕业考试 | 爱莎 | 空 |
| Vani | 欧洲经济委员会 | Vani | 空 |
| 迈纳 | 东方马脑脊髓炎 | 迈纳 | 空 |

</center>

将显示左表和右表中相应的匹配行。如果用户希望只显示左表中的行，可以在查询中使用**其中**子句。左连接通常最多用于两个表，但是对于 SQL Server，它也可以用于多个表。

**2。右连接:**
右连接应用于“课程”和“学生”表，下表是结果集。

```
select name, rollno 
from c.course right join s.student on c.age = s.age 
```

<center>

| 名字 | 罗龙 | 名字 | 罗龙 |
| 爱莎 | One hundred and eleven | 爱莎 | 空 |
| Vani | One hundred and twelve | Vani | 空 |
| 迈纳 | One hundred and thirteen | 迈纳 | 空 |

</center>

如果这些表没有公共行，它会将这些行显示为空。正确的连接也可以用于多个表。