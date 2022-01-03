# 猪和蜂巢的区别

> 原文:[https://www . geesforgeks . org/猪与蜂巢的区别/](https://www.geeksforgeeks.org/difference-between-pig-and-hive/)

**1。[猪](https://www.geeksforgeeks.org/introduction-to-apache-pig/) :**
猪用于大量数据的分析。它比 MapReduce 更抽象。在 Hadoop 中，Pig 用于执行各种数据操作。它提供了猪拉丁语言来编写包含许多内置函数的代码，如连接、过滤等。阿帕奇猪的两个部分是猪拉丁和猪引擎。Pig Engine 用于将所有这些脚本转换为特定的地图并减少任务。猪的抽象处于更高的层次。与 MapReduce 相比，它包含的代码行更少。

**2。 [Hive](https://www.geeksforgeeks.org/apache-hive/) :**
Hive 构建在 [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 之上，用于处理 Hadoop 中的结构化数据。蜂巢是由脸书开发的。它提供了各种类型的查询语言，通常称为 Hive 查询语言。Apache Hive 是一个数据仓库，它在用户和集成了 Hadoop 的 Hadoop 分布式文件系统(HDFS)之间提供了一个类似于 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 的接口。

**猪和蜂巢的区别:**

<center>

| 没有。 | 猪 | 储备 |
| 1. | Pig 在集群的客户端运行。 | Hive 在集群的服务器端运行。 |
| 2. | 猪使用猪拉丁语言。 | Hive 使用 HiveQL 语言。 |
| 3. | Pig 是一种过程数据流语言。 | Hive 是一种声明式的英语语言。 |
| 4. | 是雅虎开发的。 | 它是由脸书开发的。 |
| 5. | 它由研究人员和程序员使用。 | 它主要由数据分析师使用。 |
| 6. | 它用于处理结构化和半结构化数据。 | 它主要用于处理结构化数据。 |
| 7. | 它用于编程。 | 它用于创建报告。 |
| 8. | 猪脚本以。猪延伸。 | 在 HIve 中，支持所有扩展。 |
| 9. | 它不支持分区。 | 它支持分区。 |
| 10. | 它可以快速加载数据。 | 它加载数据很慢。 |
| 11. | 它不支持 JDBC。 | 支持 [JDBC](https://www.geeksforgeeks.org/introduction-to-jdbc/) 。 |
| 12. | 它不支持 ODBC。 | 支持 [ODBC](https://www.geeksforgeeks.org/difference-odbc-jdbc/) 。 |
| 13. | Pig 没有专用的元数据数据库。 | Hive 通过预先定义表来利用专用 SQL-DDL 语言的精确变体。 |
| 14. | 它支持 Avro 文件格式。 | 它不支持 Avro 文件格式。 |
| 15. | Pig 适用于复杂的嵌套数据结构。 | Hive 适用于批量处理 [OLAP](https://www.geeksforgeeks.org/olap-full-form/) 系统。 |
| 16. | Pig 不支持存储数据的模式。 | Hive 支持在表中插入数据的模式。 |

</center>