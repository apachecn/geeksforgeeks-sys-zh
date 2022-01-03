# VoltDB 和 Warp 10 之间的差异

> 原文:[https://www . geesforgeks . org/volt db-and-warp-10 之间的差异/](https://www.geeksforgeeks.org/difference-between-voltdb-and-warp-10/)

**1。VoltDB :**
VoltDB 是分布式内存中的 NewSQL [RDBMS](https://www.geeksforgeeks.org/rdbms-architecture/) 和 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 兼容的 RDBMS，采用无共享架构。这个数据库是由迈克尔·斯通布雷克、萨姆·马登和丹尼尔·阿巴迪设计的。最初，VoltDB 数据库包括集群吞吐量和延迟以及 CPU 和内存使用情况的图表。VoltDB 基于 H-Store，随着多核服务器上每 CPU 内核数量的增加而扩展。

**2。Warp 10 :**
Warp 10 是一个时间序列数据库管理系统，专门处理基于 LevelDB 或 HBase 的带时间戳的地理数据。Warp 10 的服务器操作系统是 Linux、OS X、Windows。它是最先进的时间序列平台。Warp 10 是一个开源的地理时间序列平台，旨在监控系统和[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)(物联网)，并处理来自传感器的数据。

**VoltDB 和 Warp 10 的区别:**

<center>

| 没有。 | VoltDB | 曲速 10 |
| 1. | 它由 VoltDB Inc .开发，最初于 2010 年发布。 | 它由 SenX 开发，最初于 2015 年发布。 |
| 2. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是时间序列数据库管理系统。 |
| 3. | VoltDB 的服务器操作系统是 Linux 和 OS X。 | Warp 10 的服务器操作系统是 Linux、OS X 和 Windows。 |
| 4. | VoltDB 的 API 和其他访问方式有 Java API、 [JDBC](https://www.geeksforgeeks.org/introduction-to-jdbc/) 、 [RESTful](https://www.geeksforgeeks.org/rest-api-introduction/) HTTP/JSON API。 | Warp 10 的 API 和其他访问方法有 HTTP API、Jupyter 和 WebSocket。 |
| 5. | VoltDB 支持 ACID 的事务概念(原子性、一致性、隔离性和持久性)。 | Warp 10 没有这样的交易概念。 |
| 6. | VoltDB 的复制方式有主从复制和主从复制。 | 曲速 10 的复制方法是选择性复制因子。 |
| 7. | VoltDB 中没有分区方法。 | Warp 10 不支持分片分区方法。 |
| 8. | VoltDB 支持 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、二郎、 [Go](https://www.geeksforgeeks.org/golang/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 、 [PHP](https://www.geeksforgeeks.org/php/) 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 编程语言。 | 缺少任何支持的编程语言。 |
| 9. | 它没有任何一致性概念。 | 它有立即一致性的概念。 |
| 10. | VoltDB 的实现语言是 Java 和 C++。 | Warp 10 的实现语言是 Java。 |

</center>