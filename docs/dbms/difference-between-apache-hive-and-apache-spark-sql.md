# 阿帕奇蜂巢和阿帕奇火花 SQL 的区别

> 原文:[https://www . geesforgeks . org/Apache-hive-和-apache-spark-sql/](https://www.geeksforgeeks.org/difference-between-apache-hive-and-apache-spark-sql/) 之间的区别

**1。[Apache Hive](https://www.geeksforgeeks.org/apache-hive/):**
Apache Hive 是一款[数据仓库](https://www.geeksforgeeks.org/data-warehousing/)设备，构建在 [Apache Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 的巅峰之上，能够实现便捷的记录汇总、即席查询以及对保存在多个数据库和文件结构中的海量数据集的评估，这些数据库和文件结构与 Hadoop 相结合，并与带有 MapR XD 和 MapR Database 的 MapR 数据平台相结合。Hive 提供了一种简单的方法来对大量非结构化事实进行结构化，然后对这些数据进行类似于 SQL 的批处理查询。

**2。[Apache Spark SQL](https://www.geeksforgeeks.org/components-of-apache-spark/):**
Spark SQL 为 Spark 带来了对 SQL 的本机辅助，并简化了查询保存在 RDDs (Spark 分配的数据集)和外部源中的记录的方法。Spark SQL 毫不费力地模糊了关系数据库和关系表之间的痕迹。统一这些有效的抽象使开发人员能够方便地将查询外部信息的 SQL 指令与复杂的分析混合在一起，所有这些都在一个应用程序中。

**阿帕奇蜂巢和阿帕奇火花的区别 SQL :**

<center>

| 没有。 | Apache 蜂巢 | 阿帕奇火花 SQL |
| --- | --- | --- |
| 1. | 这是一个基于 Apache Hadoop 构建的开源数据仓库系统。 | 它用在结构化数据处理系统中
用 SQL 处理信息。 |
| 2. | 它包含大型数据集，并存储在 Hadoop 文件中，用于
分析和查询。 | 它计算繁重的功能，然后使用正确的
优化技术来处理任务。 |
| 3. | 2012 年上映。 | 它最早出现在 2014 年。 |
| 4. | 对于它的实现，主要使用 JAVA。 | 可以用 R、Python、Scala 等多种语言实现。 |
| 5. | 其最新版本(2.3.2)于 2017 年发布。 | 其最新版本(2.3.0)于 2018 年发布。 |
| 6. | 主要使用 RDMS 作为其数据库模型。 | 它可以与任何非 SQL 数据库集成。 |
| 7. | 它可以支持所有提供的操作系统，JVM 环境将在那里。 | 它支持各种操作系统，如 Linux、Windows 等。 |
| 8. | 其处理的访问方法包括 JDBC、ODBC 和节俭。 | 它只能由 ODBC 和 JDBC 访问。 |

</center>