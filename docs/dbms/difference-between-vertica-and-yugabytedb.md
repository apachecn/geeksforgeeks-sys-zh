# 【Vertica 和 YugabyteDB 的区别

> 原文:[https://www . geeksforgeeks . org/vertica 和-yugabytedb 之间的差异/](https://www.geeksforgeeks.org/difference-between-vertica-and-yugabytedb/)

**1。yugabbtedb:**
yugabbtedb 是开源、云原生和高性能的分布式 SQL 数据库全球分布式文档存储。YugabyteDB 的目标是让应用变得敏捷。尤加比特总部位于加利福尼亚州森尼维尔。YugabyteDB 是作为 Apache 2.0 开源项目分发和开发的。

**2。Vertica :**
Vertica 是一个柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础架构的平台，通过该平台，它支持在多个云平台( [AWS](https://www.geeksforgeeks.org/introduction-to-amazon-web-services/) 、 [Google Cloud](https://www.geeksforgeeks.org/google-cloud-services/) 、Azure)上的部署，内部部署以及在 Hadoop 节点上的本地部署。其分析平台社区版是免费提供的，但有一定的限制。

**Vertica 和 YugabyteDB 的区别:**

<center>

| 没有。 | 垂直的 | 南斯拉夫 b |
| one | 由 Vertica / Micro Focus 开发，最初于 2005 年发布。 | 由 Yugabyte Inc .开发，最初于 2017 年发布，目前于 2020 年 3 月发布。 |
| Two | 当前发布日期- Vertica 10.0 软件，2020 年 5 月，Vertica for SQL on Hadoop 10.0 软件，2020 年 5 月。 | 当前发布日期-2020 年 3 月。 |
| three | Vertica 的服务器操作系统是 Linux。 | YugabyteDB 的服务器操作系统是 Linux，OS X。 |
| four | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是关系数据库管理系统。 |
| five | Vertica 的二级数据库模型是文档存储。 | YugabyteDB 的二级数据库模型是文档存储和宽列存储。 |
| six | Vertica 支持 C++、Java、Perl、Python、R、编程语言。 | YugabyteDB 支持 C、C#、C++、Go、Java、JavaScript (Node.js)、Python、Ruby 等编程语言。 |
| seven | Vertica 的 API 和其他访问方法是 ADO.NET、JDBC、卡夫卡、ODBC、专有协议、RESTful HTTP、API。 | YugabyteDB 支持 YCQL，这是一个基于 SQL 的灵活模式 API，其根源在于 Cassandra 查询语言。 |
| eight | 它有数据模式。 | YugabyteDB 的数据方案取决于所使用的数据模型。 |
| nine | 它没有任何实现语言。 | YugabyteDB 的实现语言是 C 和 C++。 |
| Ten | 事务概念是 ACID(原子性、一致性、隔离性和持久性)。 | 它的事务概念是具有可序列化和快照隔离的分布式 ACID。灵感来自谷歌扳手架构。 |
| Eleven | Vertica 的复制方法是主从复制。 | YugabyteDB 的复制方法基于 Raft 分布式共识协议，最少 3 个副本以实现连续可用性。 |
| Twelve | 它有立即一致性的概念。 | 它在写入时具有很强的一致性，在读取时具有可调的一致性。 |

</center>