# 【AnzoGraph 和 MongoDB 的区别

> 原文:[https://www . geeksforgeeks . org/ANZ graph 和-mongodb 之间的差异/](https://www.geeksforgeeks.org/difference-between-anzograph-and-mongodb/)

**1。 [MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) :**
MongoDB 是一个开源的面向文档的数据库，用于大容量数据存储。属于 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库分类。NoSQL 工具意味着它不使用通常的行和列。MongoDB 使用 BSON(文档存储格式)，这是 JSON 文档的二进制风格。

**2。澳新图:**
这是一个为分析而设计的内存分布式图数据库管理系统。它用于嵌入式分析。该数据库是一个大规模并行处理(MPP)原生图形数据库，旨在以规模、速度和深度链接洞察力进行多种数据协调和分析。

【MongoDB 和 AnzoGraph 的区别:

<center>

| 没有。 | MongoDB | 澳新移民 |
| --- | --- | --- |
| 1. | 它是由蒙古数据库公司在 2009 年开发的。 | 由剑桥语义学于 2018 年开发。 |
| 2. | 它是开源的。 | 这是商业广告。 |
| 3. | 蒙古数据库的服务器操作系统是 Linux、OS X、Solaris、Windows。 | AnzoGraph 的服务器操作系统是 Linux。 |
| 4. | 它的主要数据库模型是文档存储。 | 它的主要数据库模型是图形数据库管理系统，RDF 存储。 |
| 5. | 它是无模式的。 | 它支持数据模式。 |
| 6. | 它通过商业智能的蒙古数据库连接器支持只读的 SQL 查询。 | SPARQL 被用作查询语言。 |
| 7. | 用于 MongoDB 的 API 和其他访问方法是使用 JSON 的专有协议。 | AnzoGraph 的 API 和其他访问方法是 gRPC、JDBC、OpenCypher、RESTful HTTP API、SPARQL。 |
| 8. | MongoDB 支持的编程语言有 Actionscript、C、C#、C++、Clojure、ColdFusion、D、Dart、Delphi、Erlang、Go、Groovy、Haskell、Java、JavaScript、Lisp、Lua、MatLab、Perl、PHP、PowerShell、Prolog、Python、R、Ruby、Scala、Smalltalk。 | AnzoGraph 支持的编程语言有 C++、Java。 |
| 9. | 它支持使用 JavaScript 的服务器端脚本。 | 它还支持服务器端脚本用户定义的功能。 |
| 10. | 它支持触发器。 | 它不支持触发器。 |
| 11. | 它没有提供参照完整性的概念。因此，没有外键。 | 它也没有提供参照完整性的概念。因此，没有外键。 |
| 12. | 它支持带有快照隔离的多文档 ACID 事务。 | 它支持 ACID 属性。 |

</center>