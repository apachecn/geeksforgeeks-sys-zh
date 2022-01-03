# MS SQL Server 中的完全连接和内部连接

> 原文:[https://www . geesforgeks . org/完全连接和内部连接-in-ms-sql-server/](https://www.geeksforgeeks.org/full-join-and-inner-join-in-ms-sql-server/)

**先决条件–**[MS SQL Server 简介](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/)
T5】1。完全连接:
完全连接选择左右表中的所有行以及匹配的行。如果没有匹配的行，它将显示为空。

**语法–**

```
select select_list 
from table1 full join table2 on join _predicate
                           (OR)
select * 
from table1 full join table2
```

**2。内部连接:**
内部连接从左右表中检索匹配的行。如果没有匹配的行，将显示空值。

**语法–**

```
select select_list 
from table1 inner join table2 on join_predicate
                        (OR)
select * 
from table1 inner join table2 
```

**注意–**
这些连接可以应用于多个表。

**示例–**
下面给出了大学数据库中的两个表，即学生表和分数表。

<center>**Table –** Student</center>

<center>

| 名字 | 罗龙 | 年龄 | 课程 |
| 阿依拉 | One hundred and eleven | Nineteen | 中学生毕业考试 |
| 白腹长尾猴 | One hundred and twelve | Eighteen | 东方马脑脊髓炎 |
| 印度的七弦琴 | One hundred and thirteen | Nineteen | 欧洲经济委员会 |
| 尼娜 | One hundred and fourteen | Eighteen | 技工 |

</center>

<center>**Table –** Mark</center>

<center>

| 名字 | 罗龙 | 课程 | 平均积点 |
| 阿依拉 | One hundred and eleven | 中学生毕业考试 | Nine point six |
| 白腹长尾猴 | One hundred and twelve | 东方马脑脊髓炎 | Nine point five |
| 印度的七弦琴 | One hundred and thirteen | 欧洲经济委员会 | Seven point seven |
| 尼娜 | One hundred and fourteen | 技工 | Seven point five |

</center>

**1。完全连接:**
完全连接应用于学生和分数表，下表是结果集。

```
select * 
from student full join marks 
```

<center>

| 名字 | 罗龙 | 年龄 | 课程 | 平均积点 |
| 阿依拉 | One hundred and eleven | Nineteen | 中学生毕业考试 | Nine point six |
| 白腹长尾猴 | One hundred and twelve | Eighteen | 东方马脑脊髓炎 | Nine point five |
| 印度的七弦琴 | One hundred and thirteen | Nineteen | 欧洲经济委员会 | Seven point seven |
| 尼娜 | One hundred and fourteen | Eighteen | 技工 | Seven point five |

</center>

**2。内部连接:**
内部连接应用于学生表和成绩表，下表是结果集。

```
select * 
from student inner join marks 
```

<center>

| 名字 | 罗龙 | 课程 |
| 阿依拉 | One hundred and eleven | 中学生毕业考试 |
| 白腹长尾猴 | One hundred and twelve | 东方马脑脊髓炎 |
| 印度的七弦琴 | One hundred and thirteen | 欧洲经济委员会 |
| 尼娜 | One hundred and fourteen | 技工 |

</center>