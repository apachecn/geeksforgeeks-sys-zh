# 修改卡珊德拉中的键空间

> 原文:[https://www . geesforgeks . org/modification-keyspace-in-Cassandra/](https://www.geeksforgeeks.org/modifying-keyspace-in-cassandra/)

先决条件–[卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)
在本文中，我们将讨论如何使用 ALTER KEYSPACE 命令修改现有的 keyspace。当我们想要修改一些属性，例如复制因子、数据中心名称、密钥空间名称等时，这非常有帮助。

**程序:**
首先，我们需要创建键空间。让我们考虑集群 1 是关键空间，我们有战略选项，如网络拓扑系统战略和数据中心名称东和西，其中两个数据中心的复制因子都是 2。让我们看看。

**创建键空间:**

```
CREATE KEYSPACE cluster1
WITH REPLICATION = {'class' : 'SimpleStrategy', 
                    'replication_factor' : 3}; 
```

如果我们使用简单策略，那么我们可以使用下面的 CQL 查询来修改现有的键空间。

```
ALTER KEYSPACE cluster1
WITH REPLICATION =  { 'class' : 'SimpleStrategy', 
                      'replication_factor' : 3 }; 
```

**更改复制策略:**
如果修改，我们可以将 RF(复制因子)和复制策略设置在键空间级别。让我们用一个例子来理解这一点。

```
ALTER KEYSPACE cluster1
WITH REPLICATION = {'class’: 'NetworkTopologyStrategy', 
                    'east1' : 3, 'west1' : 3}; 
```

现在，如果我们想修改一个现有的键空间，在这个空间中我们有更改键空间名称的限制。让我们来看看。

```
ALTER KEYSPACE cluster1
WITH REPLICATION = {'class’: 'NetworkTopologyStrategy', 
                    'east1' : 3, 'dc2' : 2}; 
```

注意:数据中心名称区分大小写。使用实用程序验证数据中心名称的大小写，如 dsetool status。
请参见更改键空间复制策略。

```
dsetool status
```

现在，当我们要添加数据中心时，我们可以对关键空间进行全面修复。让我们来看看。

```
nodetool repair --full keyspace_name
nodetool repair –full cluster1; 
```

现在，使用下面的 CQL 查询来验证键空间的更改。

```
describe keyspace cluster1; 
```