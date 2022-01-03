# 【Trafodion 和 Vertica 的区别

> 原文:[https://www . geeksforgeeks . org/trafodion 和-vertica 之间的差异/](https://www.geeksforgeeks.org/difference-between-trafodion-and-vertica/)

**1。trafodian:**
trafodian 是一个事务型[SQL](https://www.geeksforgeeks.org/sql-tutorial/)-on-[Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/)DBMS。这是一个基于 Hadoop 的网络级 SQL 解决方案，支持 Apache Hadoop 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 Apache Hadoop 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

**2。Vertica :**
Vertica 是一个柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础架构的平台，通过它，它支持在多个云平台(AWS、谷歌云、Azure)、内部和 Hadoop 节点上的本地部署。其分析平台社区版是免费提供的，但有一定的限制。

**特拉福德和 Vertica 的区别:**

<center>

| 没有。 | 交易 | 垂直的 |
| 1. | Trafodion 由 Apache 软件基金会开发，最初由惠普开发。 | Vertica 由 Vertica /微焦点开发。 |
| 2. | Trafodion 最初于 2014 年发布。 | Vertica 最初于 2005 年发布。 |
| 3. | Linux 是 Trafodion 的服务器操作系统。 | Linux 是 Vertica 的服务器操作系统。 |
| 4. | 主要数据库模型是[关系型数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/)。 | 主要的数据库模型是关系数据库管理系统。 |
| 5. | 交通运输部缺乏二级数据库模型。 | Vertica 的二级数据库模型是文档存储。 |
| 6. | 所有支持 JDBC/ODBC/ADO 的编程语言。Net 是由 Trafodion 支持的。 | C++、Java、 [Perl](https://www.geeksforgeeks.org/perl-programming-language/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 和 R 是 Vertica 支持的编程语言。 |
| 7. | ADO.NET、 [JDBC、ODBC](https://www.geeksforgeeks.org/difference-odbc-jdbc/) 是 Trafodion 的 API 等访问方式。 | ADO.NET、JDBC、卡夫卡、ODBC、专有协议、 [RESTful HTTP](https://www.geeksforgeeks.org/rest-api-introduction/) 、API 是 Vertica 的 API 和其他访问方式。 |
| 8. | 事务有数据模式。 | Vertica 也有数据模式。 |
| 9. | Trafodion 的实现语言是 [Java](https://www.geeksforgeeks.org/java/) 和 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 。 | Vertica 没有任何实现语言。 |
| 10. | Trafodion 有 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 交易概念。 | Vertica 也有 ACID 交易概念。 |
| 11. | Trafodion 的复制方法是通过 HBase。 | Vertica 的复制方法是主-主复制。 |
| 12. | Trafodion 持有即时一致性概念。 | Vertica 还持有即时一致性概念。 |

</center>