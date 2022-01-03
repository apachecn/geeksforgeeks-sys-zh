# 微软 SQL Server 中有子句

> 原文:[https://www . geesforgeks . org/having-子句 in-ms-sql-server/](https://www.geeksforgeeks.org/having-clause-in-ms-sql-server/)

在本文中，我们将讨论微软的 SQL Server 中的 have 子句。

在某些情况下，要从查询中提取的数据是使用特定条件完成的。为此，使用了 having 子句。Having 子句根据用户在查询中给出的条件提取行。Having 子句必须与 group by 子句配对才能提取数据。否则，会产生错误。

**语法–**

```
select 
select_list
from
table_name
group by
group_list
having 
conditions 

```

**示例–**

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |

</center>

假设用户想要从学生表中提取姓名以 R 开头的学生的学号，查询如下–

```
select roll number
from student 
having name like 'R%'

```

输出将显示一个错误。这是因为查询中没有包含 group by 子句。
为获得所需结果而修改的查询如下–

```
select roll number 
from student 
group by name
having name like 'r%'

```

输出如下–

<center>

| 辊号 | 名字 |
| --- | --- |
| One hundred and fourteen | 丽塔 |
| One hundred and eleven | 里亚 |

</center>

Where 子句通常用于通过包含条件来提取查询。Where '和' Having '子句，两者都用于使用特定条件提取数据。然而，“Having”子句通过基于组列表进行分组来提取数据，“Where”子句通过插入条件来直接提取数据。