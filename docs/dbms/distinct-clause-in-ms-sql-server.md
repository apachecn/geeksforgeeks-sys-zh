# 微软服务器中的独特子句

> 原文:[https://www . geesforgeks . org/distinct-子句 in-ms-sql-server/](https://www.geeksforgeeks.org/distinct-clause-in-ms-sql-server/)

在本文中，我们将讨论微软 SQL Server 中的独特子句。

**简介:**

1.  一个表最多包含 1000 行。
2.  表中可能会出现重复的行(在 SQL 术语中称为重复行)。
3.  在 SQL Server 中，distinct 是一个用于从表中删除重复项的术语。

**基本语法:**

```
select distinct
select_list
from
table_name 
```

**示例:**

**样表–学生**

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

要删除重复项，查询必须按如下方式编写–

```
select distinct
roll number, name, course
from student 
```

输出如下–

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

由于没有重复项，因此返回相同数量的行。让我们看一个有重复的例子。

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |
| One hundred and eleven | 里亚 | 中学生毕业考试 |

</center>

查询应写成–

```
select distinct
roll number, name, course
from student 
```

输出是–

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

有一个名为 Riya 的副本，但通过使用 distinct，这些副本被删除。

考虑另一个空值的例子。

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | – | – |

</center>

请注意，在 Deepa 的情况下，名称和课程为空，因此查询编写为–

```
select distinct 
name, roll number, course 
from student 
```

输出如下–

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 空 |

</center>

In case of null values, distinct removes all the other null values and restores only one null value as shown in the output.