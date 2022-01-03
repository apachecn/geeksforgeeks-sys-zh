# 【PouchDB 和 Couchbase 之间的差异

> 原文:[https://www . geeksforgeeks . org/pouchdb 和-couchbase 之间的差异/](https://www.geeksforgeeks.org/difference-between-pouchdb-and-couchbase/)

**1。PouchDB :**
PouchDB 是一个开源的、 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 的在线数据库。它是根据 CouchDB 设计的，这是一个为国家预防机制提供动力的 NoSQL 数据库。是用 [JavaScript 语言](https://www.geeksforgeeks.org/javascript-tutorial/)写的。不需要通过网络执行查询，因为 PouchDB 位于浏览器内部，因此速度非常快。它使用浏览器中的 IndexedDB 和 WebSQL 在本地存储数据。

**2。couch base:**
couch base Server 是一个开源、分布式、JSON 文档数据库，针对交互式应用程序进行了增强。它也被称为 Membase。它由 Couchbase，Inc .开发，最初于 2010 年 8 月发布。它使用 C++、Erlang、C、Go 语言编写，其服务器旨在为我们提供易于扩展的键值或 JSON 文档访问，具有高持续吞吐量和低延迟。

**PouchDB 和 Couchbase 的区别:**

<center>

| 没有 | PouchDB | 美洲狮号 |
| --- | --- | --- |
| 1. | 由 Apache 软件基金会开发。 | 由 Couchbase 公司开发。 |
| 2. | 它最初于 2012 年发布。 | 它最初于 2010 年 8 月发布。 |
| 3. | 它是用 Javascript 语言编写的。 | 它是用 C++、Erlang、C 和 Go 语言编写的。 |
| 4. | 它不支持 SQL。 | 它提供了对声明性查询语言(N1QL)的支持，该语言将 ANSI SQL 扩展到 JSON。 |
| 5. | 它只提供最终一致性方法来确保分布式系统中的一致性。 | 它为我们提供了最终一致性和即时一致性方法，以确保分布式系统中的一致性。 |
| 6. | 它不支持 ACID 事务。 | 它支持 ACID 转换。 |
| 7. | 在 PouchDB 中，没有预定义的数据类型。 | Couchbase 的预定义数据类型有布尔值、字符串、数字等。 |
| 8. | 它没有服务器。它需要一个 JavaScript 环境(浏览器，Node.js)。 | 它有 Linux、OS X 和 Windows 作为服务器操作系统。 |
| 9. | 它支持 JavaScript 编程语言。 | 它支持。NetC、Clojure、ColdFusion、Erlang、Go、Java、JavaScript、Perl、PHP、Python、Ruby、Scala、Tcl 等编程语言。 |
| 10. | 它使用 HTTP REST JavaScript API。 | 它为 CRUD、查询、搜索和分析 API 使用本机语言绑定。 |

</center>