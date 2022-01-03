# 阿达巴斯和 AgensGraph 的区别

> 原文:[https://www . geeksforgeeks . org/adabas 和-agensgraph 之间的差异/](https://www.geeksforgeeks.org/difference-between-adabas-and-agensgraph/)

**1。阿达巴斯:**
阿达巴斯代表适应性数据库系统。它是由软件公司开发的，运行在 IBM 大型机上。它于 1971 年推出。这是一个面向大型机和 Linux/Unix/Windows 环境的 [OLTP-DBMS](https://www.geeksforgeeks.org/on-line-transaction-processing-oltp-system-in-dbms/) 。Adabas 是一种企业数据库管理系统(DBMS)，旨在实现可靠性、高性能、可扩展性和低总拥有成本。

**2。AgensGraph :**
AgensGraph 是一个企业图形数据库管理系统，它存储和管理各种类型的数据，包括遗留系统中的关系数据。AgensGraph 是一个基于 [PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) RDBMS 的多模型数据库，同时支持关系和图形数据模型。AgensGraph 支持关系模型中的索引类型，包括 BTree、Hash、Gist、Gin。它符合 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 标准，并提供基于触发器的逻辑复制以及高可用性工具，以确保您的稳定性。

**阿达巴斯和 AgensGraph 的区别:**

<center>

| 没有 | 阿达玛 | AGENSGRAPH |
| --- | --- | --- |
| 1. | 它是由软件公司在 1971 年开发的。 | 它是由比特宁全球公司于 2016 年开发的。 |
| 2. | 它是一个面向大型机和 Linux/Unix/Windows 环境的 OLTP-DBMS。 | 它是一个支持关系和图形数据模型的多模型数据库，建立在 PostgreSQL 之上。 |
| 3. | 阿达巴斯是用自然语言写的。 | AgensGraph 是用 [C](https://www.geeksforgeeks.org/c-programming-language/) 语言编写的。 |
| 4. | Adabas 的服务器操作系统有 BS2000、Linux、Unix、Windows、z/OS 和 z/VSE。 | AgensGraph 的服务器操作系统是 linux、OS X 和 Windows。 |
| 5. | 它不支持 XML 格式。 | 它也不支持 XML 格式。 |
| 6. | 服务器端脚本是用自然语言完成的。 | 它还支持服务器端脚本。 |
| 7. | 它支持分区方法。 | 没有分区方法，但是可以使用表继承来实现。 |
| 8. | 它支持带有附加产品 Adabas SQL Gateway 的 SQL 查询语言。 | 还支持 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 查询语言。 |
| 9. | 它支持使用附加产品事件复制器进行复制。 | 它只支持一种复制方法:主从复制。 |
| 10. | Adabas 没有提供参照完整性的概念。因此，没有外键。 | AgensGraph 提供了参照完整性的概念。因此，有外键。 |
| 11. | 阿达巴斯的许可证是商业的。 | AgensGraph 的许可证是开源的。 |
| 12. | Adabas 的主要数据库模型是多值数据库管理系统。 | AgensGraph 的主要数据库模型是图形数据库管理系统和[关系数据库管理系统](https://www.geeksforgeeks.org/rdbms-architecture/)。 |

</center>