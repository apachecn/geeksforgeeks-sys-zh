# 【Derby 和 MongoDB 的区别

> 原文:[https://www . geeksforgeeks . org/derby-and-MongoDB 之间的差异/](https://www.geeksforgeeks.org/difference-between-derby-and-mongodb/)

**1。德比:**
德比是一个用 Java 实现的全功能、开源的关系数据库管理系统(RDBMS)，顾名思义，它是由 Apache Software Foundations 开发的。它基于 Java、JDBC 和 SQL 标准。Derby 易于安装、部署和使用。它要么嵌入到 Java 应用程序中，要么用作数据库服务器。

**2。MongoDB :**
MongoDB 是一个跨平台的面向文档和非关系(即 NoSQL)的数据库程序。它是一个开源文档数据库，以键值对的形式存储数据。MongoDB 由 MongoDB Inc .开发，最初于 2009 年 2 月 11 日发布。它是用 C++、Go、JavaScript、Python 语言编写的。MongoDB 提供了高速度、高可用性和高扩展性。

**德比与 MongoDB 的区别:**

<center>

| SR.NO | 德比 | MongoDB |
| --- | --- | --- |
| one | 它是由 Apache 软件基金会在 1997 年开发的。 | 它是由 MongoDB Inc .于 2009 年开发的。 |
| Two | 它是用 Java 语言编写的。 | 它是用 C++语言编写的。 |
| three | Derby 的主要数据库模型是关系数据库管理系统。 | MongoDB 的主要数据库模型是文档存储。 |
| four | Derby 的服务器操作系统有 Windows、macOs、Linux、Unix、BSD 和 z/OS。 | 蒙古数据库的服务器操作系统是 Linux、OS X、Solaris 和 Windows。 |
| five | 它有服务器端脚本的 Java 存储过程。 | 它有服务器端脚本的 Javascript。 |
| six | 它支持主从复制方法。 | 它还支持主从复制方法。 |
| seven | Derby 使用的 API 和其他访问方法是 JDBC。 | MongoDB 使用的 API 和其他访问方法是使用 JSON 的专有协议。 |
| eight | 它只支持 Java 编程语言。 | 它支持 C、C#、C++、D、Delphi、Java、JavaScript、Lua、MatLab、Objective-C、Perl、PHP、PL/SQL、Python、R、Ruby、Scala 等。 |
| nine | 它提供了 XML 支持。 | 它不提供 XML 支持。 |
| Ten | 它支持根据 SQL 标准的细粒度访问权限。 | 它不支持用户的访问权限。 |
| Eleven | 它不支持任何分区方法。 | 在 MongoDB 中，分区可以通过分片来完成。 |
| Twelve | 它不支持地图缩小方法。 | 它支持地图缩减方法。 |
| Thirteen | 它提供了即时一致性方法来确保分布式系统中的一致性。 | 它提供最终一致性和即时一致性方法，以确保分布式系统中的一致性。 |
| Fourteen | 它为多文档 ACID 事务提供快照隔离 | 它提供 ACID 事务。 |

</center>