# 【Neo4j 和 Redis 的区别

> 原文:[https://www . geesforgeks . org/difference-neo4j-and-redis/](https://www.geeksforgeeks.org/difference-between-neo4j-and-redis/)

**1。 [Neo4j](https://www.geeksforgeeks.org/neo4j-introduction/) :**
Neo4j 是最著名的 graph [数据库管理系统](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)，也是 Neo4j，Inc .开发的 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库系统，与 [Mysql](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 或 [MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) 不同的是，它有自己的特点，这使得它与其他数据库管理系统相比很特别。Neo4j 还以图表的形式存储和呈现数据，而不是表格格式或 Jason 格式。在这种情况下，整个数据由节点表示，您可以在节点之间创建关系，这意味着整个数据库集合看起来像一个图形，这使得 Neo4j 与其他数据库管理系统不同。

**2。Redis :**
Redis 或远程字典服务器，这是一个应用分布式内存键值数据库的内存数据结构项目，由 Redis 实验室开发，最初于 2009 年 5 月 10 日发布。它也是根据 BSD 3 条款许可发布的开源软件。它还为我们提供了内存效率、高可用性、快速运行速度，并提供了一些功能，如复制、集群等。

**Neo4j 和 Redis 的区别:**

<center>

| 没有。 | Neo4j | Redis |
| --- | --- | --- |
| 1. | 它是由 Neo4j 公司开发的。 | 它是由 Redis 实验室开发的。 |
| 2. | 它最初于 2007 年发布。 | 最初于 2009 年 5 月 10 日发布。 |
| 3. | 它是用 Java 和 Scala 语言编写的。 | 它是用 ANSI 和 C 语言编写的。 |
| 4. | Neo4j 服务器操作系统有 Linux、OS X、Solaris 和 Windows。 | 它的服务器操作系统是 BDS、Linux、OS X 和 Windows。 |
| 5. | 它为我们提供了因果集群设置中可配置的因果和最终一致性，以及独立模式中的即时一致性。 | 它为我们提供了最终一致性，与 CRDTs 的强最终一致性。 |
| 6. | Neo4j APIs 等访问方式包括 Bolt 协议、Cypher 查询语言、Java API、Neo4j-OGM、RESTful HTTP、API、Spring Data Neo4j、TinkerPop 3。 | API 和其他访问方法包括专有协议。 |
| 7. | 它有外键。 | 它没有外键。 |
| 8. | 它的主要数据库模型是图数据库管理系统。 | 它的主要数据库模型是键值存储。 |
| 9. | Neo4j 支持的编程语言是。Net、Clojure、酏、Go、Groovy、Haskell、Java、JavaScript、Perl、PHP、Python、Ruby 和 Scala。 | 它支持 C、C#、C++、Clojure、Crystal、D、Dart、酏、Erlang、Fancy、Go、Haskell、Haxe、Java、JavaScript (Node.js)、Lisp、Lua、MatLab、Objective-C、OCaml、Pascal、Perl、PHP、Prolog、Pure Data、Python、R、Rebol、Ruby、Rust、Scala、Scheme、Smalltalk、Swift、Tcl、Visual Basic 编程语言。 |
| 10. | 它不支持分区方法。 | 它不支持共享分区方法。 |

</center>