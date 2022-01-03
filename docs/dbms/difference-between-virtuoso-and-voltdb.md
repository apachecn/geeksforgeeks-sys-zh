# 【Virtuoso 和 VoltDB 的区别

> 原文:[https://www . geeksforgeeks . org/virtuoso 和-voltdb 之间的差异/](https://www.geeksforgeeks.org/difference-between-virtuoso-and-voltdb/)

**1。VoltDB :**
VoltDB 是分布式内存中的 **NewSQL [RDBMS](https://www.geeksforgeeks.org/rdbms-full-form/)** 和一个 **[ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 兼容的 RDBMS** ，它使用的是一个共享的 nothing 架构。这个[数据库](https://www.geeksforgeeks.org/what-is-database/)由迈克尔·斯通布雷克、萨姆·马登和丹尼尔·阿巴迪设计。最初，VoltDB 数据库包括集群吞吐量和延迟以及 CPU 和内存使用情况的图表。VoltDB 基于 H-Store，随着多核服务器上每 CPU 内核数量的增加而扩展。

**2。Virtuoso :**
Virtuoso 是一个**中间件**，支持对表示为关系表和/或属性图的数据进行管理。它是一个**多模型混合-关系数据库管理系统**，主要数据库模型为图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储、搜索引擎。它是为利用操作系统线程支持和多个 CPU 而设计的。对象关系数据库支持实体完整性和引用完整性。

**VoltDB 和 Virtuoso 的区别:**

<center>

| 没有。 | VoltDB | 维尔图奥索 |
| one | 由 VoltDB Inc .开发，最初于 2010 年发布，目前于 2019 年 4 月发布。 | 由 Virtuoso 开发，最初于 1998 年发布，目前于 2019 年 5 月发布。 |
| Two | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是图形数据库、原生 XML 数据库、关系数据库、RDF 存储、搜索引擎，其辅助数据库模型是文档存储.. |
| three | 它有 Linux，OS X 服务器操作系统。 | AIX、FreeBSD、惠普-UX、Linux、OS X、Solaris、Windows 的服务器操作系统。 |
| four | VoltDB 支持 Java API、JDBC、RESTful HTTP/JSON API。 | Virtuoso 支持 ADO.NET、GeoSPARQL、HTTP API、JDBC、Jena、RDF API、ODBC、OLE DB、RDF4J API、RESTful HTTP API、芝麻街 REST HTTP 协议、SOAP、webservices、WebDAV、XPath、XQuery、XSLT。 |
| five | VoltDB 的事务概念是 ACID(原子性、一致性、隔离性和持久性)。 | 它有事务概念——ACID(原子性、一致性、隔离性和持久性)。 |
| six | VoltDB 的复制方式有主从复制和主从复制。 | Virtuoso 的复制方法基于链式、星型和双向复制，主-主复制，主从复制。 |
| seven | 它不支持分片分区方法。 | 它不支持分片分区方法。 |
| eight | 它支持 C#、C++、Erlang、Go、Java、JavaScript、PHP、Python 等编程语言。 | 大师支持。Net、C、C#、C++、Java、JavaScript、Perl、PHP、Python、Ruby、Visual Basic 编程语言。 |
| nine | 它没有一致性概念。 | 是的，Virtuoso 有一致性的概念。 |
| Ten | VoltDB 的实现语言是 Java，C++。 | Virtuoso 的实现语言是 c。 |
| Eleven | 缺少外键。 | 它有外键。 |

</center>