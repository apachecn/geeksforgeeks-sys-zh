# 卡珊德拉 SET 集合的二级索引

> 原文:[https://www . geesforgeks . org/secondary-indexes-on-set-collection-in-Cassandra/](https://www.geeksforgeeks.org/secondary-indexes-on-set-collection-in-cassandra/)

在本文中，我们将讨论 Cassandra 中关于 SET 集合的二级索引的概述，然后将实现该练习，并看看它实际上是如何工作的，最后将总结二级索引对 SET 集合的重要性。我们一个一个来讨论。

**先决条件–**

*   [阿帕奇卡珊德拉中的索引概念](https://www.geeksforgeeks.org/concept-of-indexing-in-apache-cassandra/)
*   [Apache Cassandra 中的采集数据类型](https://www.geeksforgeeks.org/collection-data-type-in-apache-cassandra/)

**概述:**
在卡珊德拉中对 SET Collection 创建二级索引非常有用。因此，这里您将看到在集合上创建索引的真实用例，因为它使得搜索和查询数据非常高效和快速。因此，如果您想要基于关键字进行搜索，那么在搜索和查询数据时，您可以对集合数据类型中的特定关键字使用 CONTAINS 关键字。让我们借助例子来理解整个概念。

**语法:**
在这里，您将看到如何在集合上创建索引的语法部分。您可以使用下面给出的命令，如下所示。

```
CREATE INDEX ON <table_name>(<collection_column>)
```

在这里，您将看到 WHERE 子句部分的语法，其中您将使用 CONTAINS 关键字来搜索 SET 集合中的特定值。

```
WHERE <collection_column> CONTAINS <value>
```

**示例–**
让我们假设您有现有的键空间，即 cluster1，然后首先使用如下的[【CQL】](https://www.geeksforgeeks.org/useful-cql-query-in-cassandra/)命令创建一个 user_data 表。

**步骤-1:** **创建表-用户 _ 数据–**

```
use cluster1;
create table user_data
           (
           user_id varchar,
           user_first_name varchar,
           user_last_name varchar,
           company varchar,
           user_tags set<varchar>,
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
values('Ashish01','Ashish','Rana','abc',{'Java'});

insert into user_data(user_id, user_first_name, user_last_name, company, user_tags) 
values('Ashish02','Ayush','NA','abc',{'Python'});

insert into user_data(user_id, user_first_name, user_last_name, company, user_tags) 
values('Ashish03','shivang','NA','abc',{'python'});

insert into user_data(user_id, user_first_name, user_last_name, company, user_tags) 
values('Ashish04','Bhagyesh','NA','abc',{'c++'});
```

**第 4 步:验证和读取数据–**

```
select * from user_data;
```

**第 5 步:输出–**

<figure class="table">

| 用户 id | 公司 | 用户名 | 用户 _ 姓氏 | 用户标签 |
| --- | --- | --- | --- | --- |
| Ashish04 | 字母表 | 巴格耶什 | 钠 | {'c++'} |
| Ashish03 | 字母表 | 希万 | 钠 | {'python'} |
| Ashish02 | 字母表 | 阿尤什 | 钠 | {'Python'} |
| Ashish01 | 字母表 | Ashish | 中国林蛙 | {'Java'} |

**第 6 步:基于特定关键词的搜索–**

```
select * from user_data where user_tags CONTAINS 'Java';
```

**第 7 步:输出–**

<figure class="table">

| 用户 id | 公司 | 用户名 | 用户 _ 姓氏 | 用户标签 |
| --- | --- | --- | --- | --- |
| Ashish01 | 字母表 | Ashish | 中国林蛙 | {'Java'} |

</figure>

</figure>