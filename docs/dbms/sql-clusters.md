# SQL 集群

> 原文:[https://www.geeksforgeeks.org/sql-clusters/](https://www.geeksforgeeks.org/sql-clusters/)

在本文中，我们将介绍 SQL 集群，还将介绍 SQL 集群的一些优点和缺点。我们一个一个来讨论。

[SQL 中的集群](https://www.geeksforgeeks.org/sql-queries-on-clustered-and-non-clustered-indexes/)用于将来自不同表的数据存储在相同的物理数据块中。如果经常一起查询这些表中的记录，则使用它们。通过存储相同的数据块，完全填充此类查询所需的数据库块读取次数减少，从而提高了性能。

*   每个集群存储表数据，并维护一个聚集索引来对数据进行排序。
*   群集索引中的列称为聚集键。这些决定了行在集群中的物理位置。
*   群集键通常是一个表的外键，它引用群集中另一个表的主键。

创建第一个集群。然后在群集键列上创建群集索引。创建集群关键字索引后，可以将数据输入到存储在集群中的表中。当插入行时，数据库在每个集群块中存储集群键及其关联行。

**语法:**

```
CREATE CLUSTER <Cluster Name> 
(<Column> <Data Type> 
[, <Column> <Data Type> ] . . . . . )
[<Other Options >]

```

**示例–**

```
create table branch_master 
( 
"branch_code" varchar(10) PRIMARY KEY, 
"branch_name" varchar(15)
);

```

现在，考虑上面创建的表，让我们为其创建集群。
**创建集群:**

```
create cluster branch_info
( 
"branch_code" varchar(10)
);

```

**集群优势:**

1.  磁盘输入/输出减少。
2.  对于聚集表的连接，访问时间得到了改善。
3.  由于聚集表中的所有行都使用相同的列作为公共主键，因此这产生了存储优势。

**集群的劣势:**

1.  与使用自己的索引单独存储表相比，降低了 INSERT 语句的性能。
2.  经常更新的列不适合作为群集键。