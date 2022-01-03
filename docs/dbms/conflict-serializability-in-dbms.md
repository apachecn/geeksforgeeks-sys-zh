# 数据库管理系统中的冲突可串行化

> 原文:[https://www . geesforgeks . org/conflict-serializability-in-DBMS/](https://www.geeksforgeeks.org/conflict-serializability-in-dbms/)

如[并发控制](https://www.geeksforgeeks.org/concurrency-control-in-dbms/)所述，串行调度资源利用率低，吞吐量低。为了改进它，两个或多个事务同时运行。但是事务的并发性可能导致数据库的不一致性。为了避免这种情况，我们需要检查这些并发调度是否可序列化。

**冲突可串行化:**如果一个调度可以通过交换不冲突的操作转化为串行调度，则称之为冲突可串行化。

**冲突操作:**如果所有条件都满足，则两个操作称为冲突操作:

*   它们属于不同的交易
*   它们对相同的数据项进行操作
*   其中至少有一个是写操作

示例:–

*   **冲突的**操作对(R <sub>1</sub> (A)，W <sub>2</sub> (A))，因为它们属于同一数据项 A 上的两个不同事务，其中一个是写操作。
*   同样，(W <sub>1</sub> (A)、W <sub>2</sub> (A))和(W <sub>1</sub> (A)、R <sub>2</sub> (A))对也是**冲突**。
*   另一方面，(R <sub>1</sub> (A)、W <sub>2</sub> (B))对是**不冲突的**，因为它们对不同的数据项进行操作。
*   同理，((W <sub>1</sub> (A)、W <sub>2</sub> (B))对为**不冲突。**

考虑以下时间表:

```
S1: R1(A), W1(A), R2(A), W2(A), R1(B), W1(B), R2(B), W2(B)

```

如果 O <sub>i</sub> 和 O <sub>j</sub> 是一个事务中的两个操作，并且 O<sub>I</sub>T13】O<sub>j</sub>(O<sub>I</sub>在 O <sub>j</sub> 之前执行)，那么在时间表中也会遵循相同的顺序。利用这个属性，我们可以得到 S1 时间表的两个事务，如下所示:

```
T1: R1(A), W1(A), R1(B), W1(B)
T2: R2(A), W2(A), R2(B), W2(B)

```

**可能的连续时间表是:T1- > T2 或 T2->T1**T3】

-> **在 S1 交换非冲突操作** s R <sub>2</sub> (A)和 R <sub>1</sub> (B)，日程变为:

```
S11: R1(A), W1(A), R1(B), W<sub>2</sub>(A), R2(A), W<sub>1</sub>(B), R2(B), W2(B)

```

->同样，在 S11 中，s **将非冲突操作**转换为 W <sub>2</sub> (A)和 W <sub>1</sub> (B)，日程变为:

```
S12: R1(A), W1(A), R1(B), W1(B), R2(A), W2(A), R2(B), W2(B)

```

S12 是一个串行调度，其中在开始 T2 的任何操作之前执行 T1 的所有操作。由于通过交换 S1 的非冲突操作，S 已经被转换为串行调度 S12，所以 S1 是冲突可串行化的。

让我们看看另一个时间表:

```
S2: R2(A), W2(A), R1(A), W1(A), R1(B), W1(B), R2(B), W2(B)

```

两项交易将是:

```
T1: R1(A), W1(A), R1(B), W1(B)
T2: R2(A), W2(A), R2(B), W2(B)

```

**可能的连续时间表是:T1- > T2 或 T2->T1**T3】

原计划是:

```
S2: R2(A), W2(A), R<sub>1</sub>(A), W1(A), R1(B), W1(B), R<sub>2</sub>(B), W2(B)

```

在 S2 交换非冲突操作 R <sub>1</sub> (A)和 R <sub>2</sub> (B)，日程变为:

```
S21: R2(A), W2(A), R2(B), W<sub>1</sub>(A), R1(B), W1(B), R1(A), W<sub>2</sub>(B)

```

类似地，在 S21 中交换非冲突操作 W <sub>1</sub> (A)和 W <sub>2</sub> (B)，调度变为，

```
S22: R2(A), W2(A), R2(B), W2(B), R1(B), W1(B), R1(A), W1(A)

```

在时间表 S22 中，首先执行 T2 的所有操作，但 T1 的操作没有按顺序执行(顺序应为 R <sub>1</sub> (A)、W <sub>1</sub> (A)、R <sub>1</sub> (B)、W <sub>1</sub> (B))。所以 S2 不是冲突可串行化的。

**冲突等价:**当一个调度可以通过交换非冲突操作转换为另一个调度时，两个调度被称为冲突等价。在上面讨论的例子中，S11 与 S1 是冲突等价的(S1 可以通过交换非冲突操作转换为 S11)。同样，S11 也是与 S12 相当的冲突，以此类推。

***注 1:** 虽然 S2 不是冲突可串行化的，但还是冲突等价于 S21 和 S21，因为 S2 可以通过交换非冲突操作转换成 S21 和 S22。*

***注 2:** 冲突可串行化的调度总是冲突等价于串行调度之一。上面讨论的 S1 时间表(可冲突序列化)相当于串行时间表(T1- > T2)。*

**问题:** **考虑以下涉及两笔交易的时间表。以下哪一种说法是正确的？**

S1:r<sub>1</sub>(x)r<sub>1</sub>(y)r<sub>2</sub>(x)r<sub>2</sub>(y)w<sub>2</sub>(y)w

*   S1 和 S2 都是冲突可串行化的
*   只有 S1 是冲突可串行化的
*   只有 S2 是冲突可串行化的
*   没有人

[GATE 2007]

**解决方案:**给定计划的两个事务是:

```
 T1: R1(X) R1(Y) W1(X)
 T2: R2(X) R2(Y) W2(Y)

```

让我们首先检查 S1 的可串行化:

```
S1: R1(X) R1(Y) R2(X) R2(Y) W2(Y) W1(X)

```

要将其转换为串行计划，我们必须交换不冲突的操作，这样 S1 就相当于串行计划 T1->T2 或 T2->T1。在这种情况下，要将其转换为串行计划，我们必须交换 R <sub>2</sub> (X)和 W <sub>1</sub> (X)，但它们是冲突的。所以 S1 不能被转换成一个连续的时间表。

现在，让我们检查一下 S2 的可序列化性:

```
S2: R<sub>1</sub>(X) R<sub>2</sub>(X) R2(Y) W2(Y) R1(Y) W1(X)

```

交换 S2 的非冲突操作 R <sub>1</sub> (X)和 R <sub>2</sub> (X)，我们得到

```
S2’: R2(X) R<sub>1</sub>(X) R<sub>2</sub>(Y) W2(Y) R1(Y) W1(X)

```

同样，交换 S2 的非冲突操作 R <sub>1</sub> (X)和 R <sub>2</sub> (Y)，我们得到

```
S2’’: R2(X) R2(Y) R<sub>1</sub>(X) W<sub>2</sub>(Y) R1(Y) W1(X)

```

同样，交换 S2 ' '的非冲突操作 R <sub>1</sub> (X)和 W <sub>2</sub> (Y)，我们得到

```
S2’’’: R2(X) R2(Y) W2(Y) R1(X) R1(Y) W1(X)

```

这相当于串行调度 T2->T1。

所以，**正确选项是 C** 。只有 S2 是冲突可串行化的。

**相关文章:**
[查看可串行化](https://www.geeksforgeeks.org/view-serializability-in-dbms-transactions/)
[测试冲突可串行化的优先图](https://www.geeksforgeeks.org/precedence-graph-testing-conflict-serializability/)

Sonal Tuteja 撰写的文章。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息