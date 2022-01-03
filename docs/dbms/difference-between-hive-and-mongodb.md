# 蜂巢和蒙古数据库的区别

> 原文:[https://www . geesforgeks . org/hive-and-MongoDB/](https://www.geeksforgeeks.org/difference-between-hive-and-mongodb/)之间的差异

**1。 [Hive](https://www.geeksforgeeks.org/apache-hive/) :**
Hive 是一款用于查询和管理大型分布式数据集的数据仓库软件，构建于 [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 之上。它由 Apache 软件基金会于 2012 年开发。它包含两个模块，一个是 MapReduce，另一个是 Hadoop 分布式文件系统(HDFS)。它将模式存储在数据库中，并将处理后的数据输入 HDFS。它位于 Hadoop 之上，用于总结大数据，并使查询和分析变得容易。

**2。 [MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) :**
MongoDB 是一个面向跨平台文档的非关系( [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) )数据库程序。它是一个开源文档数据库，以键值对的形式存储数据。MongoDB 由 MongoDB Inc .开发，最初于 2009 年 2 月 11 日发布。它是用 C++、Go、JavaScript、Python 语言编写的。MongoDB 提供了高速度、高可用性和高扩展性。

**蜂巢与 MongoDB 的区别:**

<center>

| 没有 | 储备 | MONGODB |
| 1. | 它是由 Apache 软件基金会在 2012 年开发的。 | 它是由 MongoDB Inc .在 2009 年开发的。 |
| 2. | 它是一个开源软件。 | 它也是一个开源软件。 |
| 3. | Hive 的服务器操作系统都是带有 Java 虚拟机的操作系统。 | MongoDB 的服务器操作系统有 Solaris、Linux、OS X、Windows。 |
| 4. | Hive 支持的复制方法是可选复制因子。 | MongoDB 支持的复制方法是主从复制。 |
| 5. | 它支持 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [PHP](https://www.geeksforgeeks.org/php/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 编程语言。 | 支持 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、Java、 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 、PHP、Lau、Python、 [R](https://www.geeksforgeeks.org/introduction-to-r-programming-language/) 、 [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/) 等多种编程语言。 |
| 6. | 它支持分片分区方法。 | 它还支持分片分区方法。 |
| 7. | 主要的数据库模型是[关系型数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/)。 | 主要的数据库模型是文档存储。 |
| 8. | [使用 JDBC、ODBC](https://www.geeksforgeeks.org/difference-odbc-jdbc/) 、节俭作为 API 等访问方式。 | 使用 JSON 的专有协议被用作 API 和其他访问方法。 |
| 9. | 它不支持内存功能。 | 它支持内存功能。 |
| 10. | 没有交易概念。 | [使用交易的 ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 |

</center>