# 阿里巴巴云 ApsaraDB 对 PolarDB 和阿里巴巴云 TSDB 的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-apsaradb-for-polar db-and-Alibaba-cloud-tsdb/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-apsaradb-for-polardb-and-alibaba-cloud-tsdb/)

**1。阿里巴巴云 ApsaraDB for polaridb:**
它是一个云原生关系数据库，兼容[MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql)[PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)和 Oracle。ApsaraDB 架构在单个集群中支持 5000 台物理机。它是为需要快速性能、高并发性和自动扩展的关键业务数据库应用程序而设计的。

**2。阿里巴巴云 TSDB :**
它是一个分布式时间序列数据库。它是一种稳定、可靠且经济高效的在线高性能数据库服务。它提供了高效的数据读写能力、高压缩比存储以及时间序列数据插值和聚合。

**阿里巴巴云 ApsaraDB for PolarDB 与阿里巴巴云 TSDB 的区别:**

<center>

| 没有 | 阿里巴巴云亚太数据库为宝丽来数据库 | 阿里巴巴云 TSDB |
| --- | --- | --- |
| 1. | 它是阿里巴巴在 2013 年 8 月开发的。 | 是阿里巴巴开发的。 |
| 2. | 它是一个云原生关系数据库，与 MySQL、PostgreSQL 和 Oracle 兼容。 | 它是一种稳定、可靠且经济高效的在线高性能时间序列数据库服务。 |
| 3. | 在阿里巴巴云平台数据库中，有托管服务器操作系统。 | 阿里巴巴云 TSDB 有托管服务器操作系统。 |
| 4. | 阿里巴巴云 ApsaraDB 对 PolarDB 的许可是商业的。 | 阿里巴巴云 TSDB 的牌照也是商用的。 |
| 5. | 它支持 XML 格式。 | 它不支持 XML 格式。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 只有一种分区方法——分片。 | 没有分区方法。 |
| 8. | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 | 它不支持 SQL 查询语言。 |
| 9. | 它支持复制方法。 | 它不支持复制方法。 |
| 10. | PolarDB 的 ApsaraDB 提供了参照完整性的概念。因此，有外键。 | TSDB 没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它也没有为用户定义的映射/减少方法提供任何应用编程接口。 |
| 13. | 它支持 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 | 它不支持 ACID 属性。 |
| 14. | 支持的编程语言有 [Java](https://www.geeksforgeeks.org/java/) 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 。 | 支持的编程语言是 Java。 |

</center>