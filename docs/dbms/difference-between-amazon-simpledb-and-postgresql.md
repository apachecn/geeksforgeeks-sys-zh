# 亚马逊 SimpleDB 和 PostgreSQL 的区别

> 原文:[https://www . geesforgeks . org/difference-Amazon-simpledb-and-PostgreSQL/](https://www.geeksforgeeks.org/difference-between-amazon-simpledb-and-postgresql/)

**1。[PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/):**
PostgreSQL 是一个强大的开源对象关系数据库系统。由于其高稳定性，它以低维护工作量提供了良好的性能。PostgreSQL 是第一个实现多版本并发控制(MVCC)功能的数据库管理系统。

**2。亚马逊简单数据库:**
这是一个由亚马逊托管的简单[数据库](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)服务，数据存储在亚马逊云中。亚马逊是一个实时运行结构化数据查询的网络服务。这个数据库是 Amazon.com 用二郎写的。它具有以下特点—高可用性和灵活性，几乎没有或根本没有管理负担。

【PostgreSQL 和 Amazon SimpleDB 的区别:

<center>

| 没有。 | 一种数据库系统 | 亚马逊简单数据库 |
| --- | --- | --- |
| 1. | 它是由 PostgreSQL 全球开发小组于 1989 年开发的。 | 它是亚马逊在 2007 年开发的。 |
| 2. | 它是开源的。 | 这是商业广告。 |
| 3. | PostgreSQL 的服务器操作系统是 FreeBSD、惠普-UX、Linux、NetBSD、OpenBSD、OS X、Solaris、Unix、Windows。 | 亚马逊简单数据库的服务器操作系统是托管的。 |
| 4. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是键值存储。 |
| 5. | 它有预定义的数据类型，如日期或浮动。 | 它没有预定义的数据类型，如日期或浮点数。 |
| 6. | 它支持 SQL。 | 它不支持 SQL。 |
| 7. | PostgreSQL 的 API 和其他访问方法是 ADO.NET，JDBC，原生 C 库，ODBC，大型对象的流 API。 | 用于 Amazon SimpleDB 的 API 和其他访问方法是 RESTful HTTP API。 |
| 8. | PostgreSQL 支持的编程语言有。Net、C、C++、Delphi、Java、JavaScript (Node.js)、Perl、PHP、Python、Tcl。 | 亚马逊 SimpleDB 支持的编程语言有。Net、C、C++、Erlang、Java、PHP、Python、Ruby、Scala。 |
| 9. | 它支持使用用户定义函数的服务器端脚本。 | 它不支持服务器端脚本。 |
| 10. | 它支持触发器。 | 它不支持触发器。 |
| 11. | 它支持使用范围分区、列表分区和哈希分区(自 PostgreSQL 11 以来)的分区方法。 | 它不支持分区方法。 |
| 12. | 它提供了参照完整性的概念。因此，存在外键。 | 它没有提供参照完整性的概念。因此，没有外键。 |
| 13. | 它支持 ACID 属性。 | 它不支持 ACID 属性。 |

</center>