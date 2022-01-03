# 【Vertica 和 VoltDB 之间的差异

> 原文:[https://www . geeksforgeeks . org/vertica-和-voltdb/](https://www.geeksforgeeks.org/difference-between-vertica-and-voltdb/) 之间的差异

**1。Vertica :**
Vertica 是一个柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础架构的平台，通过它，它支持在多个云平台(AWS、谷歌云、Azure)、内部和 Hadoop 节点上的本地部署。其分析平台社区版是免费提供的，但有一定的限制。

**2。VoltDB :**
VoltDB 是分布式内存中的 NewSQL RDBMS，是一个符合 ACID 标准的 RDBMS，采用无共享架构。这个数据库是由迈克尔·斯通布雷克、萨姆·马登和丹尼尔·阿巴迪设计的。最初，VoltDB 数据库包括集群吞吐量和延迟以及 CPU 和内存使用情况的图表。VoltDB 基于 H-Store，随着多核服务器上每 CPU 内核数量的增加而扩展。

**Vertica 和 VoltDB 的区别:**

<center>

| 没有 | 垂直的 | VoltDB |
| one | 由 Vertica / Micro Focus 开发，最初于 2005 年发布。当前发布日期- Vertica 10.0 软件，2020 年 5 月，Vertica for SQL on Hadoop 10.0 软件，2020 年 5 月。 | 由 VoltDB Inc .开发，最初于 2010 年发布，目前于 2019 年 4 月发布。 |
| Two | Vertica 的服务器操作系统是 Linux | 它有 Linux，OS X 服务器操作系统。 |
| three | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是关系数据库管理系统。 |
| four | Vertica 的二级数据库模型是文档存储 | 缺少辅助数据库模型是 VoltDB。 |
| five | Vertica 支持 C++、Java、Perl、Python、R、编程语言。 | 它支持 C#、C++、Erlang、Go、Java、JavaScript、PHP、Python 等编程语言。 |
| six | Vertica 的 API 和其他访问方法是 ADO.NET、JDBC、卡夫卡、ODBC、专有协议、RESTful HTTP、API。 | VoltDB 支持 Java API、JDBC、RESTful HTTP/JSON API。 |
| seven | 是的，它有服务器端脚本 | VoltDB 的服务器端脚本是 Java。 |
| eight | 它没有任何实现语言。 | VoltDB 的实现语言是 Java，C++。 |
| nine | Vertica-事务概念是 ACID(原子性、一致性、隔离性和持久性)。 | VoltDB 的事务概念是 ACID(原子性、一致性、隔离性和持久性)。 |
| Ten | Vertica 的复制方法是主从复制 | VoltDB 的复制方式有主从复制和主从复制。 |
| Eleven | Vertica 有即时一致性概念。 | 它没有一致性概念。 |

</center>