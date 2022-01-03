# 加入微软 SQL 服务器

> 原文:[https://www.geeksforgeeks.org/joins-in-ms-sql-server/](https://www.geeksforgeeks.org/joins-in-ms-sql-server/)

数据库由表组成，在[关系数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/)的情况下，每个表称为一个关系。

让我们考虑一个名为“大学”的示例数据库，它有两个名为“学生”和“分数”的表。如果用户想要传输某一组行，则查询时将使用[insert in select](https://www.geeksforgeeks.org/insert-into-select-statement-in-ms-sql-server/)语句。但是，如果用户想要从这两个表中提取一整组行，或者如果用户只想从这两个表中提取一组选定的行，那么在查询中使用联接是完美的匹配。

联接是从两个表中提取数据以形成一组有意义的新数据的子句。联接最多只能用于两个表。从表中提取的数据形成了一个新的表或关系，它不同于用于数据提取的以前的表。Microsoft 版本的 SQL 支持不同类型的连接，如左连接、右连接、自连接、内部连接、完全外部连接和交叉连接。

**示例–**
两个表即 Student 和 Marks 属于同一个数据库 University。如果用户想要连接两个表中的所有行，查询必须以–

```
select * 
from student full join marks
```

<center>
**Table –** Student

| 名字 | 罗龙 | 课程 |
| 爱莎 | One hundred and eleven | 中学生毕业考试 |
| 迈纳 | One hundred and twelve | 东方马脑脊髓炎 |
| 希霸 | One hundred and thirteen | 技工 |

</center>

<center>
**Table –** Marks

| 名字 | 年龄 | 平均积点 |
| 爱莎 | Eighteen | Nine point five |
| 迈纳 | Nineteen | Eight point nine |
| 希霸 | Eighteen | Seven point seven |

</center>

我们可以看到，表已经被连接在一起，没有遗漏任何一列。为了只提取几行，我们可以根据方便使用其他连接。

<center>

| 名字 | 罗龙 | 课程 | 名字 | 年龄 | 平均积点 |
| 爱莎 | One hundred and eleven | 中学生毕业考试 | 爱莎 | Eighteen | Nine point five |
| 迈纳 | One hundred and twelve | 东方马脑脊髓炎 | 迈纳 | Nineteen | Eight point nine |
| 希霸 | One hundred and thirteen | 技工 | 希霸 | Eighteen | Seven point seven |

</center>