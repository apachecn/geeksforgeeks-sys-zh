# 【Aerospike 和阿里巴巴云 TSDB 的区别

> 原文:[https://www . geesforgeks . org/aerospike-and-Alibaba-cloud-tsdb/](https://www.geeksforgeeks.org/difference-between-aerospike-and-alibaba-cloud-tsdb/)之间的区别

**1。Aerospike:**
Aerospike 是一个闪存优化的内存开源 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，以生产它的同名公司命名。这是一个关键价值数据存储，旨在为实时大数据应用程序提供亚毫秒级的响应时间。Aerospike 的三个主要组件是 Aerospike 数据库服务器、Aerospike 智能客户端和 Aerospike 管理控制台。

**2。阿里巴巴云 TSDB :**
阿里巴巴云 TSDB 是一个分布式时间序列数据库。它是一种稳定、可靠且经济高效的在线高性能数据库服务。它提供了高效的数据读写能力、高压缩比存储以及时间序列数据插值和聚合。

**Aerospike 与阿里巴巴云 TSDB 的区别:**

<center>

| 没有 | aerospoke | 阿里巴巴云 TSDB |
| --- | --- | --- |
| 1. | 它是由 Aerospike 在 2012 年开发的。 | 是阿里巴巴开发的。 |
| 2. | 这是一个闪存优化的内存 NoSQL 数据库。 | 它是一种稳定、可靠且经济高效的在线高性能时间序列数据库服务。 |
| 3. | Aerospike 的许可证是开源的。 | 阿里巴巴云 TSDB 的许可证是商业的。 |
| 4. | Aerospike 的服务器操作系统是 Linux。 | 阿里巴巴云 TSDB 的服务器操作系统是托管的。 |
| 5. | 它不能作为云服务使用 | 它可以作为云服务使用。 |
| 6. | 它有用户定义的函数，用于使用 Lua 编写服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 支持的分区方法是分片。 | 没有分区方法。 |
| 8. | 它不支持 SQL 查询语言。 | 它也不支持 SQL 查询语言。 |
| 9. | 它仅支持一种复制方法—可选复制因子。 | 它不支持任何复制方法。 |
| 10. | Aerospike 没有提供参照完整性的概念。因此，没有外键。 | TSDB 也没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它为用户定义的映射/缩减方法提供了一个应用编程接口。 | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 |
| 13. | 它只支持操作的原子执行。 | 它不支持任何事务概念。 |
| 14. | 它的主要数据库模型是键值存储。 | 它的主要数据库模型是时序数据库管理系统。 |
| 15. | Aerospike 支持的 API 是 [JDBC](https://www.geeksforgeeks.org/introduction-to-jdbc/) 。 | 阿里巴巴云 TSDB 支持的 API 是 [HTTP REST](https://www.geeksforgeeks.org/rest-api-introduction/) 。 |

</center>