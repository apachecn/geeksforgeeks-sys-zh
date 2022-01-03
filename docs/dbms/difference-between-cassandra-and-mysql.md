# 卡珊德拉和 MySQL 的区别

> 原文:[https://www . geesforgeks . org/Cassandra 和-mysql 之间的区别/](https://www.geeksforgeeks.org/difference-between-cassandra-and-mysql/)

**1。[Cassandra](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/):**
Cassandra 是一个免费开源、分布式、宽列存储、NoSQL 数据库管理系统。它由 Apache 软件基金会开发，最初于 2008 年 7 月发布。Cassandra 旨在处理许多商用服务器上的大量数据，提供高可用性，没有单点故障。

**2。 [MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) :**
MySQL 是基于[结构化查询语言(SQL)](https://www.geeksforgeeks.org/structured-query-language/) 的开源关系数据库管理系统(RDBMS)。它由甲骨文公司开发和管理，最初于 1995 年 5 月 23 日发布。它被广泛用于许多小型和大型工业应用中，并且能够处理大量数据。

**卡珊德拉和 MySQL 的区别:**

<center>

| 没有 | 卡桑德拉 | 关系型数据库 |
| --- | --- | --- |
| 1. | 由 Apache 软件基金会开发，于 2008 年 7 月发布。 | 由甲骨文公司开发，于 1995 年 5 月发布。 |
| 2. | Cassandra 仅用 Java 语言编写。 | MySQL 是用 C 和 C++语言编写的。 |
| 3. | 卡珊德拉是一个 NoSQL 类型的数据库。 | MySql 是一个 RDBMS 类型的数据库。 |
| 4. | 它不提供 ACID 属性，但可以进行调整以支持 ACID 属性。 | MySQL 提供了 ACID 属性。 |
| 5. | 卡珊德拉说，读取性能非常高效，因为它需要 0(1)时间。 | MySQl 需要使用 JOIN 从多个表中读取。因此，读取它需要 0(log(n))的时间。 |
| 6. | 在《卡珊德拉》中的写作表现也是非常的高效。 | 用 MySQL 写需要先搜索，这会降低写性能。 |
| 7. | 卡珊德拉没有提供参照完整性的概念。因此没有外键。 | MySQL 提供了引用完整性的概念，并且有外键。 |
| 8. | Cassandra 提供了最终一致性和即时一致性方法，以确保分布式系统中的一致性。 | MySQL 只提供即时一致性方法，以确保分布式系统中的一致性。 | 9. | 卡珊德拉的服务器操作系统是 BSD、Linux、OS X、Windows。 | MySQL 的服务器操作系统有 FreeBSD、Linux、OS X、Solaris、Windows。 | 10. | 像 Hulu、Instagram、Intuit、网飞、Reddit 等知名公司都使用 Cassandra。 | 像 Airbnb、Pinterest、Slack、Udemy、Twitter 等知名公司都使用 MySQL。 |

</center>