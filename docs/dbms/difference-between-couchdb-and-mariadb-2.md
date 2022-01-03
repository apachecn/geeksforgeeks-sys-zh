# couch db 和 MariaDB 的区别

> 原文:[https://www . geesforgeks . org/difference-couch db-and-Maria db-2/](https://www.geeksforgeeks.org/difference-between-couchdb-and-mariadb-2/)

**1。CouchDB :**
Apache CouchDB 是一个开源的面向文档的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，使用多种格式和协议来存储、传输和处理其数据，它使用 JSON 来存储数据，使用 MapReduce 将 JavaScript 作为其查询语言，并使用 [HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) 作为一个 API。它由 Apache 软件基金会开发，最初于 2005 年发布。是二郎写的。

**2。MariaDB :**
MariaDB 是一个开源的关系数据库管理系统(RDBMS)，是广泛使用的 [MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 数据库技术的兼容插件替代。它由马里亚数据库基金会开发，最初于 2009 年 10 月 29 日发布。MariaDB 有大量新功能，这使得它在性能和面向用户方面更好。

**couch db 和 MariaDB 的区别:**

<center>

| 没有 | CouchDB | 马里亚 DB |
| --- | --- | --- |
| 1. | 由 Apache 软件基金会开发，最初于 2005 年发布。 | 由马里亚数据库基金会开发，最初于 2009 年 10 月 29 日发布。 |
| 2. | CouchDB 是用 Erlang 写的。 | MariaDB 是用 C、C++、Perl 和 Bash 语言编写的。 |
| 3. | CouchDB 的主要数据库模型是文档存储。 | 马里亚数据库的主要数据库模型是关系数据库管理系统。 |
| 4. | 在 CouchDB 中，没有预定义的数据类型。 | 马里亚数据库有预定义的数据类型，如浮点数、日期、数字等。 |
| 5. | CouchDB 不支持 XML 数据格式。 | MariaDB 支持 XML 数据格式。 |
| 6. | CouchDB 是无数据模式的。 | 在马里亚数据库中，数据模式支持动态列。 |
| 7. | CouchDB 支持地图缩减方法。 | 马里亚数据库不支持地图缩小方法。 |
| 8. | CouchDB 没有提供引用完整性的概念。因此，没有外键。 | MariaDB 提供了引用完整性的概念，并且有外键。 |
| 9. | CouchDB 提供了最终一致性方法来确保分布式系统中的一致性。 | 马里亚数据库提供了即时一致性方法，以确保分布式系统中的一致性。 |
| 10. | CouchDB 不支持 ACID 事务。 | MariaDB 提供 ACID 事务。 |
| 10. | CouchDB 的服务器操作系统有安卓、BSD、Linux、OS X、Solaris 和 Windows | MariaDB 的服务器操作系统有 FreeBSD、Linux、Solaris、Windows。 |
| 12. | 像 Akamai Technologies，Hothead Games，Inc，GenCorp Technologies，Vivint Solar 等知名公司都使用 CouchDB。 | 纽约市立大学、埃森哲、Docplanner、Grooveshark、诺斯罗普·格鲁曼等著名公司都使用 MariaDB。 |

</center>