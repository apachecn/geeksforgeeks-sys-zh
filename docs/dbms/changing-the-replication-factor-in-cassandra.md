# 改变卡珊德拉的复制因子

> 原文:[https://www . geeksforgeeks . org/changing-replication-in-Cassandra/](https://www.geeksforgeeks.org/changing-the-replication-factor-in-cassandra/)

在本文中，我们将讨论如何在简单复制策略和网络拓扑复制策略中改变复制因素。为了更好的理解，请参考卡珊德拉文章中的[复制策略。](https://www.geeksforgeeks.org/replication-strategy-in-cassandra/)

**更改密钥空间:**
要更改复制因子，您可以执行“更改密钥空间”语句，在该语句中，您可以更改简单策略和网络拓扑策略的复制因子。

例如:
**更改 SimpleStrategy 的复制因子:**
如果要更改键空间的复制因子，可以通过执行 ALTER KEYSPACE 命令来实现，该命令具有以下语法:

```
Syntax:

ALTER KEYSPACE "KeySpace Name"
WITH replication = {'class': 'Strategy name', 
                    'replication_factor' : 'No.Of replicas'}; 
```

首先，您可以创建任何键空间，然后可以更改复制因子，或者如果您有现有的键空间，则可以用同样的方式进行更改。

示例:创建 WFH 键空间。

```
CREATE KEYSPACE WFH WITH replication =
           {
            'class': 'SimpleStrategy',
           'replication_factor': '2'
               }
            AND durable_writes = true;

```

现在，您可以在这里更改相同的复制因子。

```
cassandra@cqlsh> ALTER KEYSPACE WFH
   ...            WITH replication =
   ...            {
   ...             'class': 'SimpleStrategy',
   ...            'replication_factor': '3'
   ...                }
   ...             AND durable_writes = true;

```

现在，为了验证结果，您可以执行以下 CQL 查询。

```
cassandra@cqlsh> describe WFH;

```

**输出:**

```
CREATE KEYSPACE wfh 
WITH 
replication = 
{
'class': 'SimpleStrategy', 
'replication_factor': '3'
}  
AND durable_writes = true;

```

在 Cassandra 中，您可以在创建键空间时或稍后通过修改键空间在键空间级别设置复制策略。

**更改网络拓扑策略的复制因子:**
在这种情况下，您可以考虑一个现有的键空间，您想要更改网络拓扑策略的复制因子。

示例:现有键空间:app_data
通过执行以下 CQL 查询，可以看到 app_data 键空间的描述。

```
cassandra@cqlsh> describe app_data;

```

**输出:**

```
CREATE KEYSPACE app_data 
WITH replication = 
{'class': 'NetworkTopologyStrategy', 
'datacenter1': '3', 
'datacenter2': '2'}  
AND durable_writes = true;

```

现在，如果我们想将 datacenter2 的复制因子从 2 更改为 3，那么您可以执行下面给出的 CQL 查询。

```
cassandra@cqlsh> ALTER KEYSPACE app_data
   ...        WITH replication =
   ...        {
   ...         'class': 'NetworkTopologyStrategy',
   ...         'datacenter1': '3',
   ...         'datacenter2': '3'
   ...        }
   ...          AND durable_writes = true;

```

现在，为了验证结果，您可以执行以下 CQL 查询。

```
cassandra@cqlsh> describe app_data;

```

**输出:**

```
CREATE KEYSPACE app_data 
WITH replication = 
{
'class': 'NetworkTopologyStrategy', 
'datacenter1': '3', 
'datacenter2': '3'
}  
AND durable_writes = true;

```

**Note:**

*   在卡珊德拉中，您不能更改键空间的名称。*   在更改复制因子或任何修改之后，执行修复命令总是一种好的做法。*   您可以执行以下 CQL 查询进行完全修复。

    ```
    nodetool repair -full

    ```