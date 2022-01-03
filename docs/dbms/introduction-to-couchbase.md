# couch base 介绍

> 原文:[https://www.geeksforgeeks.org/introduction-to-couchbase/](https://www.geeksforgeeks.org/introduction-to-couchbase/)

Couchbase Server 是一个开源的、分布式的、多模型的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) ，JSON 文档数据库，针对交互式应用程序进行了增强。它也被称为 Membase。它由 Couchbase，Inc .开发，最初于 2010 年 8 月发布。
使用 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、二郎、 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [Go](https://www.geeksforgeeks.org/golang/) 语言编写。它的服务器旨在为我们提供易于扩展的键值或 JSON 文档访问，具有高持续吞吐量和低延迟。这些应用程序可以通过存储、创建、聚合、检索、操作和呈现数据来帮助服务于许多用户。它被设计为从一台机器聚集到跨越多台机器的非常大规模的部署。

**Couchbase 的历史:**
Memcached 项目的几位领导者扩展了 couch base，利用 Memcached 的简单性、速度和可扩展性来开发键值存储。NorthScale 贡献了最初的 membase 源代码，项目共同发起人 Zynga 和 Naver Corporation 在 2010 年 6 月贡献了一个关于 membase.org 的新项目。
Membase 项目创始人和 Membase，Inc .于 2011 年 2 月 8 日宣布与 CouchOne 合并，并进行关联项目合并。2012 年 1 月，合并后的公司名为 Couchbase，Inc .Couchbase 发布了 Couchbase Server 1.8。Orbitz 在 2012 年 9 月改变了一些系统，使用 Couchbase。couch base Server 2.0(2011 年 7 月发布)于 2012 年 12 月发布。它包括一个新的 JSON 文档存储、增量 MapReduce、索引和查询以及跨数据中心的复制。

**couch base 的特点:**

*   这是一个开源的 NoSQL 数据库，它为我们提供了一种存储和恢复数据的机制，这种机制的建模方式不同于关系数据库中使用的表格关系。
*   它非常有用，因为它针对交互式应用程序进行了优化。
*   它具有无模式的数据模式。
*   它有多个数据访问路径来查询和管理我们的 JSON 文档。
*   它具有灵活的数据访问路径，这使得它对各种各样的应用程序和用例更加有用。
*   它支持将 ANSI SQL 扩展到 JSON 的声明式查询语言(N1QL)。
*   它提供最终一致性和即时一致性方法，以确保分布式系统中的一致性。
*   它没有提供参照完整性的概念。因此，没有外键。
*   它支持地图缩减方法。
*   它有预定义的数据类型，如布尔值、字符串、数字等。
*   Couchbase 的主要数据库模型是文档存储。
*   Couchbase 的辅助数据库模型是键值存储。
*   它支持 XML 数据格式。
*   在 Couchbase 中，分区可以通过分片来完成。
*   它支持主从复制和主-主复制复制方法。
*   它具有内存功能。
*   它提供了 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 交易概念。
*   它还支持二级索引，没有任何限制。
*   它在服务器端脚本的 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 中有函数和定时器。
*   它使用 Linux、OS X 和 Windows 作为其服务器操作系统。
*   它被一些公司使用，如道尔集团、洛克伍德出版公司、代码编织公司、微软集团等。