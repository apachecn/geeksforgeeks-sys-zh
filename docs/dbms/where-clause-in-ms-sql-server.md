# 微软服务器中的 Where 子句

> 原文:[https://www . geesforgeks . org/where-子句-in-ms-sql-server/](https://www.geeksforgeeks.org/where-clause-in-ms-sql-server/)

在本文中，where 子句将与示例一起讨论。

**简介:**

1.  为了不时地提取数据，我们需要满足特定的条件。
2.  “where”是用于在查询中写入条件的子句。

**语法:**

```
select select_list
from table_name
where condition
```

下面给出了一个例子，以便更好地说明–

**示例:**

**样表:学生**

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

如果用户想要提取攻读机械专业的学生的姓名，查询如下:

```
select name
from student
where course='Mechanical' 
```

输出是–

<center>

| 名字 | 课程 |
| --- | --- |
| 迈纳 | 技工 |

</center>

“where”条件仅筛选评估为 true 的行。如果条件评估为 false 或未知，则不会筛选行，从而导致错误。