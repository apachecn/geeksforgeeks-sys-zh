# 如何打印表格中的重复行？

> 原文:[https://www . geesforgeks . org/如何打印表格中的重复行/](https://www.geeksforgeeks.org/how-to-print-duplicate-rows-in-a-table/)

Let us consider below table.

| 名字 | 部分 |
| --- | --- |
| 字母表 | CS1 |
| bcd | CS2 |
| 字母表 | CS1 |

在上表中，我们可以使用下面的查询找到重复的行。

```
SELECT name, section FROM tbl
GROUP BY name, section
HAVING COUNT(*) > 1

```

**另一个例子:**
给定一个名为 PERSON 的表任务是编写一个 SQL 查询来查找表中所有重复的名字。
**例:**

```
+----+---------+
| Id | NAME    |
+----+---------+
| 1  | Geeks   |
| 2  | for     |
| 3  | Geeks   |
+----+---------+

Output :
+---------+
| NAME    |
+---------+
| Geeks   |
+---------+

```

**简单的方法**是制作一个临时表，其中包含一个表中所有名字的计数。

重复的名称存在不止一次，因此为了计算每个名称存在的次数，我们可以使用以下代码:

```
select NAME, count(NAME) as num
from Person
group by NAME;

```

```
| NAME    | num |
|---------|-----|
| Geeks   | 2   |
| for     | 1   |

```

这是一个临时表，我们可以在上面运行下面的代码来获取重复的名称。

```
select NAME from
(
  select NAME, count(NAME) as num
  from Person
  group by NAME
) as statistic
where num > 1;

```

**最佳方法**是使用**分组**和**拥有**条件。它比以前的更有效、更快。

**MySql :**

```
select NAME
from Person
group by NAME
having count(NAME) > 1;

```

本文由 **[萨赫勒拉吉普特](https://www.linkedin.com/in/sahil-rajput-3ba2b3134/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。