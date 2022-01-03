# 两阶段锁定(2-PL)并发控制协议|集合 3

> 原文:[https://www . geesforgeks . org/两相锁定-2-pl-并发控制-协议-set-3/](https://www.geeksforgeeks.org/two-phase-locking-2-pl-concurrency-control-protocol-set-3/)

先决条件-[两相](https://www.geeksforgeeks.org/dbms-concurrency-control-protocols-two-phase-locking-2-pl/)[锁定协议基础(2-PL)](https://www.geeksforgeeks.org/dbms-concurrency-control-protocols-two-phase-locking-2-pl/) 、[2-PL 类型](https://www.geeksforgeeks.org/dbms-concurrency-control-protocol-two-phase-locking-2-pl-ii/)。

现在，我们知道严格 2-PL 和严格 2-PL *都避免了*级联回滚，*确保了*严格的时间表，但仍然不能保证我们的时间表没有死锁。我们已经看到严格 2-PL 和严格 2-PL 在应用上是相似的，一个普遍的误解是保守 2-PL 也遵循与上面两个相同的协议集。为了清楚起见，让我们详细介绍一下保守党 2-PL。

### 保守的 2-PL–

A.也称为 **Static 2-PL** ，该协议要求事务通过预定义其读集和写集来锁定它在事务开始执行之前访问的所有项目。如果需要的任何预先声明的项目无法锁定，事务不会锁定任何项目，而是等待，直到所有项目都可以锁定。因此，在我们锁定所有需要的项目之前，对数据的操作无法开始。

现在让我们看看保守党 2-PL 的一个有趣的例子。告诉我以下时间表是否遵循保守党 2-PL？

```
Schedule:   Lock-X(A)  Lock-X(B)  Read(A)  Read(B)  Write(A)  Unlock(A)  Commit  Unlock(B)
```

你认为上面的时间表*没有遵循*保守 2-PL 吗？不要把协议混淆为只是一个严谨 2-PL 的修改版本，我们可以随时释放锁，但是我们需要在执行任何操作之前锁定所有数据项。这是它无死锁的原因。上述时间表遵循保守党 2-PL。

保守党 2-PL 的一些有趣特征:

*   接下来的时间表不会像我们在基本、严格和严格 2-PL 中看到的那样有一个增长阶段。由于在使用前锁定数据是强制性的，因此该协议没有增长阶段。此外，该规则使其无死锁，就像某个项目不可用于锁定事务一样，释放所有锁，稍后再试，即*无等待*。这使得[死锁的四个必要条件之一](https://www.geeksforgeeks.org/operating-system-process-management-deadlock-introduction/)无效。
*   我们只需要事先锁定所有的物品，所以释放或解锁它们没有限制，就像我们在严格或严格 2-PL 中一样。
*   由于在获取所有锁之前没有任何操作，我们在这个协议中没有增长阶段，不像基本的、严格的、严格的 2-PL。
*   虽然我们在这个协议中获得了一个无死锁的调度，但是我们仍然可能面临类似*级联回滚*的缺点。所以这个协议*不保证严格的时间表*。与严格和严谨 2-PL 相比，这是一个缺点。

现在我们来讨论一个例子。看看下面的时间表如何遵循保守 2-PL，但不遵循严格和严格 2-PL。

<figure class="table">

|   | **T<sub>1</sub>T3】** | **T<sub>2</sub>T3】** |
| **1**T2】 | 锁定-X(A) |   |
| **2** | 锁-十(乙) |   |
| **3** | 阅读(一) |   |
| **4** | *对 A 的操作 |   |
| **5** | 写作(一) |   |
| **6** | 解锁(一) |   |
| **7** |   | 锁定-X(A) |
| **8** |   | 阅读(一) |
| **9** |   | *对 A 的操作 |
| **10** |   | 写作(一) |
| **11** |   | 解锁(一) |
| **12** | 阅读(二) |   |
| **13** | *对 B 的操作 |   |
| **14** | 写(乙) |   |
| **15** | 解锁(乙) |   |
| **16** | **提交** |   |
| **17** |   | **提交** |

看时间表，完全遵循了 Conservative 2-PL，但是没有达到 Strict 和 Strict 2-PL 的要求，那是因为我们在事务提交之前解锁了 A 和 B。

**保守党 2-PL 怎么会发生级联中止？**
这可能发生，因为一个事务可能会执行另一个事务的*脏读*。我们的协议中没有这样的限制，所以这种情况是可能的。

看上面给出的例子，我们在第 8 步有一个从**T<sub>1</sub>T3】到**T<sub>2</sub>T7】的脏读操作。如果 **T <sub>1</sub>** 中止，则 **T <sub>2</sub>** 将回滚。****

GATE 相关问题:
[GATE-CS-2016(第 1 集)|问题 61](https://www.geeksforgeeks.org/gate-gate-cs-2016-set-1-question-61/)

</figure>