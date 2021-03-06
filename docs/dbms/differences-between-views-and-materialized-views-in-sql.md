# SQL 中视图和物化视图的区别

> 原文:[https://www . geesforgeks . org/视图和物化视图之间的差异-in-sql/](https://www.geeksforgeeks.org/differences-between-views-and-materialized-views-in-sql/)

**视图:**
A [视图](https://www.geeksforgeeks.org/sql-views/)是充当实际关系的虚拟关系。它不是数据库系统的逻辑关系模型的一部分。视图的元组不存储在数据库系统中，并且每次访问视图时都会生成视图的元组。视图的查询表达式存储在数据库系统中。

我们可以使用实际关系的任何地方都可以使用视图。视图可用于根据特定用户的需求创建自定义虚拟关系。我们可以在数据库系统中创建任意多的视图。

**物化视图:**
当视图表达式的结果存储在数据库系统中时，它们被称为物化视图。SQL 没有提供任何定义物化视图的标准方法，但是一些数据库管理系统提供了使用物化视图的自定义扩展。保持物化视图更新的过程称为视图维护。

数据库系统使用三种方法之一来保持实体化视图的更新:

*   定义实体化视图的关系更新后，立即更新实体化视图。
*   每次访问实体化视图时更新该视图。
*   定期更新实体化视图。

当视图被频繁访问时，物化视图是有用的，因为它节省了计算时间，因为结果被预先存储在数据库中。在定义视图的关系非常大，而视图的最终关系非常小的情况下，实体化视图也很有帮助。实体化视图有相关的存储成本和更新开销。

**视图和物化视图的区别:**

<center>

| 视图 | 物化视图 |
| --- | --- |
| 查询表达式存储在数据库系统中，而不是查询表达式的结果元组中。 | 查询表达式的结果元组存储在数据库系统中。 |
| 不必在每次更新定义视图的关系时都更新视图，因为每次访问视图时都会计算视图的元组。 | 物化视图随着元组存储在数据库系统中而更新。根据上面提到的数据库系统，它可以通过三种方式之一进行更新。 |
| 它没有任何相关的存储成本。 | 它确实有相关的存储成本。 |
| 它没有任何相关的更新成本。 | 它确实有相关的更新成本。 |
| 有一个定义视图的 SQL 标准。 | 没有定义物化视图的 SQL 标准，该功能由一些数据库系统作为扩展提供。 |
| 当视图很少被访问时，视图很有用。 | 当视图被频繁访问时，物化视图是有效的，因为它通过提前存储结果来节省计算时间。 |

</center>