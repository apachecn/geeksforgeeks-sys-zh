# 【Vertica 和 Virtuoso 的区别

> 原文:[https://www . geeksforgeeks . org/vertica 和 virtuoso 的区别/](https://www.geeksforgeeks.org/difference-between-vertica-and-virtuoso/)

**1。Vertica :**
Vertica 是一个柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础架构的平台，通过它，它支持在多个云平台(AWS、谷歌云、Azure)、内部和 Hadoop 节点上的本地部署。其分析平台社区版是免费提供的，但有一定的限制。

**2。Virtuoso :**
Virtuoso 是一个中间件，支持对表示为关系表和/或属性图的数据进行管理。它是一个多模型混合关系数据库管理系统，主要的数据库模型有图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储、搜索引擎。它是为利用操作系统线程支持和多个 CPU 而设计的。对象关系数据库支持实体完整性和引用完整性。

**Vertica 和 Virtuoso 的区别:**

<center>

| 没有 | 垂直的 | 维尔图奥索 |
| one | 由 Vertica / Micro Focus 开发，最初于 2005 年发布。当前发布日期- Vertica 10.0 软件，2020 年 5 月，Vertica for SQL on Hadoop 10.0 软件，2020 年 5 月。 | 由 Virtuoso 开发，最初于 1998 年发布，目前于 2019 年 5 月发布。 |
| Two | Vertica 的服务器操作系统是 Linux | AIX、FreeBSD、惠普-UX、Linux、OS X、Solaris、Windows 的服务器操作系统。 |
| three | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是图形数据库、原生 XML 数据库、关系数据库、RDF 存储、搜索引擎。 |
| four | Vertica 的二级数据库模型是文档存储 | 它的二级数据库模型是文档存储。 |
| five | Vertica 支持 C++、Java、Perl、Python、R、编程语言。 | 大师支持。Net、C、C#、C++、Java、JavaScript、Perl、PHP、Python、Ruby、Visual Basic 编程语言。 |
| six | Vertica 的 API 和其他访问方法是 ADO.NET、JDBC、卡夫卡、ODBC、专有协议、RESTful HTTP、API。 | Virtuoso 支持 ADO.NET、GeoSPARQL、HTTP API、JDBC、Jena、RDF API、ODBC、OLE DB、RDF4J API、RESTful HTTP API、芝麻街 REST HTTP 协议、SOAP、webservices、WebDAV、XPath、XQuery、XSLT。 |
| seven | 是的，Vertica 有一个数据模式。 | 是的，大师有一个数据模式。 |
| eight | 它没有任何实现语言。 | Virtuoso 的实现语言是 c。 |
| nine | Vertica-事务概念是 ACID(原子性、一致性、隔离性和持久性)。 | 它有事务概念——ACID(原子性、一致性、隔离性和持久性)。 |
| Ten | Vertica 的复制方法是主从复制 | Virtuoso 的复制方法基于链式、星型和双向复制，主-主复制，主从复制。 |
| Eleven | Vertica 有即时一致性概念。 | 是的，Virtuoso 有一致性的概念。 |

</center>