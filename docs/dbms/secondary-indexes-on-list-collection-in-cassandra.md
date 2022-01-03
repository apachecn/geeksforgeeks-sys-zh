# 卡珊德拉列表集合的二级索引

> 原文:[https://www . geesforgeks . org/secondary-indexes-on-list-collection-in-Cassandra/](https://www.geeksforgeeks.org/secondary-indexes-on-list-collection-in-cassandra/)

在本文中，我们将讨论 Cassandra 中 LIST Collection 上的二级索引的概述，然后将实现该练习，并看看它实际上是如何工作的，最后将总结 LIST Collection 上的二级索引的重要性。我们一个一个来讨论。

**先决条件–**

*   [阿帕奇卡珊德拉中的索引概念](https://www.geeksforgeeks.org/concept-of-indexing-in-apache-cassandra/)
*   [Apache Cassandra 中的采集数据类型](https://www.geeksforgeeks.org/collection-data-type-in-apache-cassandra/)

**概述:**
在 Cassandra 的 LIST Collection 上创建二级索引非常有用。因此，这里您将看到在集合上创建索引的真实用例，因为它使得搜索和查询数据非常高效和快速。因此，如果您想要基于关键字进行搜索，那么在搜索和查询数据时，您可以对 LIST 集合数据类型中的特定关键字使用 CONTAINS 关键字。让我们借助例子来理解整个概念。

**语法:**
在这里，您将看到如何在集合上创建索引的语法部分。您可以使用下面给出的命令，如下所示。

```
CREATE INDEX ON <table_name>(<collection_column>)
```

在这里，您将看到 WHERE 子句部分的语法，其中您将使用 CONTAINS 关键字来搜索 LIST 集合中的特定值。

```
WHERE <collection_column> CONTAINS <value>
```

**示例:**
让我们假设您有现有的键空间，即 cluster1，然后首先我们将使用 CQL 命令创建一个 user_data 表，如下所示。

**步骤-1 :** **创建表-用户 _ 数据–**

```
use cluster1;
create table user_data
           (
           user_id varchar,
           user_first_name varchar,
           user_last_name varchar,
           company varchar,
           user_tags list<varchar>,
           primary key(user_id)
           );
```

**步骤 2:在 user_tags 上创建索引–**

```
CREATE INDEX ON user_data(user_tags);
```

**步骤 3:插入数据–**

```
insert into user_data(user_id, user_first_name, user_last_name, company, user_tags)
values('Ashish01','Ashish','Rana','abc',['Java','python', 'c++']);

insert into user_data(user_id, user_first_name, user_last_name, company, user_tags)
values('Ashish02','Ayush','NA','abc',['Python','java']);

insert into user_data(user_id, user_first_name, user_last_name, company, user_tags)  
values('Ashish03','Ayushi','NA','abc',['Python','c++','Java']);
```

**第 4 步:验证和读取数据–**

```
select * from user_data;
```

**第 5 步:输出–**

<figure class="table">

| 用户 id | 公司 | 用户名 | 用户 _ 姓氏 | 用户标签 |
| --- | --- | --- | --- | --- |
| Ashish03 | 字母表 | Ayushi | 钠 | [‘Python’、‘c++’、‘Java’ |
| Ashish02 | 字母表 | 阿尤什 | 钠 | ['Python '，' java ' |
| Ashish01 | 字母表 | Ashish | 中国林蛙 | ['Java '，' python '，' c++ ' |

**第 6 步:基于特定关键词的搜索–**

```
select * from user_data where user_tags CONTAINS 'Java';
```

**第 7 步:输出–**

<figure class="table">

| 用户 id | 公司 | 用户名 | 用户 _ 姓氏 | 用户标签 |
| --- | --- | --- | --- | --- |
| Ashish03 | 字母表 | Ayushi | 钠 | [‘Python’、‘c++’、‘Java’ |
| Ashish01 | 字母表 | Ashish | 中国林蛙 | ['Java '，' python '，' c++ ' |

</figure>

</figure>