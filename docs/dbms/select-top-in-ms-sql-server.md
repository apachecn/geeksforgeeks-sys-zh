# 在 MS SQL Server 中选择顶部

> 原文:[https://www.geeksforgeeks.org/select-top-in-ms-sql-server/](https://www.geeksforgeeks.org/select-top-in-ms-sql-server/)

先决条件–[在 MS SQL Server 中选择](https://www.geeksforgeeks.org/select-statement-in-ms-sql-server/)
假设一个用户想要抽取整个机构的尖子生，但是必须使用一些复杂的查询来抽取数据。为了避免复杂性，用户可以使用“选择顶部”。
“选择顶部”提取有限的行数。这导致了准确的数据和更少的时间消耗。

**语法–**

```
select top (expression) [percent] [with ties]
from table_name 
order by column_name 
```

**分析语法–**

*   **Top** 是从列表顶部提取数据的关键字。
*   **表达式**是要从表中提取的数据。
*   **Percent** 是需要从表中提取的行数。
*   **With Ties** 返回与最后一行具有相同值的行。在某些情况下，可以检索更多的行。

order by 子句用于按时间顺序排列数据。必须在语法中使用此子句，否则会导致错误。

**示例–**
如果用户想要抽取一个机构的前 5 名学生，那么查询将被写成–

```
select top 5 name rollnumber gpa
from student 
order by name ASC

```

**输出–**

<center>

| 辊号 | 名字 | 平均积点 |
| --- | --- | --- |
| One hundred and fourteen | 爱莎 | Nine point five |
| One hundred and sixteen | 它能提供 | Nine point four |
| One hundred and nineteen | 迈纳 | Eight point seven |
| One hundred and fourteen | 丽塔 | Eight point one |
| One hundred and eighteen | 印度的七弦琴 | Seven point seven |

</center>

这样可以提取所需的数据。最后一行学生的 gpa 为 7.7，如果还有几个学生共享相同的数字，则查询必须写成–

```
select top 8 with ties
name rollnumber gpa
from student
order by name ASC

```

**输出–**

<center>

| 辊号 | 名字 | 平均积点 |
| --- | --- | --- |
| One hundred and fourteen | 爱莎 | Nine point five |
| One hundred and sixteen | 它能提供 | Nine point four |
| One hundred and nineteen | 迈纳 | Eight point seven |
| One hundred and fourteen | 丽塔 | Eight point one |
| One hundred and eighteen | 印度的七弦琴 | Seven point seven |
| One hundred and ten | 维尼莎 | Seven point seven |
| One hundred and one | Yamini | Seven point seven |
| One hundred and seven | 祖贝达 | Seven point seven |

</center>

ASC 从升序到降序排列数据。如果数据必须从降序排列到升序，可以使用 DESC。