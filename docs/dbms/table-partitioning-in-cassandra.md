# 卡珊德拉中的表划分

> 原文:[https://www . geesforgeks . org/table-partitioning-in-Cassandra/](https://www.geeksforgeeks.org/table-partitioning-in-cassandra/)

在本文中，我们将介绍如何在分区的基础上访问数据，以及如何在集群中唯一地存储数据。我们一个一个来讨论。

**先决条件—** [数据分发](https://www.geeksforgeeks.org/data-distribution-in-cassandra/)

**表分区:**
在表分区中，数据可以基于分区键分布。如果您没有指定任何分区键，那么可能会丢失数据。并且很难按照要求访问数据。

**示例:**
让我们考虑一下如果你的需求中你想要查询用户数据的名字。现在，首先，您必须创建一个表，其中分区键的作用非常重要。

```
CREATE TABLE User_data_by_first_name
(
Usr_id UUID,
first_name text,
last_name text,
primary key (first_name)
);
```

让我们为上面创建的表插入一些数据。

```
Insert into User_data_by_id(Usr_id, first_name, last_name) 
values(uuid(), 'Ashish', 'A');
Insert into User_data_by_id(Usr_id, first_name, last_name) 
values(uuid(), 'Ashish', 'A');
Insert into User_data_by_id(Usr_id, first_name, last_name) 
values(uuid(), 'Ashish', 'B');
```

现在，如果您想读取数据，那么使用下面的 cqlsh 查询。

```
select * from User_data_by_id;
```

**输出:**

<center>

| 名字 | 姓氏 | Usr_id |
| Ashish | B | 8 a71a 441-ebee-48 E6-861 e-CB 097570 b09b |

</center>

在上面的示例中，如果您已经通过名字指定了分区键，那么不建议将唯一的名字指定为分区键。否则，可能无法唯一识别您的数据，如果您有多个同名条目，您的数据将会丢失。

现在，要解决这个问题，请指定 Usr_id 和 first_name 作为分区键。

```
CREATE TABLE User_data_by_first_name_modify
(
Usr_id UUID,
first_name text,
last_name text,
primary key (first_name, Usr_id)
);
```

现在，插入与您必须插入的用户名数据相同的数据。

```
Insert into User_data_by_first_name_modify(Usr_id, first_name, last_name) 
values(uuid(), 'Ashish', 'A');
Insert into User_data_by_first_name_modify(Usr_id, first_name, last_name) 
values(uuid(), 'Ashish', 'A');
Insert into User_data_by_first_name_modify(Usr_id, first_name, last_name) 
values(uuid(), 'Ashish', 'B');
```

现在，如果您将读取您的数据，那么它将被唯一识别，并且您的数据不会丢失。

```
select * from User_data_by_first_name_modify;
```

**输出:**

<center>

| 名字 | Usr_id | 姓氏 |
| Ashish | 9d 0 BD 000-d 822-41 F4-9a 0 B- ee 5 至 3f100dbf | B |
| Ashish | -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | A |
| Ashish |

</center>