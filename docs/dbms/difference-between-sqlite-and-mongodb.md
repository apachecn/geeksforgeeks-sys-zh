# SQLite 和 MongoDB 的区别

> 原文:[https://www . geeksforgeeks . org/SQLite 和-mongodb 之间的差异/](https://www.geeksforgeeks.org/difference-between-sqlite-and-mongodb/)

**1。SQLite :**
SQLite 是一个提供[关系数据库管理系统(RDBMS)](https://www.geeksforgeeks.org/difference-between-rdbms-and-dbms/) 的软件库。它是由理查德·希普于 2000 年 8 月设计的。SQLite 的设计目标是允许程序在不安装数据库管理系统(DBMS)或不需要数据库管理员的情况下运行。

**2。MongoDB :**
MongoDB 是一个开源的面向文档的数据库，用于大容量数据存储。属于 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库的分类。NoSQL 工具意味着它不使用通常的行和列。MongoDB 使用 BSON(文档存储格式)，这是 JSON 文档的二进制风格。

**SQLite 和 MongoDB 的区别:**

<center>

| 没有 | SQLITE | MONGODB |
| --- | --- | --- |
| 1. | 由理查德·希普于 2000 年 8 月开发。 | 由 MongoDB 公司于 2009 年开发。 |
| 2. | 它是广泛使用的过程中关系数据库管理系统。 | 它是最受欢迎的文档存储之一，既可作为完全托管的云服务，也可部署在自我管理的基础架构上。 |
| 3. | SQLite 的主要数据库模型是关系数据库管理系统。 | MongoDB 的主要数据库模型是文档存储。 |
| 4. | 它没有辅助数据库模型。 | 它将文档存储为辅助数据库模型。 |
| 5. | SQLite 只用 C 语言开发。 | MongoDB 仅用 C++语言开发。 |
| 6. | SQLite 不需要运行服务器。因此，它是无服务器的。 | 蒙古数据库的服务器操作系统是 Linux、OS X、Solaris 和 Windows。 |
| 7. | 它不支持服务器端脚本。 | 它有服务器端脚本的 Javascript。 |
| 8. | 它只支持 SQL 查询语言。 | 它支持 JSON 查询语言和 SQL。 |
| 9. | 它不支持任何复制方法。 | 它只支持一种复制方法——主-主复制。 |
| 10. | 它不支持任何分区方法。 | 在 MongoDB 中，分区可以通过分片来完成。 |
| 11. | SQLite 不支持地图缩减方法。 | MongoDB 支持地图缩减方法。 |
| 12. | SQLite 提供了引用完整性的概念，并具有外键。 | MongoDB 没有提供引用完整性的概念。因此，没有外键。 |

</center>