# SQLite 和 CouchDB 的区别

> 原文:[https://www . geeksforgeeks . org/SQLite 和-couchdb 之间的差异/](https://www.geeksforgeeks.org/difference-between-sqlite-and-couchdb/)

**1。SQLite :**
SQLite 是一个提供[关系数据库管理系统(RDBMS)](https://www.geeksforgeeks.org/difference-between-rdbms-and-dbms/) 的软件库。它是由理查德·希普于 2000 年 8 月设计的。SQLite 的设计目标是允许程序在不安装数据库管理系统(DBMS)或不需要数据库管理员的情况下运行。SQLite 中的 lite 意味着在设置、数据库管理和所需资源方面重量轻。

**2。CouchDB :**
Apache CouchDB 是一个开源的面向文档的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，使用多种格式和协议来存储、传输和处理它的数据，它使用 JSON 来存储数据， [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 作为它的查询语言使用 MapReduce，HTTP 作为一个 API。它由 Apache 软件基金会开发，最初于 2005 年发布。是二郎写的。

**SQLite 和 CouchDB 的区别:**

<center>

| 没有 | SQLITE | COUCHDB |
| --- | --- | --- |
| 1. | 由理查德·希普于 2000 年 8 月开发。 | 由 Apache 软件基金会开发，最初于 2005 年发布。 |
| 2. | SQLite 只用 C 语言开发。 | CouchDB 是用 Erlang 写的。 |
| 3. | 它是广泛使用的过程中关系数据库管理系统。 | 受 Lotus Notes 启发的本地 JSON 文档存储，可从全球分布的服务器集群扩展到手机。 |
| 4. | SQLite 的主要数据库模型是关系数据库管理系统。 | CouchDB 的主要数据库模型是文档存储。 |
| 5. | SQLite 不需要运行服务器。因此，它是无服务器的。 | CouchDB 的服务器操作系统有安卓、BSD、Linux、OS X、Solaris 和 Windows。 |
| 6. | 在 SQLite 中，数据模式是固定的。 | CouchDB 是无数据模式的。 |
| 7. | SQLite 有预定义的数据类型，如浮点数、日期、数字等。 | 在 CouchDB 中，没有预定义的数据类型。 |
| 8. | 它不支持 XML 格式。 | 它不支持 XML 格式。 |
| 9. | 它不支持任何复制方法。 | 它支持两种复制方式–

*   Master slave copy
*   Master slave copy

 |
| 10. | SQLite 提供 ACID 事务。 | CouchDB 不支持 ACID 事务。 |
| 11. | SQLite 不支持地图缩减方法。 | CouchDB 支持地图缩减方法。 |
| 12. | SQLite 提供了引用完整性的概念，并具有外键。 | CouchDB 没有提供引用完整性的概念。因此，没有外键。 |

</center>