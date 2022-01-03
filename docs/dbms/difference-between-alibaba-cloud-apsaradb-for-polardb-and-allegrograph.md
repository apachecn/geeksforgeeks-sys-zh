# 阿里巴巴云 ApsaraDB 对 PolarDB 和快板的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-apsaradb-for-polar db-and-allegrograph/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-apsaradb-for-polardb-and-allegrograph/)

**1。阿里巴巴云 ApsaraDB for polaridb:**
它是一个云原生关系数据库，兼容[MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql)[PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)和 Oracle。ApsaraDB 架构在单个集群中支持 5000 台物理机。它是为需要快速性能、高并发性和自动扩展的关键业务数据库应用程序而设计的。

**2。**
这是一个高性能、持久的 RDF 存储，还支持图形数据库管理系统。它是一个文档存储库，用于以 JSON-LD 格式存储、检索和管理面向文档的信息。2004 年发布了第一个版本的 AllegroGraph。

**阿里巴巴云 ApsaraDB for PolarDB 和 AllegroGraph 的区别:**

<center>

| 没有 | 阿里巴巴云亚太数据库为宝丽来数据库 | ALLEGROGRAPH |
| --- | --- | --- |
| 1. | 它是阿里巴巴在 2013 年 8 月开发的。 | 它是由弗朗茨公司在 2004 年开发的。 |
| 2. | 它是一个云原生关系数据库，与 MySQL、PostgreSQL 和 Oracle 兼容。 | 这是一个高性能、持久的 RDF 存储，并额外支持图形数据库管理系统。 |
| 3. | 在阿里巴巴云平台数据库中，有托管服务器操作系统。 | AllegroGraph 的服务器操作系统是 Linux、OS X 和 Windows。 |
| 4. | 阿里巴巴云 ApsaraDB 对 PolarDB 的许可是商业的。 | AllegroGraph 的许可证也是商业的。 |
| 5. | 它支持 XML 格式。 | 它不支持 XML 格式。 |
| 6. | 它支持服务器端脚本 | 它支持服务器端脚本，使用 JavaScript 或通用 Lisp。 |
| 7. | 只有一种分区方法——分片。 | 分区可以通过联合来完成。 |
| 8. | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 | 它使用 SPARQL 作为查询语言。 |
| 9. | 它支持复制方法。 | 它支持两种复制方法:主从复制和多主复制。 |
| 10. | PolarDB 的 ApsaraDB 提供了参照完整性的概念。因此，有外键。 | 指称程序没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它也没有为用户定义的映射/减少方法提供任何应用编程接口。 |
| 13. | 它可以作为云服务使用。 | 它不能作为云服务使用。 |
| 14. | 支持的编程语言有 [Java](https://www.geeksforgeeks.org/java/) 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 。 | 支持的编程语言有 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、Clojure、Java、Lisp、 [Perl](https://www.geeksforgeeks.org/perl-programming-language/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 、 [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/) 和 [Scala](https://www.geeksforgeeks.org/scala-programming-language/) 。 |

</center>