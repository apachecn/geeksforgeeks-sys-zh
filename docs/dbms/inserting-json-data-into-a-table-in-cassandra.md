# 将 JSON 数据插入卡珊德拉的表中

> 原文:[https://www . geesforgeks . org/insert-JSON-data-in-a-table-in-Cassandra/](https://www.geeksforgeeks.org/inserting-json-data-into-a-table-in-cassandra/)

在本文中，您将能够理解如何在 Cassandra 中将 JSON 数据插入到表中，并将借助一个示例进行讨论，然后最终总结 JSON 插入的重要性。我们一个一个来讨论。

**概述:**
插入列和列值比 cqlsh 更实用。在 JSON 中，以字符串形式插入的值，如果它们不是数字，例如 id，数据类型 uuid 作为字符串插入，但将作为 uuid 存储。为了更好地理解，首先，我们将看到使用 cqlsh 命令的插入数据，然后将讨论如何使用 JSON 格式插入数据。

**示例:**
让我们假设您有现有的键空间即 cluster1，然后首先我们将使用如下的 [CQL](https://www.geeksforgeeks.org/useful-cql-query-in-cassandra/) 命令创建一个 user_data 表。

```
use cluster1;
create table user_record
           (
           user_id uuid,
           first_name varchar,
           last_name varchar,
           company varchar,
           primary key(user_id)
           );
```

**方法-1 :**
**使用 cqlsh 命令插入–**

```
insert into user_record(user_id, first_name, last_name, company) 
values(101aa90a-4bba-211f-a4fb-00001a101cda,'Ashish','Rana','abc');

insert into user_record(user_id, first_name, last_name, company) 
values(102aa90a-4bba-211f-a4fb-00002a102cda,'Ayush','NA','abc');
```

插入后，可以使用以下 cql 命令来验证插入的数据。

```
select * from user_record;
```

**输出–**

<figure class="table">

| 用户 id | 公司 | 名字 | 姓氏 |
| --- | --- | --- | --- |
| 102 aa 90 a-4 BBA-211 f-a4fb-00002 a 102 CDA | 字母表 | 阿尤什 | 钠 |
| 101 aa 90 a-4 BBA-211 f-a4fb-00001 a 101 CDA | 字母表 | Ashish | 中国林蛙 |

**方法-2 :**
**使用 JSON 格式插入–**
要以 JSON 格式插入数据，将在 INSERT 命令中添加 JSON 关键字，如下所示。

```
 INSERT INTO cluster1.user_record JSON '{
 "user_id" : "103aa90a-4bba-211f-a4fb-00001a101cda",  
 "first_name" : "Ashish",  
 "last_name" : "Rana",
 "company" : "abc" }';
```

U 使用 JSON 格式 i 如果您没有为任何列插入任何值，那么将自动输入一个空值，如下例所示。

```
 INSERT INTO cluster1.user_record JSON '{
 "user_id" : "104aa90a-4bba-211f-a4fb-00001a101cda",  
 "first_name" : "Ashish",  
 "last_name" : "Rana" 
 }';
```

插入后，可以使用以下 cql 命令来验证插入的数据。

```
select * from user_record;
```

**输出–**

<figure class="table">

| 用户 id | 公司 | 名字 | 姓氏 |
| --- | --- | --- | --- |
| 104 aa 90 a-4 BBA-211 f-a4fb-00001 a 101 CDA | 空 | Ashish | 中国林蛙 |
| 103 aa 90 a-4 BBA-211 f-a4fb-00001 a 101 CDA | 字母表 | Ashish | 中国林蛙 |
| 102 aa 90 a-4 BBA-211 f-a4fb-00002 a 102 CDA | 字母表 | 阿尤什 | 钠 |
| 101 aa 90 a-4 BBA-211 f-a4fb-00001 a 101 CDA | 字母表 | Ashish | 中国林蛙 |

</figure>

</figure>