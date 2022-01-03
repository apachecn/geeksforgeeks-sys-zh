# 阿里巴巴云 ApsaraDB for PolarDB 与阿里巴巴云表店的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-apsaradb-for-polar db-and-Alibaba-cloud-table-store/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-apsaradb-for-polardb-and-alibaba-cloud-table-store/)

**1。阿里巴巴云宝丽来数据库:**
宝丽来数据库是一个云原生关系数据库，兼容[MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql)[Postgresql](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)和甲骨文。ApsaraDB 架构在单个集群中支持 5000 台物理机。它是为需要快速性能、高并发性和自动扩展的关键业务数据库应用程序而设计的。

**2。阿里巴巴云表商店:**
阿里巴巴云表商店是一个完全管理的宽列商店，用于存储大量半结构化数据，并可实时访问。这是一个使用多种数据模型的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库服务。Tablestore 由阿里巴巴云开发，可以存储大量结构化数据。它用于高效的查询和数据分析。

**阿里巴巴云 ApsaraDB for PolarDB 与阿里巴巴云表店的区别:**

<center>

| 没有 | 阿里巴巴云亚太数据库为宝丽来数据库 | 阿里巴巴云平台商店 |
| --- | --- | --- |
| 1. | 它是阿里巴巴在 2013 年 8 月开发的。 | 它是阿里巴巴在 2016 年开发的。 |
| 2. | 它是一个云原生关系数据库，与 MySQL、PostgreSQL 和 Oracle 兼容。 | 这是一个完全管理的宽列存储，用于存储大量具有实时访问能力的半结构化数据。 |
| 3. | 在阿里巴巴云平台数据库中，有托管服务器操作系统。 | 阿里巴巴云平台商店有托管服务器操作系统。 |
| 4. | 阿里巴巴云 ApsaraDB 对 PolarDB 的许可是商业的。 | 阿里巴巴云表店的牌照也是商用的。 |
| 5. | 它支持 XML 格式。 | 它不支持 XML 格式。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 只有一种分区方法——分片。 | 它还支持分区方法。 |
| 8. | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 | 它不支持 SQL 查询语言。 |
| 9. | 它支持复制方法。 | 它还支持复制方法。 |
| 10. | PolarDB 的 ApsaraDB 提供了参照完整性的概念。因此，有外键。 | 表存储不提供引用完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它也没有为用户定义的映射/减少方法提供任何应用编程接口。 |
| 13. | 它支持 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 | 它支持原子单行操作。 |
| 14. | 支持的编程语言有 [Java](https://www.geeksforgeeks.org/java/) 和 Python。 | 支持的编程语言有 Java 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 。 |

</center>