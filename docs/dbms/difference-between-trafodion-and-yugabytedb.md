# 【Trafodion 和 YugabyteDB 的区别

> 原文:[https://www . geeksforgeeks . org/trafodion-and-yugabytedb/](https://www.geeksforgeeks.org/difference-between-trafodion-and-yugabytedb/)之间的差异

**1。**
这是一个事务性的数据库管理系统。这是一个基于 Hadoop 的网络级 SQL 解决方案，支持 Apache Hadoop 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 Apache Hadoop 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

**2。**
它是高性能、云原生和开源的分布式 SQL 数据库全球分布式文档存储。它旨在使应用变得敏捷。尤加比特总部位于加利福尼亚州森尼维尔。它是作为 Apache 2.0 开源项目分发和开发的。

**Trafodion 和 YugabyteDB 的区别:**

<center>

| 没有 | 交易 | 南斯拉夫 b |
| --- | --- | --- |
| one | 由 Apache 软件基金会开发，最初由惠普开发，最初于 2014 年发布。 | 由 Yugabyte Inc .开发，最初于 2017 年发布。 |
| --- | --- | --- |
| Two | Linux 是服务器，特拉福德的操作系统。 | Linux、OS X 都是 YugabyteDB 的服务器操作系统。 |
| --- | --- | --- |
| three | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是关系数据库管理系统。 |
| --- | --- | --- |
| four | 交通中缺少辅助数据库模型。 | 辅助数据库模型是文档存储和宽列存储。 |
| --- | --- | --- |
| five | 支持 JDBC/ODBC/ADO 的所有语言。Net 是编程语言。 | C、C#、C++、Go、Java、JavaScript (Node.js)、Python、Ruby 都是支持编程的语言。 |
| --- | --- | --- |
| six | ADO.NET、JDBC、ODBC 是 Trafodion 的 API 和其他访问方法。 | YCQL，一个基于 SQL 的灵活模式应用编程接口，其根源在于卡珊德拉查询语言、应用编程接口和其他访问方法。 |
| --- | --- | --- |
| seven | 它有数据模式。 | 其数据方案取决于所使用的数据模型。 |
| --- | --- | --- |
| eight | 它有实现语言 Java 和 C++。 | 它的 YugabyteDB 实现语言是 C 和 C++。 |
| --- | --- | --- |
| nine | 是的，Trafodion 有 ACID 交易概念。 | 具有可序列化快照隔离的分布式 ACID。受谷歌扳手架构启发的是交易概念。 |
| --- | --- | --- |
| Ten | 通过糖化血红蛋白是交通的复制方法。 | 复制方法基于 Raft 分布式共识协议，最少 3 个副本以实现连续可用性。 |
| --- | --- | --- |
| Eleven | 它有直接的一致性概念。 | 它在写入时具有很强的一致性，在读取时具有可调的一致性。 |
| --- | --- | --- |

</center>