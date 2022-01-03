# 【MongoDB 和 CouchDB 的区别

> 原文:[https://www . geesforgeks . org/MongoDB 和-couchdb 之间的差异/](https://www.geeksforgeeks.org/difference-between-mongodb-and-couchdb/)

**1。MongoDB :**
MongoDB 是一个开源的面向文档的数据库，用于大容量数据存储。属于 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库的分类。NoSQL 工具意味着它不使用通常的行和列。MongoDB 使用 BSON(文档存储格式)，这是一种二进制样式的 JSON 文档。

**2。CouchDB :**
Apache CouchDB 是一个开源的面向文档的 NoSQL 数据库，它使用多种格式和协议来存储、传输和处理其数据，它使用 JSON 来存储数据，使用 MapReduce 将 JavaScript 作为其查询语言，并使用 [HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) 作为 API。它由 Apache 软件基金会开发，最初于 2005 年发布。是二郎写的。

**MongoDB 和 CouchDB 的区别:**

<center>

| 没有 | MONGODB | COUCHDB |
| --- | --- | --- |
| 1. | 由 MongoDB 公司于 2009 年开发。 | 由 Apache 软件基金会开发，最初于 2005 年发布。 |
| 2. | MongoDB 是用 C++编写的。 | CouchDB 是用 Erlang 写的。 |
| 3. | 它是最受欢迎的文档存储之一，既可作为完全托管的云服务，也可部署在自我管理的基础架构上。 | 它是受 Lotus Notes 启发的本地 JSON 文档存储，可从全球分布式服务器集群扩展到手机。 |
| 4. | MongoDB 的主要数据库模型是文档存储。 | CouchDB 的主要数据库模型是文档存储。 |
| 5. | 没有辅助数据库模型。 | 它将文档存储为辅助数据库模型。 |
| 6. | 蒙古数据库的服务器操作系统是 Linux、OS X、Solaris 和 Windows。 | CouchDB 的服务器操作系统有安卓、BSD、Linux、OS X、Solaris 和 Windows。 |
| 7. | 它支持预定义的数据类型，如字符串、整数、双精度、十进制、布尔或日期。 | 它不支持预定义的数据类型。 |
| 8. | 它通过商业智能的蒙古数据库连接器支持只读的 SQL 查询。 | 它不支持 SQL 查询语言。 |
| 9. | 它只支持一种复制方法——主-主复制。 | 它支持两种复制方法——主-主复制和主-从复制。 |
| 10. | 它支持内存功能。 | 它不支持内存功能。 |
| 11. | 它支持带有快照隔离的多文档 ACID 事务。 | 它不支持在对数据进行非原子操作后确保数据完整性。 |

</center>