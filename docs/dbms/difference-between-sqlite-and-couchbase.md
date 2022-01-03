# SQLite 和 Couchbase 的区别

> 原文:[https://www . geeksforgeeks . org/SQLite 和-couchbase 之间的差异/](https://www.geeksforgeeks.org/difference-between-sqlite-and-couchbase/)

**1。 [SQLite](https://www.geeksforgeeks.org/introduction-to-sqlite/) :**
SQLite 是一个提供关系数据库管理系统( [RDBMS](https://www.geeksforgeeks.org/rdbms-architecture/) )的软件库。它是由理查德·希普于 2000 年 8 月设计的。SQLite 的设计目标是允许程序在不安装数据库管理系统(DBMS)或不需要数据库管理员的情况下运行。

**2。couch base:**
couch base Server 是一个开源的分布式多模型 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 面向文档的数据库软件包，针对交互式应用程序进行了优化。它也被称为 Membase。它由 Couchbase，Inc .开发，最初于 2010 年 8 月发布。

**SQLite 和 Couchbase 的区别:**

<center>

| 没有 | 

SQLITE

 | 

美洲狮号

 |
| --- | --- | --- |
| 1. | 它是由理查德·希普于 2000 年 8 月开发的。 | 它由 Couchbase，Inc .开发，最初于 2011 年 8 月发布。 |
| 2. | SQLite 只用 C 语言开发。 | Couchbase 是用 C++、Erlang、C 和 Go 语言编写的。 |
| 3. | 它是一种广泛使用的进程内关系数据库管理系统。 | 它是一个基于 JSON 的文档存储，从带有 Memcached 兼容接口的 CouchDB 派生而来。 |
| 4. | SQLite 的主要数据库模型是 RDBMS。 | Couchbase 的主要数据库模型是文档存储。 |
| 5. | SQLite 不需要运行服务器。因此，它是无服务器的。 | Couchbase 的服务器操作系统是 Linux、OS X 和 Windows。 |
| 6. | 它不支持任何复制方法。 | 它支持两种复制方法:主-主复制和主-从复制。 |
| 7. | SQLite 不支持地图缩减方法。 | Couchbase 支持地图缩减方法。 |
| 8. | SQLite 提供了引用完整性的概念，并且有外键。 | Couchbase 不提供引用完整性的概念，也没有外键。 |
| 9. | 它不支持任何分区方法。 | 在 Couchbase 中，分区可以通过分片来完成。 |
| 10. | SQLite 提供 ACID 事务。 | Couchbase 还提供 ACID 交易。 |
| 11. | 它不支持服务器端脚本。 | 它在服务器端脚本的 JavaScript 中有函数和定时器。 |
| 12. | SQLite 不支持辅助索引。 | Couchbase 支持二级索引。 |
| 13. | SQLite 有 SQL 支持。 | Couchbase 支持声明式查询语言(N1QL)，将 ANSI SQL 扩展到 JSON。 |

</center>