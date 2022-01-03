# 【UniData、UniVerse 和 YugabyteDB 的区别

> 原文:[https://www . geeksforgeeks . org/difference-unidata universe-and-yugabyted b/](https://www.geeksforgeeks.org/difference-between-unidatauniverse-and-yugabytedb/)

**1。UniData，UniVerse :**
它是一个多值数据库和应用服务器，具有 SQL 映射层和元数据库功能。UniData 简化了数据库设计，消除了 SQL 规范化的限制。UniVerse 是多值应用平台的一个组件，它的优势是快速、灵活的数据服务器，用于开发企业应用。基于 UniVerse 的应用程序最大化可用资源的处理吞吐量，动态分配可用资源。

**2。**
它是开源、云原生和高性能的分布式 SQL 数据库全球分布式文档存储。它旨在使应用变得敏捷。尤加比特总部位于加利福尼亚州森尼维尔。YugabyteDB 是作为 Apache 2.0 开源项目分发和开发的。

**UniData、UniVerse 和 YugabyteDB 的区别:**

<center>

| 没有 | 统一，宇宙 | 南斯拉夫 b |
| one | 由火箭软件公司开发，最初于 1985 年发布。 | 由 Yugabyte Inc .开发，最初于 2017 年发布，目前于 2020 年 3 月发布。 |
| Two | UniData、UniVerse 的服务器操作系统是 AIX、惠普-UX、Linux、Solaris、Windows。 | YugabyteDB 的服务器操作系统是 Linux，OS X。 |
| three | 它的主要数据库模型是多值数据库管理系统。 | 它的主要数据库模型是关系数据库管理系统。 |
| four | UniData，UniVerse 中缺少辅助数据库模型 | YugabyteDB 的二级数据库模型是文档存储和宽列存储 |
| five | UniData，UniVerse 支持。Net，Basic，C，Java，编程语言。 | YugabyteDB 支持 C、C#、C++、Go、Java、JavaScript (Node.js)、Python、Ruby 等编程语言。 |
| six | API 等访问方式的 UniData、UniVerse 是 Java API、JDBC、ODBC、OLE DB、专有协议、RESTful HTTP API、基于 SOAP 的 API。 | YugabyteDB 支持 YCQL，这是一个基于 SQL 的灵活模式 API，其根源在于 Cassandra 查询语言。 |
| seven | 是的，统一数据，宇宙有一个无模式的数据模式。 | YugabyteDB 的数据方案取决于所使用的数据模型。 |
| eight | 它有实现语言 C。 | YugabyteDB 的实现语言是 C 和 C++。 |
| nine | UniData，UniVerse 中的 ACID(原子性、一致性、隔离性、持久性)事务概念。 | 它的事务概念是具有可序列化快照隔离的分布式 ACID。灵感来自谷歌扳手架构。 |
| Ten | UniData、UniVerse 主从复制的复制方法。 | YugabyteDB 的复制方法基于 Raft 分布式共识协议，最少 3 个副本以实现连续可用性。 |
| Eleven | UniData，UniVerse 没有一致性概念。 | YugabyteDB 在写入时具有很强的一致性，在读取时具有可调的一致性。 |

</center>