# 转基和弱化的区别

> 原文:[https://www . geeksforgeeks . org/trans base-and-wea viate 之间的差异/](https://www.geeksforgeeks.org/difference-between-transbase-and-weaviate/)

**1。Transbase :**
它是一个资源优化、高性能、普遍适用的 [RDBMS](https://www.geeksforgeeks.org/rdbms-architecture/) ，由慕尼黑交易软件有限公司开发和维护。它是一个关系数据库管理系统，支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 标准的所有重要功能。Transbase 的数据库可通过附加函数进行扩展，自定义数据类型也通过动态多线程技术提供查询的并行执行。

**2。weavete:**
这是一个开源的基于 GraphQL 的智能图，其核心特征是:语义搜索、自动分类和知识表示。主数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。它允许我们的数据以基于 GraphQL 查询语言的大型图形格式表示。这是一个基于图嵌入机制的搜索图，称为 Contextionary。

**Transbase 和 Weaviate 的区别:**

<center>

| 没有。 | Transbase | 变弱 |
| 1. | 它由交易软件有限公司开发，最初于 1987 年发布。 | 它由 SeMI Technologies B.V .开发，最初于 2017 年发布。 |
| 2. | 目前发布于 2019 年 9 月。 | 目前发布于 2020 年 1 月。 |
| 3. | FreeBSD、Linux、macOS、Solaris、Windows，都是 Transbase 的服务器、操作系统。 | Weaviate 没有这样的服务器操作系统。 |
| 4. | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是搜索引擎。 |
| 5. | Transbase 中缺少二级数据库模型。 | Weaviate 的二级数据库模型是图数据库管理系统。 |
| 6. | 支持 Transbase 中的 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 、 [Kotlin](https://www.geeksforgeeks.org/kotlin-programming-language/) 、Objective-C、 [PHP](https://www.geeksforgeeks.org/php/) 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 编程语言。 | 在 Weaviate 中没有这种受支持的编程语言。 |
| 7. | ADO.NET、 [JDBC](https://www.geeksforgeeks.org/introduction-to-jdbc/) 、ODBC、专有原生 API 是 Transbase 的 API 和其他访问方式。 | GraphQL 查询语言和 [RESTful](https://www.geeksforgeeks.org/rest-api-introduction/) HTTP/JSON API 是 Weaviate 的 API 和其他访问方式。 |
| 8. | Transbase 有数据模式。 | 弱化数据方案基于到 GraphQL 接口的映射。 |
| 9. | Transbase 的实现语言是 C 和 C++。 | Weaviate 的实现语言是 [Go](https://www.geeksforgeeks.org/golang/) 。 |
| 10. | Transbase 有事务概念。 | 《财富》杂志缺乏交易概念。 |
| 11. | Transbase 的复制方式是主从复制。 | 弱化的复制方法有主从复制和主从复制。 |
| 12. | Transbase 持有即时一致性概念。 | 威瓦特持有最终一致性概念。 |
| 13. | Transbase 支持外键的概念。 | Weaviate 不支持外键的概念。 |

</center>