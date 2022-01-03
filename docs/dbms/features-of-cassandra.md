# 卡珊德拉的特点

> 原文:[https://www.geeksforgeeks.org/features-of-cassandra/](https://www.geeksforgeeks.org/features-of-cassandra/)

[Apache Cassandra](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/) 是一个开源的、用户可用的、分布式的、 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库管理系统，旨在跨多台服务器处理大量数据。它提供了零故障点。Cassandra 为跨多个数据中心的集群提供了大量支持。

卡珊德拉有很多特点。以下是下面描述的一些功能:

1.  **分布式:**
    集群中的每个节点都有相同的角色。不存在失败的问题&数据集分布在整个集群中，但是有一个问题是主节点不在每个节点中来支持服务请求。
2.  **支持复制&多数据中心复制:**
    复制因子拥有卡珊德拉最好的配置。Cassandra 旨在拥有一个分布式系统，用于跨多个数据中心部署大量节点以及其他关键功能。
3.  **可扩展性:**
    设计为 r/w 吞吐量，随着新机器的增加而逐渐增加，不会中断其他应用。
4.  **容错:**
    数据自动存储&复制容错。如果一个节点出现故障，它将立即被替换。
5.  **MapReduce 支持:**
    支持 Hadoop 集成，支持 MapReduce。阿帕奇蜂巢&也支持阿帕奇猪。
6.  **查询语言:**
    卡珊德拉推出了 CQL(卡珊德拉查询语言)。这是一个访问卡珊德拉的简单界面。

[**【卡珊德拉查询语言(CQL)**](https://www.geeksforgeeks.org/additional-functions-in-cql-cassandra-query-language/) **:**
CQL 有简单的卡珊德拉访问界面，也是传统 SQL 的替代。CQL 增加了一个抽象层来隐藏结构的实现&也为集合提供了原生语法。

例如，请遵循给定的示例，该示例显示了如何在 CQL 3.0 中创建包含列族的键空间-

```
CREATE KEYSPACE MyKeySpace
WITH REPLICATION = { 'class' : 'SimpleStrategy', 
                     'replication_factor' : 3 };

USE MyKeySpace;

CREATE COLUMNFAMILY MyColumns (id text, Last text, 
                               First text, PRIMARY KEY(id));

INSERT INTO MyColumns (id, Last, First) 
VALUES ('1', 'Doe', 'John'); 
```

查询:

```
SELECT * FROM MyColumns; 
```

它给出了:

```
id | First | Last
----+-------+------
1 | Ratul | Sarkar 
```

(1 行)

**关于卡珊德拉的一些事实如下:**

*   在卡珊德拉版本更新之前，直到卡珊德拉 1.0，卡珊德拉不是行级一致的，这意味着插入和更新表。它可能影响几乎同时处理的同一行，也可能以不一致的方式影响非键列。
    Cassandra 1.1 使用行级隔离解决了这个问题。
*   被称为墓碑(来源互联网)的标记的删除也会导致性能下降到严重的后果水平。
*   Cassandra，本质上是键值和有组织的表格数据库管理系统的混合。可以在运行时创建、删除和更改表，而不会阻塞更新和查询。
*   称为表的列族代表一个关系数据库管理系统。每一行都由一行明确标识&关键字、名称、值、时间戳等。卡珊德拉的一张桌子是一张受钥匙监控的混乱的多维地图。更多的应用由超级列族指定。