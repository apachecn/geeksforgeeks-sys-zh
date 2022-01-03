# 测谎仪检查数据库管理系统中视图的可串行化

> 原文:[https://www . geesforgeks . org/polygraph-to-check-view-serializability-in-DBMS/](https://www.geeksforgeeks.org/polygraph-to-check-view-serializabilty-in-dbms/)

先决条件–[并发控制-简介](https://www.geeksforgeeks.org/concurrency-control-introduction/)、[冲突可串行化](https://www.geeksforgeeks.org/conflict-serializability/)、[DBMS 中的事务隔离级别](https://www.geeksforgeeks.org/transaction-isolation-levels-dbms/)
**可串行化:**如果任何事务(非串行)产生的结果等于该调度的事务串行执行的结果，那么我们可以将该事务调度称为**可串行化**调度。

请注意，可序列化的主要目标是找到允许事务在不受干扰的情况下并发执行的非串行调度，并产生一个可以由串行执行产生的数据库状态。这些是以下类型的计划:

1.  串行计划
2.  [冲突可串行化](https://www.geeksforgeeks.org/precedence-graph-testing-conflict-serializability/)
3.  视图可序列化性
4.  非连续时间表

**查看可序列化性–**
一个计划被称为**查看可序列化性**，如果它的[视图等同于一个串行计划](https://www.geeksforgeeks.org/dbms-how-to-test-two-schedule-are-view-equal-or-not-2/)(不允许重叠事务)。以下是视图可序列化的条件:

1.  在计划中，按事务读取数据项的初始值和写入数据项的最终值必须相同。
2.  W->R 冲突在两个计划中必须相同。

现在，让我们考虑下面的例子。

**示例:**假设有两个调度，一个是非串行调度，另一个是串行调度。

```
    Schedule 1              Schedule 2      
  --------------          ---------------
   T1      T2               T1      T2
  --------------          ---------------
  r1(A)                    r1(A)
  A=A+10                   A=A+10
  w1(A)                    w1(A)
  r1(B)                            r2(A)
  B=B*10                           A=A+10
  w1(B)                            w2(a)
          r2(A)            r1(B)                            
          A=A+10           B=B*10      
          w2(A)            w2(B)      
          r2(B)                    r2(B)
          B=B*10                   B=B*10
          w2(B)                    w2(B)  
```

检查视图是否可序列化:

```
    Comparison Table
---------------------------
Schedule 1    Schedule 2
---------------------------
A   T1 T2         T1 T2
B   T1 T2         T1 T2 
```

所以附表 2 是相当于附表 1 的视图。

**当交易次数超过 2 次时使用测谎仪:**
假设我们有 3 次交易 T1、T2 和 T3。这些交易的可能组合是:

```
--------------
 T1   T2   T3
 T1   T3   T2
 T2   T1   T3
 T2   T3   T1
 T3   T1   T2
 T3   T2   T1
-------------- 
```

1.Tn 读取计划中的初始数据，同样的 Tn 也应该读取事务组合之一中的初始数据。这意味着 T1 应该出现在 T2 之前，所以我们必须移除这些组合:

```
--------------
 T2   T1   T3
 T2   T3   T1
 T3   T2   T1
-------------- 
```

2.一个 Tn 在另一个 Tn 写入一个计划后读取一个数据，同样的 Tn 也应该在另一个 Tn 写入一个事务组合后读取。

3.一个 Tn 在一个计划中写入一个数据的最终值，同样的 Tn 也应该在一个事务组合中写入最终数据。这意味着 T2 发生在 T3 之前，所以我们必须删除这些组合:

```
--------------
 T1   T3   T2
 T3   T1   T2
 T3   T2   T1
-------------- 
```

**例:**

```
Schedule = w3(x),r2(x),w2(y),r1(z),w3(y),w1(y) 
```

```
  T1   T2    T3
----------------
            w(x)
     r2(x)
     w2(y)
r1(z)
           w3(y)
w1(y)
---------------- 
```

这里 T3 必须先占用，虽然实际上没有关系，因为没有其他人写 X，我们将在第一步保留所有可能的事务组合。

T1 必须出现在 T3 之后，因为 T1 在 T3 写入 Z 之后读取 Z。因此，这里我们删除了这三种事务组合，其中 T1 在 T3 之前。

```
Available combination:
 T2 T3 T1
 T3 T1 T2
 T3 T2 T1 
```

T2 必须最后出现，因为如果不是 T3，T2 将覆盖 T1 在我们的时间表中写入的 y，因此我们从可用组合中删除 T1 不是最后出现的位置。

```
Available combination:
 T2 T3 T1
 T3 T2 T1 
```

**注意**当在任何交易中盲写可用时，我们使用测谎仪。