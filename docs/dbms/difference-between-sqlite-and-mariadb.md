# SQLite 和 MariaDB 的区别

> 原文:[https://www . geesforgeks . org/SQLite 和-mariadb 之间的差异/](https://www.geeksforgeeks.org/difference-between-sqlite-and-mariadb/)

**1。SQLite :**
SQLite 是一个提供[关系数据库管理系统(RDBMS)](https://www.geeksforgeeks.org/difference-between-rdbms-and-dbms/) 的软件库。它是由理查德·希普于 2000 年 8 月设计的。SQLite 的设计目标是允许程序在不安装数据库管理系统(DBMS)或不需要数据库管理员的情况下运行。

**2。MariaDB :**
MariaDB 是一个开源的关系数据库管理系统(RDBMS)，是广泛使用的 [MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 数据库技术的兼容插件替代。它由马里亚数据库基金会开发，最初于 2009 年 10 月 29 日发布。MariaDB 有大量新功能，这使得它在性能和面向用户方面比 MySQL 更好。

**SQLite 和 MariaDB 的区别:**

<center>

| 没有 | SQLITE | 马里亚 DB |
| --- | --- | --- |
| 1. | 由理查德·希普于 2000 年 8 月开发。 | 由 MariaDB 公司 Ab 和 MariaDB 基金会于 2009 年开发。 |
| 2. | 它是广泛使用的过程中关系数据库管理系统。 | 它是一个 MySQL 应用程序兼容的开源 RDBMS，增强了高可用性、安全性、互操作性和性能能力。 |
| 3. | SQLite 是用 C 语言编写的。 | MariaDB 是用 C、C++、Perl 和 Bash 语言编写的。 |
| 4. | SQLite 的主要数据库模型是关系数据库管理系统。 | 马里亚数据库的主要数据库模型也是关系数据库管理系统。 |
| 5. | 它没有辅助数据库模型。 | 它有两个辅助数据库模型——文档存储和图形数据库管理系统。 |
| 6. | SQLite 不需要运行服务器。因此，它是无服务器的。 | MariaDB 的服务器操作系统是 FreeBSD、Linux、Solaris 和 Windows。 |
| 7. | 它不支持 XML 格式。 | 它支持 XML 格式。 |
| 8. | 它不支持服务器端脚本。 | 它支持服务器端脚本。 |
| 9. | 它不支持任何复制方法。 | 它支持两种复制方法——主-主复制和主-从复制。 |
| 10. | 它不支持任何分区方法。 | 支持的分区方法有–水平分区，使用 Spider 存储引擎和 Galera 集群进行分片。 |
| 11. | 它不能替代 MariaDB。 | 它为 SQLite 提供了一个替代插件。 |

</center>