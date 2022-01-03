# 【Aerospike 和阿里巴巴云 MaxCompute 的区别

> 原文:[https://www . geesforgeks . org/aerospike-and-Alibaba-cloud-maxcompute/](https://www.geeksforgeeks.org/difference-between-aerospike-and-alibaba-cloud-maxcompute/)的区别

**1。Aerospike :**
这是一个闪存优化的内存开源 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，以生产它的同名公司的名字命名。这是一个关键价值数据存储，旨在为实时大数据应用程序提供亚毫秒级的响应时间。Aerospike 的三个主要组件是 Aerospike 数据库服务器、Aerospike 智能客户端和 Aerospike 管理控制台。

**2。【阿里巴巴云 MaxCompute :**
它以前被称为 ODPS，是一个通用的、完全托管的、多租户的数据处理平台，用于大规模数据仓储。它用于存储和计算成批的结构化数据。它提供了大量的数据仓库解决方案以及大数据分析和建模服务。

**Aerospike 与阿里巴巴云 MaxCompute 的区别:**

<center>

| 没有 | aerospoke | 阿里巴巴云 MaxCompute |
| --- | --- | --- |
| 1. | 它是由 Aerospike 在 2012 年开发的。 | 它是阿里巴巴在 2016 年开发的。 |
| 2. | 这是一个闪存优化的内存 NoSQL 数据库。 | 它是一个通用的、完全管理的、多租户的数据处理平台，用于大规模数据仓库。 |
| 3. | Aerospike 的许可证是开源的。 | 阿里巴巴云 MaxCompute 的许可证是商用的。 |
| 4. | Aerospike 的服务器操作系统是 Linux。 | 在阿里巴巴云 MaxCompute 中，有托管服务器操作系统。 |
| 5. | 它不能作为云服务使用。 | 它可以作为云服务使用。 |
| 6. | 它有用户定义的函数，用于使用 Lua 编写服务器端脚本。 | 它具有用户定义的功能，用于使用 [Java](https://www.geeksforgeeks.org/java/) 进行服务器端脚本编写。 |
| 7. | 支持的分区方法是分片。 | 支持的分区方法是分片。 |
| 8. | 它不支持 SQL 查询语言。 | 它支持类似 SQL 的查询语言。 |
| 9. | 它仅支持一种复制方法—可选复制因子。 | 它还支持复制方法。 |
| 10. | Aerospike 没有提供参照完整性的概念。因此，没有外键。 | MaxCompute 也没有提供引用完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它只支持操作的原子执行。 | 它不支持 ACID 属性。 |
| 13. | 它的主要数据库模型是键值存储。 | 它的主要数据库模型是[关系数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/)。 |

</center>