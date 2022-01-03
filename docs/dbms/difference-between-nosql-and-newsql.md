# NoSQL 和纽思强的区别

> 原文:[https://www . geesforgeks . org/nosql 和-newsql 之间的区别/](https://www.geeksforgeeks.org/difference-between-nosql-and-newsql/)

**1。**[**【NoSQL】**](https://www.geeksforgeeks.org/introduction-to-nosql/)**:**
术语 NoSQL 将数据库归类为描述性的“无 SQL”。NoSQL 是一个全面的数据库类别，旨在克服 SQL 数据库产生的问题。它们被称为无模式文档，以文档、图形、键值和非有序的方式存储数据。

**NoSQL 优势:**

*   当需要动态行为时，它们比传统系统扩展得更好。
*   这些系统针对非关系数据进行了更好的优化。
*   允许执行写入时架构操作。

**NoSQL 的劣势:**

*   与 NoSQL 建立的系统基本上是非交易性的。
*   创建的数据量巨大，不提供任何传统的数据库功能。
*   当同时执行多个事务时，它不遵循一致性。

**2。**[**NewSQL**](https://www.geeksforgeeks.org/introduction-of-newsql-set-2/)**:**
NewSQL 这个术语对数据库进行了分类，这些数据库是关系模型与数据类型的可扩展性、灵活性的进步的结合。这些数据库侧重于 NoSQL 没有的功能，这提供了强有力的一致性保证。这包括两层数据一层是关系数据，一层是键值存储。

**NewSQL 的优势:**

*   它为传统的关系数据库引入了新的实现。
*   它集合了 SQL 和 NoSQL 的优点。
*   很容易在用户的类型和需求之间进行迁移。

**NewSQL 的缺点:**

*   它们提供了对丰富的传统系统的部分访问。
*   超过数据量可能会导致内存架构出现问题。
*   这种数据库的核心基础是关系系统，这使得它很难理解。

**NoSQL 和 NewSQL 的区别:**

<figure class="table">

| S.No | NoSQL | NewSQL |
| --- | --- | --- |
| 1. | NoSQL 是一个没有模式的数据库。 | NewSQL 是固定模式的，也是无模式的数据库。 |
| 2. | 它是可横向扩展的。 | 它是可横向扩展的。 |
| 3. | 它具有自动高可用性。 | 它拥有内置的高可用性。 |
| 4. | 它支持云、磁盘和缓存存储。 | 它完全支持云、磁盘和缓存存储。 |
| 5. | 提升 [CAP](https://www.geeksforgeeks.org/the-cap-theorem-in-dbms/) 属性。 | 它提升了[酸性](https://www.geeksforgeeks.org/acid-properties-in-dbms/)属性。 |
| 6. | 不支持联机事务处理。 | [完全支持在线交易处理](https://www.geeksforgeeks.org/on-line-transaction-processing-oltp-system-in-dbms/)。 |
| 7. | 存在安全性较低的问题。 | 有适度的安全顾虑。 |
| 8. | 用例:[大数据](https://www.geeksforgeeks.org/what-is-big-data/)、社交网络应用和 [IOT](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/) 。 | 用例:电子商务、电信行业和游戏。 |
| 9. | 例如:DynamoDB、MongoDB、RaveenDB 等。 | 例如:VoltDB、CockroachDB、NuoDB 等。 |

</figure>