# 亚马逊极光和亚马逊 DocumentDB 的区别

> 原文:[https://www . geesforgeks . org/区别-Amazon-aurora-和-amazon-documentdb/](https://www.geeksforgeeks.org/difference-between-amazon-aurora-and-amazon-documentdb/)

**1。[亚马逊极光](https://www.geeksforgeeks.org/amazon-aurora/) :**
这是一款来自亚马逊网络服务的全托管关系数据库引擎，兼容 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 和 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql) 。它比标准的 MySQL 数据库快 5 倍，比标准的 PostgreSQL 数据库快 3 倍。极光的特点是分布式、容错和自愈存储系统。

**2。亚马逊文档数据库:**
这是一个商业许可的数据库，具有以下特点，因为它是一个快速、可扩展、高可用性和完全托管的文档数据库服务，支持 MongoDB 工作负载。它目前在 AWS 的加利福尼亚、俄勒冈、北弗吉尼亚和爱尔兰地区提供。它通过模拟响应来实现 Apache 2.0 开源 MongoDB 3.6 应用编程接口。

**亚马逊极光与亚马逊 DocumentDB 的区别:**

<center>

| 没有 | 亚马逊奥罗拉 | Amazon DocumentDB |
| --- | --- | --- |
| 1. | 它是亚马逊在 2015 年开发的。 | 它是亚马逊在 2019 年开发的。 |
| 2. | 它是亚马逊推出的一款 MySQL 和 PostgreSQL 兼容的云服务。 | 它是一个快速、可扩展、高可用性和完全管理的 MongoDB 兼容的数据库服务。 |
| 3. | 亚马逊极光的许可证是商业的。 | 亚马逊 DocumentDB 的许可证也是商业的。 |
| 4. | 亚马逊极光有托管服务器操作系统。 | 在亚马逊文档数据库中，有托管服务器操作系统。 |
| 5. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是文档存储。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 分区可以通过水平分区来完成。 | 它不支持分区方法。 |
| 8. | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 | 它不支持 SQL 查询语言。 |
| 9. | 它只支持一种复制方法:主从复制。 | 它支持高可用性的多可用性区域。 |
| 10. | 它提供了参照完整性的概念。因此，有外键。 | 它没有提供参照完整性的概念。因此，没有外键。但是可以通过亚马逊弹性地图缩减来实现。 |
| 11. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它也没有为用户定义的映射/减少方法提供任何应用编程接口。但是可以通过亚马逊弹性地图缩减来实现。 |
| 12. | 它支持 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 | 它支持原子单文档操作。 |

</center>