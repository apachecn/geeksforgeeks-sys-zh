# 【Transbase 和 XAP 的区别

> 原文:[https://www . geesforgeks . org/trans base-and-xap 之间的差异/](https://www.geeksforgeeks.org/difference-between-transbase-and-xap/)

**1。Transbase :**
它是一个资源优化、高性能、普遍适用的 [RDBMS](https://www.geeksforgeeks.org/rdbms-architecture/) ，由慕尼黑交易软件有限公司开发和维护。它是一个关系数据库管理系统，支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 标准的所有重要功能。Transbase 的数据库可通过附加函数进行扩展，自定义数据类型也通过动态多线程技术提供查询的并行执行。

**2。XAP :**
这是一个面向任务关键型应用程序的高性能内存数据网格，提供了一组基本的数据存储功能，如事务、索引和查询语言(类似于 SQL 的查询)。它是一种用于安装和分发应用软件的文件格式。

**Transbase 和 XAP 的区别:**

<center>

| 没有。 | Transbase | XAP |
| 1. | 它由交易软件有限公司开发，最初于 1987 年发布。 | 它由 Gigaspaces Technologies 开发，最初于 2000 年发布。 |
| 2. | 目前发布于 2019 年 9 月。 | 目前发布于 2019 年 6 月。 |
| 3. | FreeBSD、Linux、macOS、Solaris、Windows 是 Transbase 的服务器操作系统。 | Linux、macOS、Solaris、Windows 是 XAP 的服务器操作系统。 |
| 4. | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是文档存储和键值存储。 |
| 5. | Transbase 中缺少二级数据库模型。 | XAP 的二级数据库模型是面向对象的数据库管理系统。 |
| 6. | 支持 Transbase 中的 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 、 [Kotlin](https://www.geeksforgeeks.org/kotlin-programming-language/) 、Objective-C、 [PHP](https://www.geeksforgeeks.org/php/) 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 编程语言。 | 支持[。Net](https://www.geeksforgeeks.org/introduction-to-net-framework/) ，C++和 Java 编程语言。 |
| 7. | ADO.NET、 [JDBC](https://www.geeksforgeeks.org/introduction-to-jdbc/) 、ODBC、专有原生 API 是 Transbase 的 API 和其他访问方式。 | gigaspace LRMI、Hibernate、JCache、JDBC、JPA、ODBC、 [RESTful HTTP API](https://www.geeksforgeeks.org/rest-api-introduction/) 、Spring Data 是 XAP 的 API 等访问方式。 |
| 8. | Transbase 有数据模式。 | XAP 的数据方案是无模式的。 |
| 9. | Transbase 的实现语言是 C 和 C++。 | XAP 的实现语言是 Java、C++和. Net |
| 10. | Transbase 有事务概念。 | XAP 有 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) (原子性、一致性、隔离性和持久性)事务概念。 |
| 11. | Transbase 的复制方式是主从复制。 | XAP 的复制方法有主从复制和主从复制。 |
| 12. | Transbase 持有即时一致性概念。 | XAP 也持有立即一致性的概念。 |
| 13. | Transbase 支持外键的概念。 | XAP 不支持外键的概念。 |
| 14. | Transbase 中缺少分区方法。 | XAP 的划分方法是分片。 |

</center>