# 在 SQL 中有 vs Where 子句

> 原文:[https://www . geesforgeks . org/having-vs-where-子句 in-sql/](https://www.geeksforgeeks.org/having-vs-where-clause-in-sql/)

SQL 中的 having 和 where 子句的区别在于，where 子句不能用于聚合，但是 having 子句可以。

其中子句作用于行的数据，而不是聚合数据。让我们考虑下表“标记”。

**学生课程成绩**

c1 40

c2 50

b c3 60

d c1 70

e c2 80

考虑一下这个查询

|  | `SELECT` `Student, `Score` `FROM` `Marks` `WHERE` `Score >=40`` |

这将逐行选择数据。

拥有子句的**处理聚合数据。**

例如，以下查询的输出

|  | `SELECT` `Student,` `SUM``(score) AS` ``total` `FROM` `Marks` `GROUP BY` `Student`` |

**学生总数**

90

b 60

d 70

e 80

当我们在上面的查询中应用时，我们得到

|  | `SELECT` `Student,` `SUM``(score) AS` ``total` `FROM` `Marks` `GROUP BY` `Student``

``HAVING` `total > 70``

 |

**学生总数**

90

e 80