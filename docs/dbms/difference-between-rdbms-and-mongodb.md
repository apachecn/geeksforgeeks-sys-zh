# 【RDBMS 和 MongoDB 的区别

> 原文:[https://www . geeksforgeeks . org/区别-RDBMS-和-mongodb/](https://www.geeksforgeeks.org/difference-between-rdbms-and-mongodb/)

**什么是 MongoDB？**
[MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) 是一个开源的面向文档的数据库，用于大容量数据存储。它属于 NoSQL 数据库的分类。NoSQL 工具意味着它不使用通常的行和列。MongoDB 使用 BSON(文档存储格式)，这是一种二进制样式的 JSON 文档。

**MongoDB 的特点:**

*   多台服务器:可以在多台服务器上运行。
*   无模式数据库:它是一个无模式数据库。
*   索引:文档中的任何字段都可以被索引。
*   丰富对象模型:它支持丰富对象模型。

**What is RDBMS?**

**关系数据库管理系统的特点:**

*   提供高级别的信息安全性。
*   它快速而精确。
*   提供工具主键，以特别区分行。

【RDBMS 与 MongoDB 的区别:

<center>

| 关系型数据库管理系统 | MongoDB |
| --- | --- |
| 这是一个关系数据库。 | 它是非关系型和面向文档的数据库。 |
| 不适合分层数据存储。 | 适合分层数据存储。 |
| 它可以纵向扩展，即增加内存。 | 它是横向可扩展的，即我们可以添加更多的服务器。 |
| 它有一个预定义的模式。 | 它有一个动态模式。 |
| 它很容易受到 SQL 注入的影响。 | 它不受 SQL 注入的影响。 |
| 它围绕着 ACID 属性(原子性、一致性、隔离性和持久性)展开。 | 它围绕 CAP 定理(一致性、可用性和分区容差)展开。 |
| 它是基于行的。 | 它是基于文档的。 |
| 它比 MongoDB 慢。 | 它几乎比 RDBMS 快 100 倍。 |
| 支持复杂连接。 | 不支持复杂连接。 |
| 它是基于列的。 | 它是基于现场的。 |
| 它不提供用于查询的 JavaScript 客户端。 | 它提供了一个用于查询的 JavaScript 客户端。 |
| 它只支持 SQL 查询语言。 | 它支持 JSON 查询语言和 SQL。 |

</center>