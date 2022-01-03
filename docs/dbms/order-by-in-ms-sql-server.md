# MS SQL Server 中的订单人

> 原文:[https://www.geeksforgeeks.org/order-by-in-ms-sql-server/](https://www.geeksforgeeks.org/order-by-in-ms-sql-server/)

在本文中，将讨论订购方以及与订购方相关的术语。

**简介–**

1.  有些情况下，表格是按时间顺序排列的。
2.  虽然用户使用 select 语句来检索行，但不能保证这些行是按顺序排列的。
3.  为了解决这个问题，使用了 order by 子句。

**基本语法:**

```
select 
select_list
from
table_name
order by 
```

**示例:**样本表-学生

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

如果用户希望按顺序排列姓名，则查询必须按如下方式编写:

```
select
roll number 
name 
course
from
student
order by name 
```

输出结果是:

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and eleven | 里亚 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |

</center>

请注意，默认情况下，使用 order by 子句按升序排列表格。

ASC | desc:

1.  用户可以分别使用 ASC 或 DESC 以升序或降序排列列。
2.  ASC 从最低到最高排列列
3.  DESC 从最高到最低排列这些列。
4.  如果表中有空列，它将被视为最低值。