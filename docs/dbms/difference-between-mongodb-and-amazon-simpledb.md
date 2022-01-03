# 【MongoDB 和亚马逊 SimpleDB 的区别

> 原文:[https://www . geeksforgeeks . org/区别-MongoDB-和-amazon-simpledb/](https://www.geeksforgeeks.org/difference-between-mongodb-and-amazon-simpledb/)

**1。 [MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) :**
MongoDB 是一个开源的面向文档的数据库，用于大容量数据存储。属于 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库分类。NoSQL 工具意味着它不使用通常的行和列。MongoDB 使用 BSON(文档存储格式)，这是 JSON 文档的二进制风格。

**2。亚马逊简单数据库:**
它是由亚马逊托管的简单数据库服务，数据存储在亚马逊云中。亚马逊是一个实时运行结构化数据查询的网络服务。这个数据库是 Amazon.com 用二郎写的。它具有以下特点—高可用性和灵活性，几乎没有或根本没有管理负担。

**MongoDB 和亚马逊 SimpleDB 的区别:**

<center>

| 没有 | MongoDB | 亚马逊简单数据库 |
| --- | --- | --- |
| 1. | 它是由蒙古数据库公司在 2009 年开发的。 | 它是亚马逊在 2007 年开发的。 |
| 2. | 它是开源的。 | 这是商业广告。 |
| 3. | 蒙古数据库的服务器操作系统是 Linux、OS X、Solaris、Windows。 | 亚马逊简单数据库的服务器操作系统是托管的。 |
| 4. | 它的主要数据库模型是文档存储。 | 它的主要数据库模型是键值存储。 |
| 5. | 它有预定义的数据类型，如日期或浮动。 | 它没有预定义的数据类型，如日期或浮点数。 |
| 6. | 它通过商业智能的蒙古数据库连接器支持只读的 SQL 查询。 | 它不支持 SQL。 |
| 7. | 用于 MongoDB 的 API 和其他访问方法是使用 JSON 的专有协议。 | 用于 Amazon SimpleDB 的 API 和其他访问方法是 RESTful HTTP API。 |
| 8. | MongoDB 支持的编程语言有 Actionscript、C、C#、C++、Clojure、ColdFusion、D、Dart、Delphi、Erlang、Go、Groovy、Haskell、Java、JavaScript、Lisp、Lua、MatLab、Perl、PHP、PowerShell、Prolog、Python、R、Ruby、Scala、Smalltalk。 | 亚马逊 SimpleDB 支持的编程语言有。Net、C、C++、Erlang、Java、PHP、Python、Ruby、Scala。 |
| 9. | 它支持使用 JavaScript 的服务器端脚本。 | 它不支持服务器端脚本。 |
| 10. | 它支持触发器。 | 它不支持触发器。 |
| 11. | 它支持使用分片的分区方法。 | 它不支持分区方法。 |
| 12. | 它没有提供参照完整性的概念。因此，没有外键。 | 它也没有提供参照完整性的概念。因此，没有外键。 |
| 13. | 它支持带有快照隔离的多文档 ACID 事务。 | 它不支持 ACID 属性。 |

</center>