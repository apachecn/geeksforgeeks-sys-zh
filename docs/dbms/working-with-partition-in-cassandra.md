# 在卡珊德拉使用分区

> 原文:[https://www . geeksforgeeks . org/与卡珊德拉分区一起工作/](https://www.geeksforgeeks.org/working-with-partition-in-cassandra/)

在本文中，我们将介绍如何根据我们的需求进行分区，以及如何使用分区键将数据处理到表中。我们一个一个来讨论。

先决条件— [数据建模概述](https://www.geeksforgeeks.org/overview-of-data-modeling-in-apache-cassandra/)

**数据建模的分区:**
分区是一个小的行集合，在这里你可以说一个表被分割成该表的一个小的子集，该子集共享基于分区的相同分区键。

让我们考虑一个例子，您希望在其中存储用户登录信息，如用户名、电子邮件、密码和电子邮件标识等。

<center>

| 列名 | 数据类型 |
| 用户名 | 文本 |
| Usr_Email | 文本 |
| Usr_password | 文本 |
| Usr_ID | UUID |

</center>

现在，您将看到如何根据用户信息访问来决定分区键，或者您可以说您希望以何种顺序对数据进行分区。让我们为这些特定的需求编写 cqlsh 查询。

首先，使用下面的 cqlsh 查询创建键空间，如下所示。

```
CREATE KEYSPACE User_Info 
WITH 
REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 2 };
```

要使用上面创建的键空间，请使用以下 cqlsh 命令。

```
user User_Info;
```

在这里，您将看到如何基于 Usr_Info_by_email 表创建分区。我们一个一个来讨论。

```
CREATE TABLE Usr_Info_by_email 
(
Usr_Name text, 
Usr_email text, 
Usr_password text, 
Usr_ID UUID, PRIMARY KEY(Usr_email)
);
```

在 Cassandra 中，创建表只是为了处理查询，并且取决于您的应用程序用例。在查询的基础上，根据应用程序的需要定义表格。

现在，要向表中插入数据，请使用以下 cqlsh 查询。

```
Insert into Usr_Info_by_email (Usr_Name, Usr_email, Usr_password, Usr_ID)
values ('Ashish', 'a@gmail.com', '123', uuid());
Insert into Usr_Info_by_email (Usr_Name, Usr_email, Usr_password, Usr_ID) 
values ('Aayush', 'ay@gmail.com', '124', uuid());
Insert into Usr_Info_by_email (Usr_Name, Usr_email, Usr_password, Usr_ID) 
values ('Ashish', 'as@gmail.com', '123', uuid());
Insert into Usr_Info_by_email (Usr_Name, Usr_email, Usr_password, Usr_ID) 
values ('Harsh', 'h@gmail.com', '125', uuid());
```

**输出:**

```
cassandra@cqlsh:user_data> select * from usr_info_by_email;

usr_email    | usr_id                               | usr_name | usr_password
--------------+--------------------------------------+----------+--------------
 h@gmail.com | fa91d89e-a401-4f4e-93b4-2b6282af75e1 |    Harsh |          125
ay@gmail.com | a27c955f-ddc1-4134-a1fa-0f65fd175ce7 |   Aayush |          124
 a@gmail.com | 9982a5a9-14ff-4caa-a6d2-8d6790853e8c |   Ashish |          123
as@gmail.com | aaafc38b-7184-4f8e-a325-b43fedd91828 |   Ashish |          123
(4 rows)
```

在这里，您可以在上面的示例中清楚地看到如何基于电子邮件访问和划分您的数据**。**