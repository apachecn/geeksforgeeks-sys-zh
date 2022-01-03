# 【Transbase 和 YugabyteDB 的区别

> 原文:[https://www . geeksforgeeks . org/trans base-and-yugabytedb/](https://www.geeksforgeeks.org/difference-between-transbase-and-yugabytedb/)之间的差异

**1。Transbase :**
这是一个资源优化、高性能、普遍适用的关系数据库管理系统，由慕尼黑交易软件有限公司开发和维护。它是一个关系数据库管理系统，支持 SQL 标准的所有重要功能。Transbase 的数据库可通过附加函数进行扩展，自定义数据类型也通过动态多线程技术提供查询的并行执行。

**yugabbtedb:**
它是高性能、云原生和开源的分布式 SQL 数据库全球分布式文档存储。它旨在使应用变得敏捷。尤加比特总部位于加利福尼亚州森尼维尔。它是作为 Apache 2.0 开源项目分发和开发的。

【Transbase 和 YugabyteDB 的区别:T2】

<center>

| 没有 | Transbase | 南斯拉夫 b |
| one | 由交易软件有限公司开发，最初于 1987 年发布。 | 由 Yugabyte Inc .开发，最初于 2017 年发布。 |
| Two | 目前发布于 2019 年 9 月 | 目前发布于 2020 年 3 月。 |
| three | FreeBSD、Linux、macOS、Solaris、Windows，都是 Transbase 的服务器、操作系统。 | Linux、OS X 都是 YugabyteDB 的服务器操作系统。 |
| four | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是关系数据库管理系统。 |
| five | Transbase 中缺少辅助数据库模型。 | 辅助数据库模型是文档存储和宽列存储 |
| six | 支持 C，C#，C++，Java，JavaScript，Kotlin，Objective-C，PHP，Python 都是编程语言。 | C、C#、C++、Go、Java、JavaScript (Node.js)、Python、Ruby 都是支持编程的语言。 |
| seven | ADO.NET、JDBC、ODBC、专有原生 API 是 Transbase 的 API 和其他访问方法。 | YCQL，一个基于 SQL 的灵活模式应用编程接口，其根源在于卡珊德拉查询语言、应用编程接口和其他访问方法。 |
| eight | Transbase 有数据模式。 | 数据方案取决于所使用的数据模型。 |
| nine | 它有实现语言 C 和 C++。 | YugabyteDB 的实现语言是 C 和 C++。 |
| 10  | 是的，Transbase 有交易概念。 | 具有可序列化和快照隔离的分布式 ACID。受谷歌扳手架构启发的是交易概念。 |
| Eleven | Transbase 的复制方法是主从复制。 | 复制方法基于 Raft 分布式共识协议，最少 3 个副本以实现连续可用性。 |
| Twelve | Transbase 持有即时一致性概念。 | 具有很强的写入一致性和可调的读取一致性。 |

</center>