# 【CouchDB 和 Redis 的区别

> 原文:[https://www . geeksforgeeks . org/difference-couch db-and-redis/](https://www.geeksforgeeks.org/difference-between-couchdb-and-redis/)

**1。[couch db](https://www.geeksforgeeks.org/introduction-to-apache-couchdb/):**
Apache couch db 是一个开源的面向文档的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，使用多种格式和协议来存储、传输和处理其数据，它使用 JSON 来存储数据，使用 MapReduce 将 JavaScript 作为其查询语言，使用 HTTP 作为一个 API。它由 Apache 软件基金会开发，最初于 2005 年发布。是二郎写的。

**2。Redis :**
Redis 代表远程字典服务器，这是一个内存中的数据结构项目，实现了一个分布式的内存中键值数据库，具有可选的持久性。Redis 由 Redis 实验室开发，最初于 2009 年 5 月 10 日发布。它是用 ANSI 和 [C 语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/)编写的。Redis 提供了内存效率、快速操作速度、高可用性，并提供了一些功能，如可调性、复制、集群等。

**CouchDB 和 Redis 的区别:**

<center>

| 没有。 | COUCHDB | REDIS |
| 1. | 它由 Apache 软件基金会开发，最初于 2005 年发布。 | 它由 Redis 实验室开发，最初于 2009 年 5 月 10 日发布。 |
| 2. | 是二郎写的。 | 它是用 ANSI 和 C 语言编写的。 |
| 3. | CouchDB 的主要数据库模型是文档存储。 | Redis 的主要数据库模型是键值存储。 |
| 4. | 它仅支持通过视图的辅助索引。 | It supports secondary indexes with RediSearch module only. |
| 5. | 在 CouchDB 中，没有预定义的数据类型。 | 它支持预定义的数据类型。 |
| 6. | CouchDB 中的服务器端脚本是通过 JavaScript 编写的。 | Redis 中的服务器端脚本是通过 Lua 实现的。 |
| 7. | 它支持地图缩减方法。 | 它不支持地图缩小方法。 |
| 8. | 它没有内存功能。 | 它有内存能力。 |
| 9. | 它支持主从复制和主从复制。 | 它支持主从复制和多主应用。 |
| 10. | CouchDB 的服务器操作系统有安卓、BSD、Linux、OS X、Solaris 和 Windows | Redis 的服务器操作系统有 BDS、Linux、OS X 和 Windows。 |
| 11. | 著名的公司，如宾克教育出版公司、美林公司、ASOS.com 有限公司、奥勒公司等都使用 Redis。 | 像 Akamai Technologies，Hothead Games，Inc，GenCorp Technologies，Vivint Solar 等知名公司都使用 CouchDB。 |

</center>