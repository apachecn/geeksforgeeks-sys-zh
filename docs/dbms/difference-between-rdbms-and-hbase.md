# 【RDBMS 和 HBase 的区别

> 原文:[https://www . geesforgeks . org/difference-RDBMS-and-hbase/](https://www.geeksforgeeks.org/difference-between-rdbms-and-hbase/)

**关系数据库管理系统(RDBMS)–**
RDBMS 是针对 SQL 的，适用于所有现代数据库系统，如 MS SQL Server、IBM DB2、Oracle、MySQL 和 Microsoft Access。关系数据库管理系统是一种基于关系模型的数据库管理系统。关系数据库管理系统是一种基于行的表结构的数据库管理系统，它连接相关的数据元素，并包括维护数据的安全性、准确性、完整性和一致性的功能。最基本的关系数据库管理系统功能是创建、读取、更新和删除操作。糖化血红蛋白遵循酸性。

**HBase–**
HBase 是一个面向列的数据库管理系统，运行在 Hadoop 分布式文件系统(HDFS)之上。它非常适合稀疏数据集，这在许多大数据用例中很常见。它是由 Apache 软件基金会开发的开源分布式数据库。最初，它被命名为谷歌大表，后来它被重新命名为 HBase，主要是用 Java 编写的。它可以存储从万亿字节到千兆字节的海量数据。它专为低延迟操作而构建，广泛用于读写操作。它以表格的形式存储大量数据。

【RDBMS 和 HBase 的区别:

| 关系型数据库管理系统 | 巴什 |
| --- | --- |
| 它需要 SQL(结构化查询语言) | 哇哦 |
| 它有固定的模式 | 没有固定模式 |
| 它是面向行的 | 它是面向列的 |
| 它是不可扩展的 | 它是可扩展的 |
| 它本质上是静态的 | 本质上是动态的 |
| 数据检索速度较慢 | 更快的数据检索 |
| 它遵循 ACID(原子性、一致性、隔离性和持久性)特性。 | 它遵循一致性、可用性、分区容差定理。 |
| 它可以处理结构化数据 | 它可以处理结构化、非结构化以及半结构化数据 |
| 它不能处理稀疏数据 | 它可以处理稀疏数据 |