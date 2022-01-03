# 关系模型和文档模型的区别

> 原文:[https://www . geesforgeks . org/关系模型和文档模型的区别/](https://www.geeksforgeeks.org/difference-between-relational-model-and-document-model/)

**1。[关系模型](https://www.geeksforgeeks.org/relational-model-in-dbms/) :**
关系模型是管理数据库的模型。之所以这样叫，是因为数据是以关系的形式存储的，即以表格的形式。每一行都由相关数据组成。表中的这些行描述了一个真实世界的实体。为了使用 python 和关系数据模型，我们需要–[SQL](https://www.geeksforgeeks.org/sql-tutorial/)和 [Pandas](https://www.geeksforgeeks.org/pandas-tutorial/) 的先决知识。熊猫是[蟒蛇](https://www.geeksforgeeks.org/python-programming-language/)的图书馆。

**2。文档模型:**
在文档模型中，数据以文档的形式存储。文件由描述文件实际和数据的记录组成。嵌套文档可用于提供有关数据子类别的信息。文档也可以用来表示现实世界的对象。

**关系模型和文档模型的区别:**

| 关系模型 | 文档模型 |
| --- | --- |
| 它是基于行的。 | 它是基于文档的。 |
| 不适合分层数据存储。 | 一般用于分层数据存储。 |
| 它由预定义的模式组成。 | 它由一个动态模式组成。 |
| 该模型遵循 ACID 属性。(原子性、一致性、隔离性和持久性)。 | 该模型遵循 CAP 定理。(一致性、可用性和分区容差)。 |
| 它比较慢。 | 它比关系模型更快。 |
| 支持复杂连接。 | 不支持复杂连接。 |
| 它是基于列的。 | 它是基于现场的。 | 它们是可纵向扩展的 | 它们是可水平扩展的 | 不提供东部复制支持。 | 它们提供了简单的复制支持 |
| 现在，在数据库中存储数据越来越常用。 | 它相对较少被使用。 |