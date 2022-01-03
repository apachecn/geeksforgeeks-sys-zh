# 【PouchDB 和 Neo4j 之间的差异

> 原文:[https://www . geesforgeks . org/difference-pouchdb-and-neo4j/](https://www.geeksforgeeks.org/difference-between-pouchdb-and-neo4j/)

**1。PouchDB :**
PouchDB 是一个开源的 NoSQL 在线数据库。它是根据为国家预防机制提供动力的 NoSQL 数据库 CouchDB 设计的。它是用 JavaScript 语言编写的。不需要通过网络执行查询，因为 PouchDB 位于浏览器内部，因此速度非常快。它使用浏览器中的 IndexedDB 和 WebSQL 在本地存储数据。

**2。Neo4j :**
Neo4j 是最著名的图形数据库管理系统，也是由 Neo4j，Inc .开发的 NoSQL 数据库系统。Neo4j 不同于 Mysql 或 MongoDB，因为它有自己的特点，这使得它与其他数据库管理系统相比很特别。Neo4j 以图表的形式存储和呈现数据，而不是表格格式或 Jason 格式。在这里，整个数据由节点表示，在那里，您可以创建节点之间的关系，这意味着整个数据库集合看起来像一个图形，这使得它与其他数据库管理系统不同。

**PouchDB 和 Neo4j 的区别:**

<center>

| 没有 | PouchDB | Neo4j |
| --- | --- | --- |
| 1. | 它是由 Apache 软件基金会开发的。 | 它是由 Neo4j 公司开发的。 |
| 2. | PouchDB 最初于 2012 年发布。 | Neo4j 最初于 2007 年发布。 |
| 3. | 它是用 Javascript 语言编写的。 | 它是用 Java 和 Scala 语言编写的。 |
| 4. | PouchDB 是无服务器的。它需要一个 JavaScript 环境(浏览器，Node.js)。 | Neo4j 服务器操作系统有 Linux、OS X、Solaris 和 Windows。 |
| 5. | 它为我们提供了最终一致性方法，以确保分布式系统中的一致性。 | 它为我们提供了因果集群设置中可配置的因果和最终一致性，以及独立模式中的即时一致性，以确保分布式系统中的一致性。 |
| 6. | 在 PouchDB 中，没有预定义的数据类型。 | Neo4j 有预定义的数据类型，如浮点数、日期等。 |
| 7. | PouchDB 支持地图缩减方法。 | Neo4j 不支持地图缩小方法。 |
| 8. | 它没有提供参照完整性的概念。因此没有外键。 | 它提供了参照完整性的概念。因此有外键。 |
| 9. | 它不提供 ACID 事务概念。 | 它提供了 ACID 事务概念。 |
| 10. | 数据库的主要模型是文档存储。 | Neo4j 的主要数据库模型是 is Graph DBMS。 |
| 11. | 它支持 Javascript 编程语言。 | Neo4j 支持。Net、Clojure、酏、Go、Groovy、Haskell、Java、JavaScript、Perl、PHP、Python、Ruby、Scala 等编程语言。 |
| 12. | PouchDB 支持主从复制和主从复制。 | 它支持使用 Raft 协议复制的因果聚类。 |
| 13. | 它支持分片分区方法。 | 它不支持分区方法。 |
| 14. | API 等访问方式包括 HTTP REST、JavaScript API。 | API 等访问方式包括 Bolt 协议、Cypher 查询语言、Java API、Neo4j-OGM、RESTful HTTP、API、Spring Data Neo4j、TinkerPop 3。 |

</center>