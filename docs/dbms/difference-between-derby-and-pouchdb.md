# 德比郡和普切德的区别

> 原文:[https://www . geeksforgeeks . org/derby-and-pouchdb/](https://www.geeksforgeeks.org/difference-between-derby-and-pouchdb/)之间的差异

**1。德比:**
德比是一个用 Java 实现的全功能、开源的关系数据库管理系统(RDBMS)，顾名思义，它是由 Apache Software Foundations 开发的。它基于 Java、JDBC 和 SQL 标准。Derby 易于安装、部署和使用。它要么嵌入到 Java 应用程序中，要么用作数据库服务器。

**2。 [PouchDB](https://www.geeksforgeeks.org/pouchdb/) :**
PouchDB 是一个开源的 NoSQL 在线数据库。它是根据 CouchDB 设计的，这是一个为国家预防机制提供动力的 NoSQL 数据库。它是用 JavaScript 语言编写的。不需要通过网络执行查询，因为 PouchDB 位于浏览器内部，因此速度非常快。它使用浏览器中的 IndexedDB 和 WebSQL 在本地存储数据。

**德比郡和普切德的区别:**

<center>

| 没有 | 德比 | Pouchdb |
| --- | --- | --- |
| one | 它是由 Apache 软件基金会在 1997 年开发的。 | 它由 Apache 软件基金会于 2012 年开发。 |
| Two | 它是用 Java 语言编写的。 | 它是用 Javascript 语言编写的。 |
| three | Derby 的主要数据库模型是关系数据库管理系统。 | PouchDB 的主要数据库模型是文档存储。 |
| four | Derby 的服务器操作系统有 Windows、macOs、Linux、Unix、BSD 和 z/OS。 | PouchDB 服务器操作系统是无服务器的，需要一个 JavaScript 环境(浏览器，Node.js)。 |
| five | Derby 使用的 API 和其他访问方法是 JDBC。 | PouchDB 使用的 API 和其他访问方法是 HTTP REST、JavaScript API。 |
| six | 它只支持 Java 编程语言。 | 它只支持 Javascript 编程语言。 |
| seven | 它支持主从复制方法。 | 它支持主从复制，主从复制。 |
| eight | 在 Derby 中，分区是无法完成的。 | 在 PouchDB 中，分区可以通过分片来完成。 |
| nine | 它是一个开源软件框架。 | 它是一个开源软件框架。 |
| Ten | 它支持根据 SQL 标准的细粒度访问权限。 | 它不支持访问权限。 |

</center>