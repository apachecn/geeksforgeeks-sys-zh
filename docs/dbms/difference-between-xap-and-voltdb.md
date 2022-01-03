# XAP 和 VoltDB 的区别

> 原文:[https://www . geesforgeks . org/difference-xap-and-volt db/](https://www.geeksforgeeks.org/difference-between-xap-and-voltdb/)

**1。VoltDB :**
VoltDB 是分布式内存中的 NewSQL RDBMS，是一个符合 ACID 标准的 RDBMS，采用无共享架构。这个数据库是由迈克尔·斯通布雷克、萨姆·马登和丹尼尔·阿巴迪设计的。最初，VoltDB 数据库包括集群吞吐量和延迟以及 CPU 和内存使用情况的图表。它基于 H-Store，并随着多核服务器上每 CPU 内核数量的增加而扩展。

**2。XAP :**
XAP 是任务关键型应用程序的高性能内存数据网格，提供了一组基本的数据存储功能，如事务、索引和查询语言(类似于 SQL 的查询)。它是一种用于安装和分发应用软件的文件格式。

**XAP 和伏尔泰的区别:**

<center>

| 没有。 | XAP | VoltDB |
| one | 它由 Gigaspaces Technologies 开发，最初于 2000 年发布，目前于 2019 年 6 月发布。 | 它由 VoltDB Inc .开发，最初于 2010 年发布，目前于 2019 年 4 月发布。 |
| Two | 它的主要数据库模型是文档存储和键值存储，它的辅助数据库模型是面向对象的数据库管理系统。 | 它的主要数据库模型是关系数据库管理系统。 |
| three | 其服务器操作系统为 XAP Linux、macOS、Solaris、Windows。 | 其服务器操作系统的 VoltDB 是 Linux，OS X。 |
| four | 它支持千兆空间 LRMI，Hibernate，JCache，JDBC，JPA，ODBC，RESTful HTTP API，Spring Data。 | 它支持 Java API，JDBC，RESTful HTTP/JSON API。 |
| five | XAP 有 ACID(原子性、一致性、隔离性和持久性)概念事务概念。 | 事务概念 VoltDB 是 ACID(原子性、一致性、隔离性和持久性)。 |
| six | XAP 复制方法-主-主复制和主从复制。 | VoltDB 的复制方式有主从复制和主从复制。 |
| seven | XAP 的分区方法是分片。 | 它不支持分片分区方法。 |
| eight | 它支持。Net、C++、Java 编程语言。 | 它支持 C#、C++、Erlang、Go、Java、JavaScript、PHP、Python 等编程语言。 |
| nine | 它有立即一致性的概念。 | 它没有一致性概念。 |
| Ten | XAP 的实现语言是 Java、C++、。网 | VoltDB 的实现语言是 Java，C++。 |

</center>