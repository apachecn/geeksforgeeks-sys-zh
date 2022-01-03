# 塞式和快语的区别

> 原文:[https://www . geeksforgeeks . org/aerospike-and-allegrograph 之间的差异/](https://www.geeksforgeeks.org/difference-between-aerospike-and-allegrograph/)

**1。Aerospike:**
Aerospike 是一个闪存优化的内存开源 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库，以生产它的同名公司命名。这是一个关键价值数据存储，旨在为实时大数据应用程序提供亚毫秒级的响应时间。Aerospike 的三个主要组件是 Aerospike 数据库服务器、Aerospike 智能客户端和 Aerospike 管理控制台。

**2。快板:**
快板是一个高性能、持久的 RDF 存储，还支持图形数据库管理系统。它是一个文档存储库，用于以 JSON-LD 格式存储、检索和管理面向文档的信息。第一个版本的 AllegroGraph 发布于 2004 年。

**长枪短炮和快板的区别:**

<center>

| 没有 | aerospoke | ALLEGROGRAPH |
| --- | --- | --- |
| 1. | 它是由 Aerospike 在 2012 年开发的。 | 它是由弗朗茨公司在 2004 年开发的。 |
| 2. | 这是一个闪存优化的内存 NoSQL 数据库。 | 这是一个高性能、持久的 RDF 存储，并额外支持图形数据库管理系统。 |
| 3. | Aerospike 的许可证是开源的。 | AllegroGraph 的许可证是商业的。 |
| 4. | Aerospike 的服务器操作系统是 Linux。 | AllegroGraph 的服务器操作系统是 linux、OS X 和 Windows。 |
| 5. | 它不支持 XML 格式。 | 它也不支持 XML 格式。 |
| 6. | 它具有用户定义的服务器端脚本功能。 | 它支持服务器端脚本，使用 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 或通用 Lisp。 |
| 7. | 支持的分区方法是分片。 | 分区可以通过联合来完成。 |
| 8. | 它不支持 SQL 查询语言。 | 它使用 SPARQL 作为查询语言。 |
| 9. | 它只支持一种复制方法:可选复制因子。 | 它支持两种复制方法:主从复制和多主复制。 |
| 10. | Aerospike 没有提供参照完整性的概念。因此，没有外键。 | 指称程序也没有提供参照完整性的概念。因此，没有外键。 |
| 11. | 它支持内存功能。 | 它不支持内存功能。 |
| 12. | 它为用户定义的映射/缩减方法提供了一个应用编程接口。 | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 |
| 13. | 它只支持操作的原子执行。 | 它支持 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 属性。 |
| 14. | 它的主要数据库模型是键值存储。 | 它的主要数据库模型是文档存储、图形数据库管理系统和 RDF 存储。 |

</center>