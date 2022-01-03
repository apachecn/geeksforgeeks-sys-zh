# 弱化和 VoltDB 的区别

> 原文:[https://www . geeksforgeeks . org/wea viate 和-voltdb 之间的差异/](https://www.geeksforgeeks.org/difference-between-weaviate-and-voltdb/)

**1。**
weavete 是一个基于开源 GraphQL 的智能图，其核心特征是:语义搜索、自动分类和知识表示。主[数据库](https://www.geeksforgeeks.org/what-is-database/)模型是搜索引擎，次数据库模型是图形[数据库管理系统](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)。它允许我们的数据以基于 GraphQL 查询语言的大型图形格式表示。它的搜索图基于一种叫做 Contextionary 的图嵌入机制。

**2。VoltDB :**
VoltDB 是分布式内存中的 NewSQL [关系数据库管理系统](https://www.geeksforgeeks.org/rdbms-full-form/)和一个 [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) 兼容的关系数据库管理系统，使用无共享架构。这个数据库是由迈克尔·斯通布雷克、萨姆·马登和丹尼尔·阿巴迪设计的。最初，VoltDB 数据库包括集群吞吐量和延迟以及 CPU 和内存使用情况的图表。VoltDB 基于 H-Store，随着多核服务器上每 CPU 内核数量的增加而扩展。

**威瓦特和 VoltDB 的区别:**

<center>

| 没有。 | 变弱 | VoltDB |
| one | SeMI Technologies B.V .开发，最初于 2017 年发布，目前于 2020 年 1 月发布。 | 由 VoltDB Inc .开发，最初于 2010 年发布，目前于 2019 年 4 月发布。 |
| Two | 它的主要数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。 | 它的主要数据库模型是关系数据库管理系统。 |
| three | Weaviate 没有这样的服务器操作系统。 | VoltDB 的服务器操作系统是 Linux，OS X。 |
| four | Weaviate 支持 GraphQL 查询语言和 RESTful HTTP/JSON API。 | VoltDB 支持 Java API、JDBC、RESTful HTTP/JSON API。 |
| five | 《武器》中交易概念的缺失。 | VoltDB 的事务概念是 ACID(原子性、一致性、隔离性和持久性)。 |
| six | 是的，有复制方法。 | VoltDB 的复制方式有主从复制和主从复制。 |
| seven | XAP 的分区方法是分片。 | 它不支持分片分区方法。 |
| eight | 在 Weaviate 中没有这种受支持的编程语言。 | 它支持 C#、C++、Erlang、Go、Java、JavaScript、PHP、Python 等编程语言。 |
| nine | 它有最终一致性的概念。 | 它没有一致性概念。 |
| Ten | 《武器是走》的实现语言。 | VoltDB 的实现语言是 Java，C++。 |

</center>