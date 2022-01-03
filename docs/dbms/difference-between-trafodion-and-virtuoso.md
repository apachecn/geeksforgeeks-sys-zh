# 【Trafodion 和 Virtuoso 的区别

> 原文:[https://www . geeksforgeeks . org/trafodion 和-virtuoso 之间的差异/](https://www.geeksforgeeks.org/difference-between-trafodion-and-virtuoso/)

**1。T2 是一个事务性的数据库管理系统。这是一个网络级的 Hadoop 上的 SQL 解决方案，支持 Apache [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 Apache Hadoop 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。**

**2。Virtuoso :**
Virtuoso 是一个中间件，支持对表示为关系表和/或属性图的数据进行管理。它是一个多模型混合- [关系数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/)，主要的数据库模型有图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储和搜索引擎。它旨在利用操作系统线程支持和多个 CPU 的优势。对象关系数据库支持实体完整性和引用完整性。

**Trafodion 和 Virtuoso 的区别:**

<center>

| 没有 | 交易 | 维尔图奥索 |
| --- | --- | --- |
| 1. | 它由 Apache 软件基金会开发，最初由惠普开发。 | 它是由 Virtuoso 开发的。 |
| 2. | 最初发布于 2014 年。 | 最初发布于 1998 年。 |
| 3. | Linux 是 Trafodion 的服务器操作系统。 | AIX、FreeBSD、惠普-UX、Linux、OS X、Solaris 和 Windows 是 Virtuoso 的服务器操作系统。 |
| 4. | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型有图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储和搜索引擎。 |
| 5. | Trafodion 中缺少二级数据库模型。 | Virtuoso 的二级数据库模型是文档存储。 |
| 6. | 所有支持 [JDBC/ODBC](https://www.geeksforgeeks.org/difference-odbc-jdbc/) /ADO 的编程语言。Net 是由 Trafodion 支持的。 | [。Net](https://www.geeksforgeeks.org/introduction-to-net-framework/) 、 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 、 [Perl](https://www.geeksforgeeks.org/perl-programming-language/) 、 [PHP](https://www.geeksforgeeks.org/php/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 、 [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/) 和 Visual Basic 是 Virtuoso 的支持编程语言。 |
| 7. | 事务有数据模式。 | 大师也有数据模式。 |
| 8. | Trafodion 的实现语言是 Java 和 C++。 | Virtuoso 的实现语言是 c。 |
| 9. | Trafodion 有 ACID 事务概念。 | 大师也有 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 交易概念。 |
| 10. | Trafodion 的复制方法是通过 HBase。 | Virtuoso 的复制方法基于链式、星型和双向复制、主-主复制和主从复制。 |
| 11. | Trafodion 持有即时一致性概念。 | 大师也持有一致性的概念。 |

</center>