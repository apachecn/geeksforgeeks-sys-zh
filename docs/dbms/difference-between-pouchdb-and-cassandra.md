# 【PouchDB 和 Cassandra 的区别

> 原文:[https://www . geeksforgeeks . org/pouchdb 和-cassandra 之间的差异/](https://www.geeksforgeeks.org/difference-between-pouchdb-and-cassandra/)

**1。 [PouchDB](https://www.geeksforgeeks.org/pouchdb/) :**
PouchDB 是一个开源的、 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 的、在线的数据库。它是在为 npm 提供动力的 NoSQL 数据库 [CouchDB](https://contribute.geeksforgeeks.org/couchdb/) 之后设计的。是用 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 语言写的。不需要通过网络执行查询，因为 PouchDB 位于浏览器内部，因此速度非常快。它使用浏览器中的 IndexedDB 和 WebSQL 在本地存储数据。

**2。[卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/) :**
卡珊德拉是一个开源的分布式数据库管理系统，拥有广泛的列存储，NoSQL 数据库，旨在处理和支持许多服务器上的大量数据。它为我们提供了无单点故障的高可用性。Cassandra 最初于 2008 年 7 月发布，由 Apache 软件基金会开发。

**PouchDB 和 Cassandra 的区别:**

<center>

| 没有 | PouchDB | 卡桑德拉 |
| --- | --- | --- |
| 1. | PouchDB 最初于 2012 年发布，由 Apache 软件基金会开发。 | Cassandra 最初于 2008 年 7 月发布，由 Apache 软件基金会开发。 |
| 2. | PouchDB 是用 Javascript 语言编写的。 | 卡珊德拉只用 [Java](https://www.geeksforgeeks.org/java/) 语言编写。 |
| 3. | PouchDB 是无服务器的。它需要一个 JavaScript 环境(浏览器，Node.js)。 | 卡珊德拉服务器操作系统是 BSD、Linux、OS X 和 Windows。 |
| 4. | PouchDB 支持 JavaScript 编程语言。 | Cassandra 支持的编程语言有 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、Clojure、Erlang、 [Go](https://www.geeksforgeeks.org/golang/) 、Haskell、Java、JavaScript、 [Perl](https://www.geeksforgeeks.org/perl-programming-language/) 、 [PHP](https://www.geeksforgeeks.org/php/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 、 [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/) 和 [Scala](https://www.geeksforgeeks.org/scala-programming-language/) 。 |
| 5. | PouchDB 仅提供最终一致性方法来确保分布式系统中的一致性。 | Cassandra 为我们提供了最终一致性和即时一致性方法，以确保分布式系统中的一致性。 |
| 6. | PouchDB 没有预定义的数据类型。 | Cassandra 有预定义的数据类型，如浮点数、日期等。 |
| 7. | 在 PouchDB 中，无法定义用户的访问权限。 | 在 Cassandra 中，可以为每个对象定义用户的访问权限。 |
| 8. | PouchDB 支持主从复制和主从复制。 | 卡珊德拉支持选择性复制因子复制方法。 |
| 9. | PouchDB 支持二级索引，没有任何限制。 | 卡珊德拉的二级索引受到限制。 |
| 10. | 像 GenCorp Technologies、Akamai Technologies、Hothead Games Inc .和 Vivint Solar 等公司都使用 PouchDB。 | Instagram、Reddit、GitHub、Hulu、天气频道等一些公司使用 Cassandra。 |

</center>