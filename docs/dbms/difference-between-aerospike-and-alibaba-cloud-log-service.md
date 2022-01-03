# 【Aerospike 与阿里巴巴云日志服务的区别

> 原文:[https://www . geesforgeks . org/aerospike-and-Alibaba-cloud-log-service/](https://www.geeksforgeeks.org/difference-between-aerospike-and-alibaba-cloud-log-service/)

**1。Aerospike:**
Aerospike 是一个闪存优化的内存开源 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，以生产它的同名公司的名字命名。这是一个关键价值数据存储，旨在为实时大数据应用程序提供亚毫秒级的响应时间。Aerospike 的三个主要组件是 Aerospike 数据库服务器、Aerospike 智能客户端和 Aerospike 管理控制台。

**2。阿里巴巴云日志服务:**
日志服务是一项完整的实时数据日志服务。它是由阿里巴巴集团开发的。它支持日志的收集、消费、运输、搜索和分析。

**Aerospike 与阿里巴巴云日志服务的区别:**

<center>

| 没有 | aerospoke | 阿里巴巴云日志服务 |
| --- | --- | --- |
| 1. | 它是由 Aerospike 在 2012 年开发的。 | 它是由 AlibabaCloud Inc .于 2016 年开发的。 |
| 2. | 这是一个闪存优化的内存 NoSQL 数据库。 | 它是一个完整的实时数据记录服务，支持日志的收集、消费、运输、搜索和分析。 |
| 3. | Aerospike 的许可证是开源的。 | 阿里巴巴云日志服务的许可证是商业的。 |
| 4. | Aerospike 的服务器操作系统是 Linux。 | 阿里巴巴云日志服务中有托管服务器操作系统。 |
| 5. | 它不能作为云服务使用。 | 它可以作为云服务使用。 |
| 6. | 它具有用户定义的服务器端脚本功能。 | 它不支持服务器端脚本。 |
| 7. | 支持的分区方法是分片。 | 支持的分区方法是分片。 |
| 8. | 它不支持 SQL 查询语言。 | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 |
| 9. | 它只支持一种复制方法:可选复制因子。 | 它支持 3 个副本。 |
| 10. | Aerospike 没有提供参照完整性的概念。因此，没有外键。 | 日志服务也不提供引用完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它为用户定义的映射/缩减方法提供了一个应用编程接口。 | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 |
| 13. | 它只支持操作的原子执行。 | 它支持 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 |
| 14. | 它的主要数据库模型是键值存储。 | 它的主要数据库模型是搜索引擎。 |

</center>