# 【VelocityDB 和 Weaviate 之间的差异

> 原文:[https://www . geesforgeks . org/difference-velocity db-and-wea viate/](https://www.geeksforgeeks.org/difference-between-velocitydb-and-weaviate/)

**1。**velocity db:
是的。NET 对象数据库，可以嵌入/分布和扩展到图形数据模型(VelocityGraph)数据库是快速和低内存消耗。它是一个性能极高、易于使用、可扩展、可嵌入和可分发的对象数据库系统。

**2。**
它是基于开源 GraphQL 的智能图，具有核心特性:语义搜索、自动分类和知识表示。主数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。它允许我们的数据以基于 GraphQL 查询语言的大型图形格式表示。它的搜索图基于一种叫做 Contextionary 的图嵌入机制。

**velocity db 和 Weaviate 的区别:**

<center>

| VelocityDB | 变弱 |
| 它由 VelocityDB Inc .开发，最初于 2011 年发布。 | 它由 SeMI Technologies B.V .开发，最初于 2017 年发布。 |
| VelocityDB 的服务器操作系统是任何支持。网 | Weaviate 没有这样的服务器操作系统。 |
| 它的主要数据库模型是图形数据库和面向对象数据库 | 它的主要数据库模型是搜索引擎。 |
| VelocityDB 中缺少辅助数据库模型 | 它的二级数据库模型是图形数据库管理系统。 |
| 它支持。Net 编程语言。 | 在 Weaviate 中没有这种受支持的编程语言。 |
| VelocityDB 的 API 和其他访问方法是。网 | 它支持 GraphQL 查询语言和 RESTful HTTP/JSON API。 |
| 它有一个数据模式。 | Weaviate 的数据模式映射到 GraphQL 接口。 |
| 它有实现语言——c#。 | 《武器是走》的实现语言。 |
| 它的事务概念是 ACID(原子性、一致性、隔离性和持久性)。 | 《武器》中交易概念的缺失。 |
| 缺少复制方法 | 还有复制方法。 |
| 它有直接的一致性概念。 | 它有最终一致性的概念。 |

</center>