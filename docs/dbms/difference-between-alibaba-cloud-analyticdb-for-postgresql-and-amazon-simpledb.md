# 阿里巴巴云分析数据库对 PostgreSQL 和亚马逊 SimpleDB 的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-analyticdb-for-PostgreSQL-and-Amazon-simpledb/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-analyticdb-for-postgresql-and-amazon-simpledb/)

**1。阿里巴巴云 AnalyticDB for PostgreSQL:**
AnalyticDB 是阿里巴巴云上的一个在线分析处理数据库系统。它同时提供 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 和 MySQL 版本。AnalyticDB for PostgreSQL 是基于 Greenplum 开源数据库程序的在线大规模并行处理(MPP)数据仓库服务，并通过阿里巴巴云的一些深入扩展得到增强。

**2。亚马逊简单数据库:**
这是一个由亚马逊托管的简单[数据库](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)服务，数据存储在亚马逊云中。亚马逊是一个实时运行结构化数据查询的网络服务。这个数据库是 Amazon.com 用二郎写的。它具有以下特点—高可用性和灵活性，几乎没有或根本没有管理负担。

**阿里巴巴云 AnalyticDB for PostgreSQL 与亚马逊 SimpleDB 的区别:**

<center>

| 没有 | 阿里巴巴云分析数据库 | 亚马逊简单数据库 |
| --- | --- | --- |
| 1. | 由阿里巴巴、Pivotal Software Inc .和 PostgreSQL 全球开发集团于 2016 年开发。 | 2007 年由亚马逊开发。 |
| 2. | 它是基于 Greenplum 的在线 MPP(大规模并行处理)数据仓库服务。 | 它是由亚马逊托管的简单数据库服务，数据存储在亚马逊云中。 |
| 3. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是键值存储。 |
| 4. | 支持的编程语言有 C、Java、PHP、R 和 Python。 | 支持的编程语言是。Net、C、C++、Erlang、Java、PHP、Python、Ruby 和 Scala。 |
| 5. | 它支持 ACID 属性。 | 它不支持 ACID 属性。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本 |
| 7. | 它支持分区方法。 | 它不支持分区方法。 |
| 8. | 它支持 SQL 查询语言。 | 它不支持 SQL 查询语言。 |
| 9. | 它支持复制方法。 | 它支持具有多可用性区域的复制方法，以实现高可用性。 |
| 10. | 它提供了参照完整性的概念。因此，有外键。 | 它没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持 ACID 属性。 | 它支持原子单文档操作 |

</center>