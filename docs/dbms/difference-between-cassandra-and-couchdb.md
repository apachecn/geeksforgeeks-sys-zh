# 卡珊德拉和 CouchDB 的区别

> 原文:[https://www . geesforgeks . org/difference-Cassandra-and-couch db/](https://www.geeksforgeeks.org/difference-between-cassandra-and-couchdb/)

**[1。卡珊德拉:](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/)**
卡珊德拉是一个免费开源、分布式、宽列存储、NoSQL 数据库管理系统。它由 Apache 软件基金会开发，最初于 2008 年 7 月发布。Cassandra 旨在处理许多商用服务器上的大量数据，提供高可用性，没有单点故障。

**2。CouchDB :**
Apache CouchDB 是一个开源的面向文档的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，使用多种格式和协议来存储、传输和处理其数据，它使用 JSON 来存储数据，使用 MapReduce 将 JavaScript 作为其查询语言，并使用 [HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) 作为一个 API。它由 Apache 软件基金会开发，最初于 2005 年发布。是二郎写的。

**卡珊德拉和 CouchDB 的区别:**

<center>

| 没有 | 卡桑德拉 | CouchDB |
| --- | --- | --- |
| 1. | 由 Apache 软件基金会开发，于 2008 年 7 月发布。 | 由 Apache 软件基金会开发，最初于 2005 年发布。 |
| 2. | Cassandra 是用 Java 语言写的。 | CouchDB 是用 Erlang 语言编写的。 |
| 3. | 卡珊德拉的主要数据库模型是宽列存储。 | CouchDB 的主要数据库模型是文档存储。 |
| 4. | Cassandra 支持预定义的数据类型，如浮点数、日期、数字等。 | 在 CouchDB 中，没有预定义的数据类型。 |
| 5. | 卡珊德拉的二级索引受到限制。 | CouchDB 不支持辅助索引。 |
| 6. | 卡珊德拉有 SQL 支持，即它支持一些 SQL 语句，如 DML、DDL、SELECT 等。 | CouchDB 不支持 SQL。 |
| 7. | 卡珊德拉支持选择性复制因子复制方法。 | CouchDB 支持主从复制和主-主复制复制方法。 |
| 8. | Cassandra 提供了最终一致性和即时一致性方法，以确保分布式系统中的一致性。 | CouchDB 提供了最终一致性方法来确保分布式系统中的一致性。 |
| 9. | 卡珊德拉的服务器操作系统是 BSD、Linux、OS X、Windows。 | CouchDB 的服务器操作系统有安卓、BSD、Linux、OS X、Solaris 和 Windows。 |
| 10. | 像 GitHub、Hulu、Instagram、Reddit、天气频道等知名公司都使用 Cassandra。 | 像 Akamai Technologies，Hothead Games，Inc，GenCorp Technologies，Vivint Solar 等知名公司都使用 CouchDB。 |

</center>