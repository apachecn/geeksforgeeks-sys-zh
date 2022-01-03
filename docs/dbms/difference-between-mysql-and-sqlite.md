# 【MySQL 和 SQLite 的区别

> 原文:[https://www . geesforgeks . org/MySQL-and-SQLite 之间的区别/](https://www.geeksforgeeks.org/difference-between-mysql-and-sqlite/)

**1。 [MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) :**
MySQL 是基于结构化查询语言(SQL)的开源关系数据库管理系统(RDBMS)。它由甲骨文公司开发和管理，最初于 1995 年 5 月 23 日发布。它被广泛用于许多小型和大型工业应用中，并且能够处理大量数据。

**2。SQLite :**
SQLite 是一个提供关系数据库管理系统(RDBMS)的软件库。它是由理查德·希普于 2000 年 8 月设计的。SQLite 的设计目标是允许程序在不安装数据库管理系统(DBMS)或不需要数据库管理员的情况下运行。SQLite 中的 lite 意味着在设置、数据库管理和所需资源方面重量轻。

**MySQL 和 SQLite 的区别:**

<center>

| 没有 | 关系型数据库 | SQLite |
| --- | --- | --- |
| 1. | 由甲骨文公司于 1995 年 5 月开发。 | 由理查德·希普于 2000 年 8 月开发。 |
| --- | --- | --- |
| 2. | MySQL 是用 C 和 C++语言开发的。 | SQLite 只用 C 语言开发。 |
| --- | --- | --- |
| 3. | MySQL 需要一个数据库服务器才能运行。因此，它遵循客户机/服务器架构。 | SQLite 不需要运行服务器。因此，它是无服务器的。 |
| --- | --- | --- |
| 4. | 它可以同时处理多个连接。 | 它一次只能处理一个连接。 |
| --- | --- | --- |
| 5. | 它具有高度的可扩展性，可以非常高效地处理大量数据。 | 如果数据量增加，性能下降，它只能处理少量数据。 |
| --- | --- | --- |
| 6. | 它需要很大的内存空间才能运行(大约 600 Mb)。 | 它只需要一些千字节的空间，因为它非常轻(大约 250 千字节-300 千字节)。 |
| --- | --- | --- |
| 7. | MySQL 支持多用户环境。 | SQLite 不支持多用户环境。 |
| --- | --- | --- |
| 8. | 它还支持 XML 格式。 | 它不支持 XML 格式。 |
| --- | --- | --- |

</center>