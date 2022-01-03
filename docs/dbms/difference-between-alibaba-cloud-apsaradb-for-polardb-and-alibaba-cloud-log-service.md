# 阿里巴巴云 ApsaraDB for PolarDB 与阿里巴巴云日志服务的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-apsaradb-for-polar db-and-Alibaba-cloud-log-service/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-apsaradb-for-polardb-and-alibaba-cloud-log-service/)

**1。阿里巴巴云宝丽来数据库:**
宝丽来数据库是一个云原生关系数据库，兼容[MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql)[Postgresql](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)和甲骨文。ApsaraDB 架构在单个集群中支持 5000 台物理机。它是为需要快速性能、高并发性和自动扩展的关键业务数据库应用程序而设计的。

**2。阿里巴巴云日志服务:**
日志服务是一项完整的实时数据日志服务。是阿里巴巴集团开发的。它支持日志的收集、消费、运输、搜索和分析。

**阿里巴巴云 ApsaraDB for PolarDB 与阿里巴巴云日志服务的区别:**

<center>

| 没有 | 阿里巴巴云亚太数据库为宝丽来数据库 | 阿里巴巴云日志服务 |
| --- | --- | --- |
| 1. | 它是阿里巴巴在 2013 年 8 月开发的。 | 它是由 AlibabaCloud Inc .于 2016 年开发的。 |
| 2. | 它是一个云原生关系数据库，与 MySQL、PostgreSQL 和 Oracle 兼容。 | 它是一个完整的实时数据记录服务，支持日志的收集、消费、运输、搜索和分析。 |
| 3. | 在阿里巴巴云平台数据库中，有托管服务器操作系统。 | 在阿里巴巴云日志服务中也有托管服务器操作系统。 |
| 4. | 阿里巴巴云 ApsaraDB 对 PolarDB 的许可是商业的。 | 阿里巴巴云日志服务的许可证也是商业的。 |
| 5. | 它支持 XML 格式。 | 它不支持 XML 格式。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 只有一种分区方法——分片。 | 只有一种分区方法——分片。 |
| 8. | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 | 它还支持 SQL 查询语言。 |
| 9. | 它支持复制方法。 | 它支持 3 个副本。 |
| 10. | PolarDB 的 ApsaraDB 还提供了参照完整性的概念。因此，有外键。 | 日志服务不提供引用完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它提供了一个 ES-Hadoop 连接器作为映射/缩减方法。 |
| 13. | 它支持 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 | 它不支持 ACID 属性。 |

</center>