# 【Trafodion 和 UniData 的区别，UniVerse

> 原文:[https://www . geeksforgeeks . org/trafodion-and-unidata universe/](https://www.geeksforgeeks.org/difference-between-trafodion-and-unidatauniverse/)之间的差异

**1。**
这是一个事务性的数据库管理系统。这是一个基于 Hadoop 的网络级 SQL 解决方案，支持 Apache Hadoop 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 Apache Hadoop 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

**2。UniData，UniVerse :**
它是一个多值数据库和应用服务器，具有 SQL 映射层和元数据库功能。UniData 简化了数据库设计，消除了 SQL 规范化的限制。UniVerse 是多值应用平台的一个组件，它的优势是快速、灵活的数据服务器，用于开发企业应用。基于 UniVerse 的应用程序最大化可用资源的处理吞吐量，动态分配可用资源。

**Trafodion 和 UniData 的区别，UniVerse :**

<center>

| 没有 | 交易 | 统一，宇宙 |
| --- | --- | --- |
| one | 它由最初由惠普开发的 Apache 软件基金会开发。最初于 2014 年发布，目前于 2019 年 2 月发布.. | 它由火箭软件公司开发，最初于 1985 年发布。 |
| Two | Linux 是服务器，特拉福德的操作系统。 | AIX、惠普-UX、Linux、Solaris、Windows 都是 UniData、UniVerse 的服务器操作系统 |
| three | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是多值数据库管理系统。 |
| four | 支持 JDBC/ODBC/ADO 的所有语言。Net 是编程语言。 | 。Net、Basic、C、Java 都是支持编程的语言。 |
| five | 它持有外键。 | 它没有外键。 |
| six | 存在分片分区方法。 | UniData，UniVerse 中缺少分区方法。 |
| seven | ADO.NET、JDBC、ODBC 是 Trafodion 的 API 和其他访问方法。 | 专有协议、RESTful HTTP API、Java API、JDBC、ODBC、OLE DB、基于 SOAP 的 API 都是 API 等访问方式。 |
| eight | 它有数据模式。 | 它有一个无模式的数据模式。 |
| nine | 它有实现语言 Java 和 C++。 | 实现语言是 c。 |
| Ten | Trafodion 有 ACID(原子性、一致性、隔离性和持久性)事务概念。 | UniData，UniVerse 有 ACID(原子性、一致性、隔离性和持久性)事务概念。 |
| Eleven | Trafodion 有通过 HBase 复制的方法。 | UniData、UniVerse 的复制方法是主从复制。 |
| Twelve | 即时一致性概念出现在 Trafodion 中。 | UniData，UniVerse 中缺乏一致性概念。 |

</center>