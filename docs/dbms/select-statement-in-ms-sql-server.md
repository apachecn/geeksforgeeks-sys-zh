# 在 MS SQL Server 中选择语句

> 原文:[https://www . geesforgeks . org/select-statement-in-ms-SQL-server/](https://www.geeksforgeeks.org/select-statement-in-ms-sql-server/)

在本文中，我们将讨论 SQL 中使用的最基本的语句。

**基本语句:选择**

1.  到处都有大量的数据。
2.  数据以表格的形式按顺序存储。
3.  每个表由代表唯一记录的行和代表字段的列组成。
4.  模式用于以逻辑顺序排列表。
5.  为了从表中提取特定的数据，使用了用结构化查询语言编写的查询。
6.  要查询数据，请使用 select 语句。

**语法:**

```
select 
select_list;
from
schema_name.table.name; 
```

为了从表中检索所有的列，使用了 select*。

```
Syntax -
select*
from
table_name; 
```

**需要记住的点:**

1.  在实时数据库中，不建议使用 select*因为它检索的数据超过了您的要求。
2.  这会导致应用程序运行缓慢。
3.  在这种情况下，用户向表中添加更多的列，select*语句检索所有的列，包括导致应用程序崩溃的新列。

**示例:**

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

如果用户想要检索攻读计算机科学的学生的姓名，查询如下:

```
select 
name 
from
course.student
where course='cse' 
```

请注意，课程是模式的名称，学生是表的名称。

输出将按如下方式检索:

<center>

| 名字 | 课程 |
| --- | --- |
| 里亚 | 中学生毕业考试 |

</center>

**注意–**
要检索查询，另一个语句**正在使用**，这将在后续文章中讨论。