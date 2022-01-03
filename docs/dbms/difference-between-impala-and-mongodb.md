# 黑斑羚和蒙戈 DB 的区别

> 原文:[https://www . geeksforgeeks . org/impala 和-mongodb 的区别/](https://www.geeksforgeeks.org/difference-between-impala-and-mongodb/)

**1。Impala :**
Impala 是一个运行在 [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 上的查询引擎。它是一个开源软件和大规模并行处理 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询引擎。它支持内存中的数据处理。它率先使用了 Parquet 文件格式，这是一种柱状存储布局，针对数据仓库场景中典型的大规模查询进行了优化。它提供高性能、低延迟的 SQL 查询，并对以 Hadoop 文件格式存储的数据提供交互式查询处理。

**2。 [Mongodb](https://www.geeksforgeeks.org/mongodb-an-introduction/) :**
MongoDB 是一个面向跨平台文档的非关系型(即 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) )数据库程序。它是一个开源文档数据库，以键值对的形式存储数据。MongoDB 由 MongoDB Inc .开发，最初于 2009 年 2 月 11 日发布。它是用 C++、Go、JavaScript、Python 语言编写的。MongoDB 提供了高速度、高可用性和高扩展性。

**黑斑羚和蒙戈 DB 的区别:**

<center>

| 没有。 | 黑斑羚 | MONGODB |
| 1. | 它是 Cloudera 在 2013 年开发的。 | 它是由 MongoDB Inc .在 2009 年开发的。 |
| 2. | 它是一个开源软件。 | 它也是一个开源软件。 |
| 3. | Impala 的服务器操作系统是 Linux。 | MongoDB 的服务器操作系统有 Solaris、Linux、OS X、Windows。 |
| 4. | 它不支持内存功能。 | 它支持内存功能。 |
| 5. | 没有交易概念。 | 使用事务的 ACID 属性。 |
| 6. | 英帕拉支持的复制方法是选择性复制因子。 | MongoDB 支持的复制方法是主从复制 |
| 7. | Impala 支持所有支持 JDBC/ODBC 的编程语言。 | 它支持 C、C#、Java、JavaScript、PHP、Lau、Python、R、Ruby 等多种编程语言。 |
| 8. | 它支持分片分区方法，用于在不同的节点上存储不同的数据。 | 它支持分片分区方法。 |
| 9. | JDBC 和 ODBC 被用作 API 和访问方法。 | 使用 JSON 的专有协议被用作 API 和其他访问方法。 |
| 10. | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是文档存储。 |

</center>