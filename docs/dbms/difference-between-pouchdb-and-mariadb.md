# 【PouchDB 和 MariaDB 之间的差异

> 原文:[https://www . geesforgeks . org/pouchdb 和-mariadb 之间的差异/](https://www.geeksforgeeks.org/difference-between-pouchdb-and-mariadb/)

**1。 [PouchDB](https://www.geeksforgeeks.org/pouchdb/) :**
PouchDB 是一个开源的、 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 的、在线的数据库。它是在 [CouchDB](https://www.geeksforgeeks.org/couchdb/) 之后设计的，后者是一个为 npm 提供动力的 NoSQL 数据库。它是用 JavaScript 语言编写的。不需要通过网络执行查询，因为 PouchDB 位于浏览器内部，因此速度非常快。它使用浏览器中的 IndexedDB 和 WebSQL 在本地存储数据。

**2。MariaDB :**
MariaDB 是一个开源的关系数据库管理系统( [RDBMS](https://www.geeksforgeeks.org/rdbms-architecture/) ，它是广泛使用的 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql) 数据库技术的兼容插件替代。它由马里亚数据库基金会开发，最初于 2009 年 10 月 29 日发布。MariaDB 有大量新功能，这使得它在性能和面向用户方面比 MySQL 更好。

**PouchDB 和 MariaDB 的区别:**

<center>

| SR.NO | PouchDB | 马里亚 DB |
| --- | --- | --- |
| 1. | 它是由 Apache 软件基金会开发的。 | 它是由马里亚数据库基金会开发的。 |
| 2. | 2012 年上映。 | 它于 2009 年 10 月 29 日发布。 |
| 3. | PouchDB 服务器操作系统是无服务器的，需要 JavaScript 环境(浏览器， [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) )。 | MariaDB 服务器操作系统有 FreeBSD、Linux、Solaris 和 Windows。 |
| 4. | 使用 [Javascript](https://www.geeksforgeeks.org/javascript-tutorial/) 语言编写。 | 它是用 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Perl](https://www.geeksforgeeks.org/perl-programming-language/) 和 Bash 语言编写的。 |
| 5. | 它没有数据模式。 | 它支持动态列数据模式。 |
| 6. | 它为我们提供了最终一致性方法，以确保分布式系统中的一致性。 | 它为我们提供了即时一致性方法，以确保分布式系统中的一致性。 |
| 7. | 它没有提供引用完整性的概念，因此没有外键。 | 它提供了引用完整性的概念，并具有外键。 |
| 8. | 它没有预定义的数据类型。 | 它有预定义的数据类型，如浮点数、日期、数字等。 |

</center>