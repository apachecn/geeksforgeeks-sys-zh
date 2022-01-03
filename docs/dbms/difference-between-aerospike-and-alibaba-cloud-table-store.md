# 【Aerospike 与阿里巴巴云平台店的区别

> 原文:[https://www . geeksforgeeks . org/aerospike-and-Alibaba-cloud-table-store/](https://www.geeksforgeeks.org/difference-between-aerospike-and-alibaba-cloud-table-store/)

**1。Aerospike:**
Aerospike 是一个闪存优化的内存开源 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，以生产它的同名公司的名字命名。这是一个关键价值数据存储，旨在为实时大数据应用程序提供亚毫秒级的响应时间。Aerospike 的三个主要组件是 Aerospike 数据库服务器、Aerospike 智能客户端和 Aerospike 管理控制台。

**2。阿里巴巴云表商店:**
阿里巴巴云表商店是一个完全管理的宽列商店，用于存储大量半结构化数据，并可实时访问。这是一个使用多种数据模型的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库服务。Tablestore 由阿里巴巴云开发，可以存储大量结构化数据。它用于高效的查询和数据分析。

**Aerospike 与阿里巴巴云平台店的区别:**

<center>

| 没有 | aerospoke | 阿里巴巴云平台商店 |
| --- | --- | --- |
| 1. | 它是由 Aerospike 在 2012 年开发的。 | 它是阿里巴巴在 2016 年开发的。 |
| 2. | 这是一个闪存优化的内存 NoSQL 数据库。 | 这是一个完全管理的宽列存储，用于存储大量具有实时访问能力的半结构化数据。 |
| 3. | Aerospike 的许可证是开源的。 | 阿里巴巴云表店的牌照是商用的。 |
| 4. | Aerospike 的服务器操作系统是 Linux。 | 阿里巴巴云平台商店有托管服务器操作系统。 |
| 5. | 它不能作为云服务使用。 | 它可以作为云服务使用。 |
| 6. | 它有用户定义的函数，用于使用 Lua 编写服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 支持的分区方法是分片。 | 支持的分区方法是分片。 |
| 8. | 它不支持 SQL 查询语言。 | 它也不支持 SQL 查询语言。 |
| 9. | 它只支持一种复制方法:可选复制因子。 | 它还支持复制方法。 |
| 10. | Aerospike 没有提供参照完整性的概念。因此，没有外键。 | 表存储也不提供引用完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它为用户定义的映射/缩减方法提供了一个应用编程接口。 | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 |
| 13. | 它只支持操作的原子执行。 | 它只支持原子单行操作。 |
| 14. | 它的主要数据库模型是键值存储。 | 它的主要数据库模型是宽列存储。 |

</center>