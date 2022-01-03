# 更新卡珊德拉的栏目

> 原文:[https://www . geesforgeks . org/updating-columns-in-Cassandra/](https://www.geeksforgeeks.org/updating-columns-in-cassandra/)

在本文中，我们将讨论如何更新现有的列，如何在 [Cassandra](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/) 中添加新列或删除列等。

**更新一列**

在 Cassandra 中，通过执行 ALTER 语句来修改列。使用 ALTER table 语句可以更改列的类型、添加新列、删除列、重命名现有列，如下所示:

```
ALTER TABLE [keyspace_name.] table_name 
[ALTER column_name TYPE cql_type]
[ADD (column_definition_list)]
[DROP column_list | COMPACT STORAGE ]
[RENAME column_name TO column_name]
[WITH table_properties];

```

现在，如果您想更改具有主键的列名。例如:在 User_Data 现有表中，如果要将列名从 id 更改为 user_id，则可以运行 Rename 命令。

```
CREATE TABLE app_data.user_data (
    id UUID PRIMARY KEY,
    address text,
    name text
);

cassandra@cqlsh:app_data> 
select * from User_Data;

 id | address | name
----+---------+------

```

现在，要更改列名，您可以执行下面给出的 CQL 查询。

```
cassandra@cqlsh:app_data> 
Alter table User_data RENAME id TO User_id;

```

现在，要验证结果列是否成功更改，您可以执行以下 CQL 查询。

```
cassandra@cqlsh:app_data> describe User_data;

CREATE TABLE app_data.user_data (
    user_id uuid PRIMARY KEY,
    address text,
    name text
) WITH bloom_filter_fp_chance = 0.01
    AND caching = {'keys': 'ALL', 
                   'rows_per_partition': 'NONE'}
    AND comment = ''
    AND compaction = 
{
'class': 'org.apache.cassandra
          .db.compaction.SizeTieredCompactionStrategy', 
'max_threshold': '32', 'min_threshold': '4'
}
    AND compression = 
{
'chunk_length_in_kb': '64', 
'class': 'org.apache.cassandra
         .io.compress.LZ4Compressor'
}
    AND crc_check_chance = 1.0
    AND dclocal_read_repair_chance = 0.1
    AND default_time_to_live = 0
    AND gc_grace_seconds = 864000
    AND max_index_interval = 2048
    AND memtable_flush_period_in_ms = 0
    AND min_index_interval = 128
    AND read_repair_chance = 0.0
    AND speculative_retry = '99PERCENTILE';

```

现在，要查看表的输出，您可以执行以下 CQL 查询。

```
cassandra@cqlsh:app_data> 
SELECT * FROM user_data;

 user_id | address | name
---------+---------+------

(0 rows)

```