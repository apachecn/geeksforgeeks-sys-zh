# Apache Cassandra 中的索引概念

> 原文:[https://www . geesforgeks . org/概念索引-in-apache-cassandra/](https://www.geeksforgeeks.org/concept-of-indexing-in-apache-cassandra/)

先决条件–[Apache Cassandra 简介](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)
**索引:**
因为我们可以使用具有分区键的属性来访问数据。例如，如果 Emp_id 是 Employee 表的列名，并且它是该表的分区键，那么我们可以借助分区键来过滤或搜索数据。在这种情况下，我们可以使用 WHERE 子句在属性上定义条件并搜索数据。
但是假设存在一个不是该表的分区键的列，并且我们想要使用 WHERE 子句过滤、搜索或访问数据，那么查询将不会被执行，并且会给出一个错误。

因此，在这种情况下，要使用分区键以外的属性来访问数据，以便快速有效地查找符合给定条件的数据，那么我们需要定义索引。它可以用于各种目的，如集合、静态列、集合列以及除计数器列之外的任何其他列。

**何时使用索引:**

1.  内置索引是具有多行且行包含索引值的表上的最佳选项。
2.  在特定的列中，哪一列具有更多的唯一值，在这种情况下，我们可以使用索引。
3.  由于多种原因，如列有更多条目，表会有更多开销，在这种情况下，我们可以使用索引。
4.  为了查询和维护索引，我们可以使用索引，在这种情况下，索引总是一个很好的选择。

**示例:**
假设您有一个板球比赛参赛表，在数百场比赛中有 100 万个选手的参赛项目，并且希望通过比赛次数来查找选手的排名。许多玩家的等级将在比赛年份共享相同的列值。match_year 列是一个很好的索引选项。

**创建索引的语法:**

```
CREATE INDEX [ IF NOT EXISTS ] index_name
  ON [keyspace_name.]table_name
  ([ ( KEYS | FULL ) ] column_name) 
  (ENTRIES column_name); 
```

**示例:**
创建表时使用了 keyspace1 作为键空间，Task 作为表名。让我们看看。

```
CREATE TABLE keyspace1.Task 
(
   Task_id text,
   Task_name text,
   Task_time timestamp,
   T_location text,
   PRIMARY KEY (Task_id, Task_name)
); 
```

由于 Cassandra 是一个分布式、分散的数据库，数据是按分区键组织的，一般情况下，WHERE 子句查询需要包含一个分区键。

**示例:**

```
SELECT * 
FROM Task 
WHERE Task_id = ‘T210’; 
```

这个查询可以正常工作。

```
SELECT * 
FROM Task 
WHERE Task_id = ‘T210’ AND Task_name; ‘set alarm’; 
```

这个查询可以正常工作。

**注:**
上表中 Task_id 和 Task_name 列是主键的一部分。

```
SELECT * FROM Task WHERE Task_time= ‘2019-09-30 15:02:56’; 
```

这个查询不起作用，因为我们可以看到 Task_time 不是分区键的一部分。

错误:错误请求:带有相等运算符的按列子句中不存在索引列。

通过在群集列上创建索引来解决此类错误。定义一个具有复合分区键的表，然后在群集列上创建索引。

```
CREATE TABLE keyspace1.Task (
   Task_id text,
   Task_name text,
   Task_time timestamp,
   T_location text,
  PRIMARY KEY ((Task_id, Task_name), Task_time) 
);

CREATE INDEX ON keyspace1.Task(Task_time); 
```

```
SELECT * 
FROM Task 
WHERE Task_time= ‘2019-09-30 15:02:56’; 
```

现在这个查询可以工作了:

**注意:**
通过创建索引，使得创建二级索引并不意味着它会提高 Cassandra 中的查询速度。

辅助索引的一个重要优点是有助于访问数据，这可以使引用主列和聚类列之外的列中的值的 WHERE 子句能够运行。

我们有更好的选择来提高 Cassandra 中的查询速度，那就是专门为查询创建一个表。
我们再来看一个例子。在本例中，Student_record 是表名，keyspace1 是键空间名。

```
CREATE TABLE Student_record 
(
  Stu_state text,
  Stu_zip text,
  Stu_address text,
  PRIMARY KEY(Stu_state, Stu_zip)
 ); 
```

在此表中 **Stu_state** 和 **Stu_zip** 可能是相同的，因此，为了在表中定义唯一的记录，我们可以添加 **Stu_id** 作为唯一定义该记录的主键。

现在我们可以使用 CQL 的 ALTER 命令对现有的表进行修改。

```
ALTER TABLE Student_record ADD Stu_id int PRIMARY KEY; 
```

**输出:**

![](img/57bca709585f33cc9fc32eb198143228.png)

<center>**Table :** Student_record</center>

为了检查卡珊德拉中的表的描述，使用了下面给出的 CQL 查询。
描述表 Student _ record

```
SELECT * 
FROM Student_record 
WHERE Stu_id = '107'; 
```

**输出:**

![](img/46aa5bca142a4b7d01b6144e3c1e5c48.png)

<center>**Table :** Output</center>

**在 Cassandra 中创建复合分区键:**
复合分区键被定义为这样的键，其中一个分区键有多个列，那么它被称为复合分区键。

**示例:**

```
CREATE TABLE Registration (
  Name text,
  Date timestamp,
  Email text, 
  Query text,
  PRIMARY KEY((Name, Date), Email) WITH CLUSTERING ORDER BY(Date DESC); 
```

```
SELECT * 
FROM Registration LIMIT 2; 
```

**注意:**
在我们创建索引时，Cassandra 中的每一行都有一个行键。在 Cassandra 中有反规范化的数据是很常见的。在 Cassandra 中，二级索引使查询运行得更快是错误的。括号用于指定复合分区键。