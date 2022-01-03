# 阿里巴巴云分析数据库 PostgreSQL 和快语

的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-analyticdb-for-PostgreSQL-and-allegrograph/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-analyticdb-for-postgresql-and-allegrograph/)

**1。PostgreSQL 的 cloud AnalyticDB:**
AnalyticDB 是阿里巴巴云上的一个在线分析处理数据库系统。它提供了 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 和 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql) 两个版本。PostgreSQL 的 AnalyticDB 是基于 Greenplum 开源数据库程序的在线 MPP(大规模并行处理)数据仓库服务，并通过阿里巴巴云的一些深入扩展得到增强。

**2。快板:**
快板是一个高性能、持久的 RDF 存储，还支持图形数据库管理系统。它是一个文档存储库，用于以 JSON-LD 格式存储、检索和管理面向文档的信息。第一个版本的 AllegroGraph 发布于 2004 年。

**阿里巴巴云分析数据库对 PostgreSQL 和 AllegroGraph 的区别:**

<center>

| 没有 | 阿里巴巴云分析数据库 | ALLEGROGRAPH |
| --- | --- | --- |
| 1. | 它由阿里巴巴、Pivotal Software Inc .和 PostgreSQL 全球开发集团于 2016 年开发。 | 它是由弗朗茨公司在 2004 年开发的。 |
| 2. | 它是基于 Greenplum 的在线 MPP(大规模并行处理)数据仓库服务。 | 这是一个高性能、持久的 RDF 存储，并额外支持图形数据库管理系统。 |
| 3. | 在阿里巴巴云分析数据库中，有托管服务器操作系统。 | AllegroGraph 的服务器操作系统是 linux、OS X 和 Windows。 |
| 4. | 阿里巴巴云分析数据库对 PostgreSQL 的许可是商业的。 | AllegroGraph 的许可证也是商业的。 |
| 5. | 它支持 XML 格式。 | 它不支持 XML 格式。 |
| 6. | 它支持服务器端脚本。 | 它支持服务器端脚本，使用 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 或通用 Lisp。 |
| 7. | 它支持分区方法。 | 分区可以通过联合来完成。 |
| 8. | 支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 | 它支持 SPARQL 作为查询语言。 |
| 9. | 它支持复制方法。 | 它支持两种复制方法:主从复制和多主复制。 |
| 10. | PostgreSQL 的 AnalyticDB 提供了引用完整性的概念。因此，有外键。 | 指称程序没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它不支持内存功能。 | 它也不支持内存功能。 |
| 12. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它也没有为用户定义的映射/减少方法提供任何应用编程接口。 |
| 13. | 它可以作为云服务使用。 | 它不能作为云服务使用。 |
| 14. | 支持的编程语言有 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [Perl](https://www.geeksforgeeks.org/perl-programming-language/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 和 [R](https://www.geeksforgeeks.org/introduction-to-r-programming-language/) 。 | 支持的编程语言有 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 、Clojure、Java、Lisp、Perl、Python、 [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/) 和 [Scala](https://www.geeksforgeeks.org/scala-programming-language/) 。 |

</center>