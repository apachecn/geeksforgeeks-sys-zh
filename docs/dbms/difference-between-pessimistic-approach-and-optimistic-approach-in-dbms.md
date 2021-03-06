# 数据库管理系统中悲观方法和乐观方法的区别

> 原文:[https://www . geesforgeks . org/DBMS 中悲观方法和乐观方法的区别/](https://www.geeksforgeeks.org/difference-between-pessimistic-approach-and-optimistic-approach-in-dbms/)

**1。悲观方法:**

悲观方法是并发控制算法的一种方法，在这种方法中，如果在将来的某个时间点上彼此发生冲突，事务就会被延迟。它锁定数据库记录以供更新访问，其他用户只能以只读方式访问记录，或者必须等待记录被“解锁”。由于死锁的风险，用悲观并发方法编程应用程序在管理上可能更加复杂。

在悲观方法的执行中，首先执行验证操作，如果存在与锁的兼容性一致的验证，则只执行读取、计算和写入操作，即，

> **验证- >读取- >计算- >写入**

在悲观方法中，我们使用两种常见的锁定协议:

1.  [**两相锁定协议**](https://www.geeksforgeeks.org/two-phase-locking-protocol/)
2.  [**时间戳排序协议**](https://www.geeksforgeeks.org/timestamp-based-concurrency-control/)

**2。乐观方法:**

乐观方法是一种并发控制算法方法，它基于数据库上操作冲突很少的假设。建议将这些事务运行到完成，并且仅在提交之前检查冲突。在这里，在执行事务时不需要进行检查。这种方法不需要任何锁定或时间戳方法。在乐观的方法中，在事务提交之前，事务的执行没有任何限制问题。乐观的方法允许事务以不同步的方式进行，也允许在最后进行冲突检查。这种方法也被称为**验证**或**认证方法。**

在乐观执行期间，我们只进行读取和计算操作，而不进行验证，并在正确的操作之前验证事务。

> **读取- >计算- >验证- >写入**

**乐观进场的优势:**

*   在乐观方法事务中，当联系人在那里时，回滚变得非常容易。
*   在乐观的方法中，您不会发现任何级联回滚，因为它只使用数据的本地副本，而不使用数据库。

**乐观方法的缺点:**

*   使用乐观方法进行并发控制可能非常昂贵，因为它需要回滚。
*   如果在这种方法中，大事务和小事务之间存在冲突，那么只有大事务会被反复回滚，因为它们包含更多的冲突。

**悲观方法和乐观方法的区别:**

<figure class="table">

| **悲观进场** | **乐观进场** |
| 它锁定记录，以便所选的更新记录在此期间不会被其他用户更改 | 它不会锁定记录，因为它确保记录不会在 SELECT & SUBMIT 操作之间及时更改。 |
| 在这种方法中，事务之间的冲突非常大 | 与悲观的方法相比，事务之间的冲突较少。 |
| 事务的同步在事务执行的生命周期的开始阶段进行 | 事务的同步在稍后阶段进行，或者在事务执行中被延迟 |
| 设计和编程都很简单。 | 它在设计和管理死锁风险方面更加复杂 |
| 它有较高的存储成本 | 与悲观方法相比，它的存储成本相对较低 |
| 它的并发程度较低 | 它具有高度的并发性 |
| 发现这种方法可用于存在更多事务冲突的地方 | 发现这种方法在事务冲突较少或非常罕见的情况下使用 |
| 交易阶段的流程:验证->读取->计算->写入 | 交易阶段的流程:读取->计算->验证->写入 |
| 它有助于保护系统免受并发冲突的影响 | 它允许冲突发生 |
| 它适用于记录较少的小型数据库或表 | 它适用于大型数据库或记录较多的数据库 |

</figure>