# 卡珊德拉的一致性水平

> 原文:[https://www . geesforgeks . org/consistency-levels-in-Cassandra/](https://www.geeksforgeeks.org/consistency-levels-in-cassandra/)

在本文中，我们将讨论 Cassandra 中的一致性级别，这对 [Cassandra](https://www.geeksforgeeks.org/features-of-cassandra/) 中的高可用性和高机制非常有帮助。让我们一个一个来讨论。

首先，我们将定义密钥空间的场景，在该场景中，我们将展示我们如何拥有一个不同的数据中心，并且每个数据中心包含 3 个副本。让我们来看看。

```
CREATE KEYSPACE cluster_consistency
with replication =  {'class' : 'NetworkTopologyStrategy', 
                     'DC1': 3, 'DC2': 3, 'DC3': 3}
AND DURABLE_WRITES = false; 
```

在上面的 CQL 查询中，我们有三个不同的数据中心，如 DC1、DC2 和 DC3。每个数据中心有 3 个副本，这意味着复制因子为 3(射频=3)。

让我们考虑这样一个场景，即每 3 个数据中心有三个复制因素。

*   **LOCAL_ONE :**
    在这个一致性级别中，我们需要 1 个节点从本地 dc 响应才能成功。

*   **LOCAL_QUORUM :**
    在这个一致性级别，我们需要 2 个节点从本地 dc 响应才能成功。

*   **每个 _QUORUM :**
    在这个一致性级别中，我们需要每个 dc 中的 2 个节点才能成功。因此，如果每个数据中心有 2 个节点响应，那么在本例中总共有 6 个节点。

*   **LOCAL_SERIAL :**
    此一致性级别为 Like LOCAL_QUORUM。在这种一致性级别下，我们需要本地 DC 的 2 个节点才能成功。但是，In LOCAL _SERIAL 一致性级别有很多额外的流量(至少 4 倍往返)，以加强 Cassandra 中的顺序和一致性。

*   **ONE:**
    在此一致性级别中，ONE 的写入一致性级别是必须写入至少一个副本节点的提交日志和 memtable。在这种情况下，我们需要来自任何 DC 的 1 个节点才能成功。

*   **TWO:**
    在此一致性级别中，TWO 的写入一致性级别是必须写入至少两个副本节点的提交日志和 memtable。在这种情况下，我们需要 2 个节点来响应来自任何 DC 的响应才能成功。

*   **THREE :**
    在此一致性级别中，THREE 的写入一致性级别是必须写入至少三个副本节点的提交日志和 memtable。在这种情况下，我们需要 3 个节点来响应来自任何 DC 的成功。

*   **QUORUM:**
    在此一致性级别中，写一致性级别是必须写入所有数据中心副本节点的 QUORUM 上的提交日志和 memtable。在此一致性级别(n/2 +1)中，节点需要(9/2 +1) 5 个节点来响应来自任何 DC 的响应才能成功。

*   **SERIAL :**
    就像 QUORUM 一致性。在这种一致性中，我们需要 ANY 数据中心的 5 个节点才能成功。但是，在串行级别，一致性也有很多额外的流量(至少 4 倍往返)，以加强顺序和一致性。

*   **ALL:**
    在这个一致性级别，我们需要所有 9 个副本才能成功。因此，在写入一致性的情况下，如果任何节点停机，写入将失败。在读取一致性级别为“全部”的情况下，这意味着所有副本都已响应。如果副本没有响应，它将失败。