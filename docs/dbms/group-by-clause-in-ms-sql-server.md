# MS SQL Server 中的分组依据子句

> 原文:[https://www . geesforgeks . org/group-by-子句-in-ms-sql-server/](https://www.geeksforgeeks.org/group-by-clause-in-ms-sql-server/)

本文将详细讨论分组条款。

数据库系统中有大量的数据。即使数据以适当的顺序以表格的形式排列，用户有时也希望将查询中的数据分组以便于访问。要以组的形式排列数据(列)，必须在查询中使用名为 group by 的子句。group by 子句根据查询中指定的列排列数据。基本语法是-

**语法:**

```
select select_list 
from table_name 
group by column_1 column_2 
```

下面给出了一个例子——学生表:

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

In case a user wants to group data according to the roll number, it can be done as shown below-

```
select name
from student 
group by roll number 
```

**输出–**

<center>

| 名字 | 辊号 |
| --- | --- |
| 里亚 | One hundred and eleven |
| 它能提供 | One hundred and twelve |
| 迈纳 | One hundred and thirteen |
| 丽塔 | One hundred and fourteen |
| 印度的七弦琴 | One hundred and fifteen |
| 迪帕 | One hundred and sixteen |

</center>

这样，可以使用 group by 子句对表进行分组。在实时生产中，group by 子句用于通过应用聚合函数(最大值、最小值等)来生成计算。用户经常混淆分组依据和排序依据子句。Order by 子句用于按时间顺序排列数据。Group by 子句用于以组的形式排列数据。

为了更好地理解，下面给出了一个例子。

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |

**使用排序依据和分组依据的查询–**

```
select  roll number
from student 
order by name ASC 
```

**输出–**

<center>

| 辊号 | 名字 |
| --- | --- |
| One hundred and twelve | 它能提供 |
| One hundred and sixteen | 迪帕 |
| One hundred and thirteen | 迈纳 |
| One hundred and fourteen | 丽塔 |
| One hundred and eleven | 里亚 |
| One hundred and fifteen | 印度的七弦琴 |

</center>

```
select roll number
from student 
group by  name 
```

**输出–**

<center>

| 辊号 | 名字 |
| --- | --- |
| One hundred and eleven | 里亚 |
| One hundred and twelve | 它能提供 |
| One hundred and thirteen | 迈纳 |
| One hundred and fourteen | 丽塔 |
| One hundred and fifteen | 印度的七弦琴 |
| One hundred and sixteen | 迪帕 |

</center>

从例子中，我们可以清楚地注意到 group by 子句和 order by 子句之间的区别。如果是按顺序排列，则名称按字母顺序(A-Z)排列。如果用户必须从 Z-A 安排，可以按如下方式进行。

```
select 
roll number 
from 
student
order by
name DESC

```

输出将安排如下:

<center>

| 辊号 | 名字 |
| --- | --- |
| One hundred and fifteen | 印度的七弦琴 |
| One hundred and eleven | 里亚 |
| One hundred and fourteen | 丽塔 |
| One hundred and thirteen | 迈纳 |
| One hundred and sixteen | 迪帕 |
| One hundred and twelve | 它能提供 |

</center>

This way, the arrangement can be modified. In the case of group by, the data is arranged in form of groups but not in chronological order. Here, the where clause is not being used as it generates an error.</center>