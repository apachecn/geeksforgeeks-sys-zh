# ToroDB 和 YugabyteDB 的区别

> 原文:[https://www . geeksforgeeks . org/difference-torodb-and-yugabyted b/](https://www.geeksforgeeks.org/difference-between-torodb-and-yugabytedb/)

**1。ToroDB :**
它是一个 [MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) 兼容的 JSON 文档存储，建立在 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 之上，是一项旨在填补面向文档和 SQL 数据库之间空白的技术。这是一个开源的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，运行在与 MongoDB 协议和应用编程接口兼容的关系数据库管理系统之上。ToroDB 是一个开源项目，它读取 NoSQL 文档，自动推断其结构，并将其转换为一组表和列，这些表和列将数据表示为关系形式。

**2。
这是一个高性能、云原生和开源的分布式 SQL 数据库全球分布式文档存储。YugabyteDB 的目标是让应用变得敏捷。尤加比特总部位于加利福尼亚州森尼维尔。它是作为 Apache 2.0 开源项目分发和开发的。**

**YugabyteDB 和 ToroDB 的区别:**

<center>

| 没有。 | toxodb | 南斯拉夫 b |
| --- | --- | --- |
| one | 由 8Kdata 开发，最初于 2016 年发布。 | 由 Yugabyte Inc .开发，最初于 2017 年发布。目前发布于 2020 年 3 月。 |
| Two | 所有带有 Java 7 虚拟机的操作系统都是服务器操作系统。 | Linux、OS X 都是 YugabyteDB 的服务器操作系统。 |
| three | 主要数据库模型是文档存储。 | 主要的数据库模型是关系数据库管理系统。 |
| four | 数据库中缺少辅助数据库模型。 | 辅助数据库模型是文档存储和宽列存储。 |
| five | 没有任何支持的编程语言。 | C、C#、C++、Go、Java、JavaScript (Node.js)、Python、Ruby 都是支持编程的语言。 |
| six | ToroDB 中缺少 API 和其他访问方法。 | YCQL，一个基于 SQL 的灵活模式应用编程接口，其根源在于卡珊德拉查询语言、应用编程接口和其他访问方法。 |
| seven | 它具有无模式的数据模式。 | 数据方案取决于所使用的数据模型。 |
| eight | 它的实现语言是 Java。 | YugabyteDB 的实现语言是 C 和 C++。 |
| nine | 数据库中缺少事务概念。 | 具有可序列化和快照隔离的分布式 ACID。受谷歌扳手架构启发的是交易概念。 |
| Ten | ToroDB 中的主从复制方法。 | 复制方法基于 Raft 分布式共识协议，最少 3 个副本以实现连续可用性。 |
| Eleven | 它有最终一致性和即时一致性的概念。 | 写操作的强一致性和读操作的可调一致性是 YugabyteDB 中的一致性概念。 |
| Twelve | 它没有外键的概念。 | 但是它有外键的概念。 |

</center>