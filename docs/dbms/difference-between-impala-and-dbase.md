# 黑斑羚和 dBASE 的区别

> 原文:[https://www . geesforgeks . org/impala 和-dbase 的区别/](https://www.geeksforgeeks.org/difference-between-impala-and-dbase/)

**1。Impala :**
Impala 是一个运行在 [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 上的查询引擎。它对存储在 Hadoop 中的数据提供高性能、低延迟的 SQL 查询。它是一个开源软件。它支持内存中的数据处理。它率先使用了 Parquet 文件格式，这是一种柱状存储布局，针对数据仓库场景中典型的大规模查询进行了优化。

**2。dBASE :**
dBASE 是最成功的微型计算机数据库管理系统之一。这是第一个商业上成功的个人电脑数据库系统。它用于创建和操作关系数据库([关系数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/))。DBASE 使用类似于 BASIC 语言的过程函数和命令。它使用简单的命令进行数据操作，如使用、GO TOP 等。

**黑斑羚和 dBASE 的区别:**

<figure class="table">

| 没有 | 黑斑羚 | 数据库 |
| --- | --- | --- |
| 1. | 它是由 Cloudera 开发的。 | 它是由阿什顿·泰特开发的。 |
| 2. | 它于 2013 年推出。 | 它于 1979 年推出。 |
| 3. | 运行操作系统是 Linux。 | 运行在操作系统上的有 DOS(数据库经典版)和 Windows(数据库专业版)。 |
| 4. | 它是一个开源软件。 | 它是一个商业软件。 |
| 5. | [JDBC 和 ODBC](https://www.geeksforgeeks.org/difference-odbc-jdbc/) 是 Impala 使用的 API 和访问方式。 | 数据库中没有使用任何应用编程接口和访问方法。 |
| 6. | Impala 支持所有支持 JDBC/ODBC 的编程语言。 | dBASE 专有 IDE 受 dBASE 支持。 |
| 7. | Impala 使用分片分区方法在不同的节点上存储不同的数据。 | dBASE 不使用任何分区方法。 |
| 8. | Impala 中没有引用完整性的概念，也没有外键。 | 数据库中使用引用完整性。 |
| 9. | 它使用可选复制因子在多个节点上冗余存储数据。 | 它不使用任何复制方法。 |
| 10. | Impala 中没有交易概念。 | 数据库内部数据没有事务概念，但是集成开发环境在访问外部数据库管理系统时确实支持事务。 |

</figure>