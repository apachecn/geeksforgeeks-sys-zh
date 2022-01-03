# 【UniData、UniVerse 和 Vertica 的区别

> 原文:[https://www . geeksforgeeks . org/unidata universe 和-vertica 之间的差异/](https://www.geeksforgeeks.org/difference-between-unidatauniverse-and-vertica/)

**1。UniData，UniVerse :**
它是一个多值数据库和应用服务器，具有 SQL 映射层和元数据库功能。UniData 简化了数据库设计，消除了 SQL 规范化的限制。UniVerse 是多值应用平台的一个组件，它的优势是快速、灵活的数据服务器，用于开发企业应用。基于 UniVerse 的应用程序最大化可用资源的处理吞吐量，动态分配可用资源。

**Vertica :**
这是一个柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础架构的平台，通过它，它支持在多个云平台(AWS、谷歌云、Azure)、内部和 Hadoop 节点上的本地部署。其分析平台社区版是免费提供的，但有一定的限制。

**UniData、UniVerse 和 Vertica 的区别:**

<center>

| 没有 | 统一，宇宙 | 垂直的 |
| one | 由火箭软件公司开发，最初于 1985 年发布。 | 由 Vertica / Micro Focus 开发，最初于 2005 年发布，当前发布日期- Vertica 10.0 软件，2020 年 5 月，Vertica for SQL on Hadoop 10.0 软件，2020 年 5 月。 |
| Two | UniData、UniVerse 的服务器操作系统是 AIX、惠普-UX、Linux、Solaris、Windows。 | Linux 是服务器操作系统。 |
| three | 主要的数据库模型是多值数据库管理系统。 | 主要的数据库模型是关系数据库管理系统。 |
| four | 缺少辅助数据库模型。 | Vertica 的二级数据库模型是文档存储。 |
| five | UniData，UniVerse 支持。Net，Basic，C，Java，编程语言。 | 支持 C++、Java、Perl、Python、R、编程语言。 |
| six | API 等访问方式的 UniData、UniVerse 是专有协议、RESTful HTTP API、Java API、JDBC、ODBC、OLE DB、基于 SOAP 的 API。 | Vertica 支持 ADO.NET、JDBC、卡夫卡、ODBC、专有协议、RESTful HTTP、API。 |
| seven | 是的，统一数据，宇宙有一个无模式的数据模式。 | 是的，Vertica 有一个数据模式。 |
| eight | 它有实现语言 C。 | 它没有任何实现语言。 |
| nine | UniData，UniVerse 中的 ACID(原子性、一致性、隔离性、持久性)事务概念。 | VoltDB 的事务概念是 ACID(原子性、一致性、隔离性和持久性)。 |
| Ten | UniData、UniVerse 的复制方法是主从复制。 | Vertica 的复制方法是主从复制。 |
| Eleven | UniData，UniVerse 没有一致性概念。 | 是的，Vertica 有即时一致性的概念。 |
| Twelve | UniData，UniVerse 中缺少分区方法。 | 存在分片分区方法。 |
| Thirteen | 它没有外键。 | 它持有外键。 |

</center>