# 数据库管理系统|第 8 集

> 原文:[https://www . geesforgeks . org/database-management-systems-set-8/](https://www.geeksforgeeks.org/database-management-systems-set-8/)

GATE 2005 CS 考试中提出了以下问题。

**1)下列关于范式的说法，哪一个是假的？**
(a) BCNF 比 3NF 更严格
(b)无损的、保持依赖的分解成 3NF 总是可能的
(c)无损的、保持依赖的分解成 BCNF 总是可能的
(d)任何有两个属性的关系都在 BCNF

回答(c)
在 BCNF 分解一个表并保持依赖关系并不总是可能的。例如，一组功能依赖{ AB–>C，C–>B }在 BCNF 无法分解。详见[本](http://en.wikipedia.org/wiki/Boyce%E2%80%93Codd_normal_form#Achievability_of_BCNF)。

**2)下表有两个属性 A 和 C，其中 A 是主键，C 是引用 A 的外键，具有 on-delete 级联。**

```
A   C
-----
2   4
3   4
4   3
5   2
7   2
9   5
6   4

```

**删除元组(2，4)时必须额外删除以保持参照完整性的所有元组的集合是:**
(a) (3，4)和(6，4)
(b) (5，2)和(7，2)
(c) (5，2)、(7，2)和(9，5)
(d) (3，4)、(4，3)和(6，4)

当(2，4)被删除时，回答(C)
。由于 C 是引用 A 的外键，在级联时删除，所以 C 中值为 2 的所有条目都必须删除。所以(5，2)和(7，2)被删除。因此，从 A 中删除了 5 和 7，这导致(9，5)被删除。

**3)关系书(<u>书名</u>，价格)包含不同书籍的书名和价格。假设没有两本价格相同的书，下面的 SQL 查询列出了什么？**

```
  select title
  from book as B
  where (select count(*)
     from book as T
     where T.price > B.price) < 5

```

(a)最贵的四本书的书名
(b)第五本最便宜的书的书名
(c)第五本最贵的书的书名
(d)最贵的五本书的书名

回答(d)
当子查询使用外部查询的值时，该子查询被称为[相关子查询](http://en.wikipedia.org/wiki/Correlated_subquery)。对于外部查询处理的每一行，相关子查询都要计算一次。
外部查询从图书表中选择所有书名。对于每个选定的图书，子查询返回那些比选定图书更贵的图书的计数。外部查询的 where 子句对于 5 本最贵的书是正确的。例如，最贵的书的计数(*)为 0，第二贵的书的计数(*)为 1。

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。