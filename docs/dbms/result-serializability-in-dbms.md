# 数据库管理系统中的结果可串行化

> 原文:[https://www . geesforgeks . org/result-serializability-in-DBMS/](https://www.geeksforgeeks.org/result-serializability-in-dbms/)

先决条件–[可序列化计划](https://www.geeksforgeeks.org/difference-between-conflict-and-view-serializability/?ref=rp)

**时间表的等价性:**
时间表是表示事务操作执行顺序的一种方式。根据与计划相关的不同属性(如最终结果)，两个计划的事务执行顺序可能是相同的。时间表的等效性大致分为以下三类–

1.  结果等价
2.  [数据库管理系统中的冲突可串行化](https://www.geeksforgeeks.org/conflict-serializability-in-dbms/)
3.  [在数据库管理系统中查看可序列化性](https://www.geeksforgeeks.org/view-serializability-in-dbms-transactions/)

**结果在 DBMS 中的可串行化:**
也称为结果等价调度。
如果两个调度 S1 和 S2 产生相同的最终数据库状态，也就是说，它们在执行后必须产生相同的结果，那么这两个调度被称为结果等价。这种类型的等价被赋予最不重要的意义，因为两个调度可能对某一组操作产生相同的结果，而对其他组产生不同的结果。

**示例-1:**
让我们考虑以下时间表 S1 和 S2，并检查 X 和 Y 的初始值分别为 2 和 5 时的结果等价性。

**S1 时间表–**

<center>

| 一种网络的名称(传输率可达 1.54mbps) | T2 |
| --- | --- |
| R(X) |  |
| X=X+5 |  |
| W(X) |  |
| 右(右) |  |
| Y=Y+5 |  |
| W(Y) |  |
|  | R(X) |
|  | X=X*3 |
|  | W(X) |

</center>

**S2 时间表–**

<center>

| 一种网络的名称(传输率可达 1.54mbps) | T2 |
| --- | --- |
| R(X) |  |
| X=X+5 |  |
| W(X) |  |
|  | R(X) |
|  | X=X*3 |
|  | W(X) |
| 右(右) |  |
| Y=Y+5 |  |
| W(Y) |  |

</center>

在上述两个时间表中，将 X 和 Y 分别替换为 2 和 5 的最终值分别为 **X=21 和 Y=10** 。
因此，S1 和 S2 是**结果等效时间表。**

**示例-2:**
让我们考虑以下时间表 S1 和 S2，并检查 X 和 Y 的初始值分别为 3 和 6 时的结果等价性。

**S1 时间表–**

<center>

| 一种网络的名称(传输率可达 1.54mbps) | T2 |
| --- | --- |
| R(X) |  |
| X=X+1 |  |
| W(X) |  |
| 右(右) |  |
| Y=Y*2 |  |
| W(Y) |  |
|  | R(X) |
|  | X=X*3 |
|  | W(X) |

</center>

**S2 时间表–**

<center>

| 一种网络的名称(传输率可达 1.54mbps) | T2 |
| --- | --- |
| R(X) |  |
| X=X+1 |  |
| W(X) |  |
|  | 右(右) |
|  | Y=Y*2 |
|  | W(Y) |

</center>

在上述两个附表中，将 X 和 Y 分别替换为 3 和 6 的最终值为–

*   对于 S1，X = 12，Y = 12
*   对于 S2，X = 4，Y = 12

两个计划完全执行后的最终值是不同的。这是因为它们都有不同的操作集。因此，S1 和 S2 不是结果等效时间表。