# 亚马逊极光和亚马逊 SimpleDB 的区别

> 原文:[https://www . geesforgeks . org/区别-Amazon-aurora-和-amazon-simpledb/](https://www.geeksforgeeks.org/difference-between-amazon-aurora-and-amazon-simpledb/)

**1。[亚马逊极光](https://www.geeksforgeeks.org/amazon-aurora/) :**
这是一款来自亚马逊网络服务的全托管关系数据库引擎，兼容 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 和 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql) 。它比标准的 MySQL 数据库快 5 倍，比标准的 PostgreSQL 数据库快 3 倍。极光的特点是分布式、容错和自愈存储系统。

**2。亚马逊简单数据库:**
这是一个由亚马逊托管的简单[数据库](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)服务，数据存储在亚马逊云中。亚马逊是一个实时运行结构化数据查询的网络服务。这个数据库是 Amazon.com 用二郎写的。它具有以下特点—高可用性和灵活性，几乎没有或根本没有管理负担。

**亚马逊极光和亚马逊 SimpleDB 的区别:**

<center>

| 没有 | 亚马逊奥罗拉 | 亚马逊简单数据库 |
| --- | --- | --- |
| 1. | 2015 年由亚马逊开发。 | 2007 年由亚马逊开发。 |
| 2. | 它是亚马逊推出的一款 MySQL 和 PostgreSQL 兼容的云服务。 | 它是由亚马逊托管的简单数据库服务，数据存储在亚马逊云中。 |
| 3. | 它支持 ACID 属性。 | 它不支持 ACID 属性。 |
| 4. | 即时一致性用于确保分布式系统中的一致性。 | 最终一致性和即时一致性用于确保分布式系统中的一致性。 |
| 5. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是键值存储。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 分区可以通过水平分区来完成。 | 它不支持分区方法。 |
| 8. | 它支持 SQL 查询语言。 | 它不支持 SQL 查询语言。 |
| 9. | 它只支持一种复制方法——主从复制。 | 它支持复制方法。 |
| 10. | 它提供了参照完整性的概念。因此，没有外键。 | 它没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持预定义的数据类型，如浮点数或日期。 | 它不支持预定义的数据类型，如浮点数或日期。 |

</center>