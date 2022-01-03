# SQLite 和卡珊德拉的区别

> 原文:[https://www . geesforgeks . org/SQLite 和-cassandra 之间的区别/](https://www.geeksforgeeks.org/difference-between-sqlite-and-cassandra/)

**1。 [SQLite](https://www.geeksforgeeks.org/introduction-to-sqlite/) :**
SQLite 是一个提供关系数据库管理系统( [RDBMS](https://www.geeksforgeeks.org/rdbms-architecture/) )的软件库。它是由理查德·希普于 2000 年 8 月设计的。SQLite 的设计目标是允许程序在不安装数据库管理系统(DBMS)或不需要数据库管理员的情况下运行。

**2。[卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/) :**
卡珊德拉是一个免费开源的、分布式的、宽栏目的商店， [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库管理系统。它由 Apache 软件基金会开发，最初于 2008 年 7 月发布。Cassandra 旨在处理许多商用服务器上的大量数据，提供高可用性，没有单点故障。

**SQLite 和 Cassandra 的区别:**

<center>

| 没有。 | SQLITE | 凶事预言家 |
| --- | --- | --- |
| 1. | 它是由理查德·希普于 2000 年 8 月开发的。 | 它由 Apache 软件基金会开发，于 2008 年 7 月发布。 |
| 2. | SQLite 只用 C 语言开发。 | 卡珊德拉也是只用 C 语言开发的。 |
| 3. | 它是广泛使用的过程中关系数据库管理系统。 | 它是基于 BigTable 和 DynamoDB 思想的宽栏商店。 |
| 4. | SQLite 的主要数据库模型是 RDBMS。 | 卡珊德拉的主要数据库模型是宽列存储。 |
| 5. | SQLite 不需要运行服务器。因此，它是无服务器的。 | 卡珊德拉的服务器操作系统是 BSD、Linux、OS X 和 Windows。 |
| 6. | 它支持二级索引。 | 它支持二级索引，但方式有限，即仅支持相等查询，并不总是性能最好的解决方案。 |
| 7. | SQLite 提供 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 事务。 | Cassandra 不提供 ACID 交易。 |
| 8. | 它不支持任何分区方法。 | 在 Cassandra 中，分区可以使用分片来完成。 |
| 9. | 它不支持任何复制方法。 | 它只支持一种复制方法–可选复制因子。 |
| 10. | SQLite 提供了引用完整性的概念，并且有外键。 | 卡珊德拉没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |

</center>