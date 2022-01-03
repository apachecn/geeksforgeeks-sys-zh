# 卡珊德拉中的物化视图

> 原文:[https://www . geesforgeks . org/物化视图 in-cassandra/](https://www.geeksforgeeks.org/materialized-views-in-cassandra/)

在本文中，我们将讨论物化视图的概述及其重要性。在[中，卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)物化视图发挥了重要作用，使得物化视图适合高基数数据。我们还讨论了如何创建、更改和删除物化视图。让我们一个一个来讨论。

**物化视图:**
物化视图像基表一样工作，定义为可以像基表一样查询的 CQL 查询。物化视图对于数据的去规范化非常重要，卡珊德拉查询语言也有利于高基数和高性能。让我们用一个例子来理解。

现在，首先我们要定义基表(基表–User _ information)，User1 是键空间名称。User_name 是分区键，我们将通过它以排序的方式获得结果。物化视图将使用相同的主键，并且由于在物化视图中定义主键的限制，可以在物化视图中为主键再添加一列来获取用户信息。用户名、用户电子邮件、用户密码和用户地址是基表的列。让我们来看看。

要创建用户信息表，请使用以下 CQL 查询。

```
CREATE TABLE User1.User_information (          
User_name text PRIMARY KEY,
User_email text,
User_password text,
User_address text
);
```

现在，让我们考虑一下，如果我们想在用户电子邮件的帮助下找到用户信息，那么我们需要创建一个新的表，通过将电子邮件定义为分区键，我们可以获得用户信息，但是我们有另一个更好的选项，称为**物化视图**。

因此，现在让我们创建上面给定表的物化表，也称为基表。要创建实体化视图，请使用以下 CQL 查询。

**语法:**创建实体化视图:

```
CREATE MATERIALIZED VIEW [IF NOT EXISTS] [keyspace_name.] view_name
AS SELECT column_list
FROM [keyspace_name.] base_table_name
WHERE column_name IS NOT NULL 
      [AND column_name IS NOT NULL ...]  
      [AND relation...] 
PRIMARY KEY ( column_list )
[WITH [table_properties]  
[AND CLUSTERING ORDER BY (cluster_column_name order_option )]]
```

[语法来源](https://docs.datastax.com/en/cql/3.3/cql/cql_reference/cqlCreateMaterializedView.html)

**示例:**

```
CREATE MATERIALIZED VIEW User1.Users_by_User_email AS
SELECT User_email, User_password, User_address
FROM User_information
WHERE User_name IS NOT NULL AND User_email IS NOT NULL
PRIMARY KEY (User_email, User_name ); 
```

要执行操作以便从实体化视图中读取数据，请使用以下 CQL 查询。

```
SELECT * 
FROM Users_by_User_email 
WHERE User_email = ? ;
```

在实体化视图中，必须遵循以下限制。

1.  在物化视图中，基表中的主列必须包含在物化视图表中，以确保物化视图的每一行都与基表相对应。
2.  仅在实体化视图中，我们可以再添加一个不是基表中主列的列。

让我们举个例子来理解这个概念。

```
CREATE TABLE base_table
(
Key1 int,
Col1 int,
Col2 int,
Col3 int,
Col4 text,
PRIMARY KEY (key1, Col1, Col2)
); 
```

以上给定基表的物化视图是**允许的**。让我们看看。

```
Case-1:
CREATE MATERIALIZED VIEW test_MV1 AS 
SELECT * 
FROM test_MV1 
WHERE key1 IS NOT NULL 
      AND Col1 IS NOT NULL 
      AND Col2 IS NOT NULL 
PRIMARY KEY (Col1, key1, Col2);

Case-2:
CREATE MATERIALIZED VIEW test_MV2 AS 
SELECT * 
FROM test_MV2 
WHERE key1 IS NOT NULL 
      AND Col1 IS NOT NULL 
      AND Col2 IS NOT NULL 
      AND Col3 IS NOT NULL 
PRIMARY KEY (Col3, key1, Col1, Col2); 
```

上述给定基表的实体化视图是不允许的。让我们看看。

```
Case-1:
CREATE MATERIALIZED VIEW test_MV1 AS 
SELECT * 
FROM test_MV2 
WHERE key1 IS NOT NULL 
      AND Col1 IS NOT NULL 
      AND Col2 IS NOT NULL 
      AND Col3 IS NOT NULL 
PRIMARY KEY (Col3, Col4, key1, Col1, Col2);  
 // * ERROR : it will give an error that Col3 
         and Col4 is not primary key in base table.

Case-2:
CREATE MATERIALIZED VIEW test_MV1 AS 
SELECT * 
FROM test_MV2 
WHERE Col1 IS NOT NULL 
      AND Col2 IS NOT NULL 
PRIMARY KEY (Col1, Col2);
// * ERROR : it will give an error that key1 is primary key 
    in base table that must contain in materialized view. 
```

**改变物化视图:**
下面给出的是使用 Alter 命令改变物化视图基本属性的 CQL 查询。让我们来看看。

**语法:**

```
ALTER MATERIALIZED VIEW [keyspace_name.] view_name 
[WITH table_options] 
```

**删除物化视图:**
我们可以使用 Drop 命令删除物化视图表，对基表不会有影响。

**语法:**

```
DROP MATERIALIZED VIEW [IF EXISTS] [keyspace_name.] view_name 
```

例如，要删除实体化视图，请使用以下 CQL 查询。

```
DROP MATERIALIZED VIEW User1.Users_by_User_email ; 
```