# 偏移-在微软 SQL 服务器中获取

> 原文:[https://www . geesforgeks . org/offset-fetch-in-ms-SQL-server/](https://www.geeksforgeeks.org/offset-fetch-in-ms-sql-server/)

假设一个表有 30 行。用户想要提取最后 10 行的列表并跳过最上面的行。为了使工作更容易，在查询中使用了**偏移-提取子句**。

**语法:**

```
order by column_list[ASC|DESC]
Offset offset_row count{ROW|ROWS}
Fetch{FIRST|NEXT} fetch row_count {ROW|ROWS} only

```

**语法分析:**

*   [Order by](https://www.geeksforgeeks.org/order-by-in-ms-sql-server/) 子句必须与 offset-fetch 子句一起使用，否则会导致错误。ASC 从升序到降序排列行，而 DESC 从降序到升序排列行。
*   偏移量跳过表中指定的行数。
*   Fetch 返回使用 offset 子句后的行数。它返回指定的行数。
*   第一个返回偏移量为后的表开头的行数，而下一个返回第一组行后的连续行。

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

如果用户想跳过前两行并返回其余行，查询给出如下

```
select name, rollnumber, course
from student 
order by rollnumber ASC
offset 2 ROWS
```

**输出–**

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |

</center>

偏移跳过查询中指定的行数，而按 ASC 排序从升序到降序排列行。如果用户想要跳过前 6 行并获取下一行，查询给出如下

```
select name, rollnumber, course 
from student
order by roll number ASC
offset 6 ROWS
fetch FIRST 2 ROWS ONLY
```

**输出–**

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and seventeen | Vani | 技工 |
| One hundred and eighteen | 非常 | 欧洲经济委员会 |

</center>

**Offset 子句**跳过表中指定的所有行，而 **Fetch 子句**返回 Offset 子句后的前两行。在 fetch 子句中，可以根据用户的要求使用 FIRST 和 NEXT。Offset 子句是必须使用的，而 fetch 在查询中是可选的。