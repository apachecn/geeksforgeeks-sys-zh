# 插入到 MS SQL Server 的选择语句中

> 原文:[https://www . geesforgeks . org/insert-in-select-statement-in-ms-SQL-server/](https://www.geeksforgeeks.org/insert-into-select-statement-in-ms-sql-server/)

先决条件–[在 MS SQL Server 中插入语句](https://www.geeksforgeeks.org/insert-statement-in-ms-sql-server/)、[在 MS SQL Server 中选择语句](https://www.geeksforgeeks.org/select-statement-in-ms-sql-server/)

考虑一个大学数据库。有两张表，即学生表和成绩表。
在这种情况下，少数学生的分数要从分数表转移到分数表，有很多种方法。

可以使用子查询(嵌套在另一个查询中的查询)，但这是一个复杂且耗时的过程。

**插入选择**语句使工作更加容易。此语句用于从其他表中插入。

**语法:**

```
insert [TOP(exp)[PERCENT]]
into target_table
column_list
query
```

**示例–**

<center>
**Table –** Student

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |

</center>

<center>
**Table –** Marks

| 辊号 | 名字 | 平均积点 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | Nine point five |
| One hundred and twelve | 它能提供 | Nine point four |
| One hundred and thirteen | 迈纳 | Eight point seven |
| One hundred and fourteen | 丽塔 | Eight point one |
| One hundred and fifteen | 印度的七弦琴 | Seven point seven |
| One hundred and sixteen | 迪帕 | Seven point one |

</center>

如果用户想将标记转移到学生表，查询如下–

```
insert into marks (roll number, name, gpa)
select roll number, name, course 
from student 
```

值被插入。为了验证，查询如下–

```
select *
from student 
```

**输出–**

<center>

| 辊号 | 名字 | 课程 | 平均分数 |
| --- | --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 | Nine point five |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 | Nine point four |
| One hundred and thirteen | 迈纳 | 技工 | Eight point seven |
| One hundred and fourteen | 丽塔 | 生物技术 | Eight point one |
| One hundred and fifteen | 印度的七弦琴 | 化学的 | Seven point seven |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 | Seven point one |

</center>

这是插入值的另一种方式。通过使用 TOP 关键字，我们可以从表中提取所需的值–

```
insert TOP (6) PERCENT
insert into marks(roll number, name, gpa)
select roll number, name, course 
from student 
order by roll number 
```

**输出–**

<center>

| 辊号 | 名字 | 课程 | 平均分数 |
| --- | --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 | Nine point five |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 | Nine point four |
| One hundred and thirteen | 迈纳 | 技工 | Eight point seven |
| One hundred and fourteen | 丽塔 | 生物技术 | Eight point one |
| One hundred and fifteen | 印度的七弦琴 | 化学的 | Seven point seven |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 | Seven point one |

</center>

查询中略有不同，但我们得到了相同的结果集。TOP 是可选的，当用户只想从表中提取特定数量的行时，可以使用它。