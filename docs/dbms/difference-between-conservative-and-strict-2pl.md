# 保守和严格 2PL 的区别

> 原文:[https://www . geesforgeks . org/保守与严格的区别-2pl/](https://www.geeksforgeeks.org/difference-between-conservative-and-strict-2pl/)

**先决条件–**[两相锁定协议](https://www.geeksforgeeks.org/two-phase-locking-protocol/?ref=rp)和[类型的两相锁定协议](https://www.geeksforgeeks.org/categories-of-two-phase-locking-strict-rigorous-conservative/)

**1。保守 2-PL :**

*   它也被称为静态 2-PL。
*   该协议要求事务在开始执行之前通过预先声明其读集和写集来锁定它访问的所有项目。
*   如果需要的任何预先声明的项目不能被锁定，事务不会锁定任何项目，而是等待，直到所有项目都可以锁定。

**2。严格 2-PL :**

*   2-PL 最流行的变体是严格 2-PL。
*   它是严谨 2-PL 的较轻版本。
*   这要求除了锁是 2 阶段的之外，事务持有的所有独占(X)锁都被释放，直到事务提交之后。
*   允许事务在提交之前释放共享锁。

**保守与严格的区别 2-PL :**

<center>

| 没有。 | 保守的 2-PL | 严格 2-PL |
| --- | --- | --- |
| 1. | 在 Conservative 2-PL 中，事务在开始执行之前，必须获取它所需要的所有数据项的锁。 | 在严格 2-PL 中，事务可以在执行过程中随时(仅在增长阶段)获取数据项的锁。 |
| 2. | 它没有生长阶段。 | 它有生长阶段。 |
| 3. | 它有收缩阶段。 | 它有部分收缩阶段。 |
| 4. | 它确保生成的计划是可序列化和无死锁的。 | 它确保生成的计划是可序列化的、可恢复的和无级联的。 |
| 5. | 它不能确保可恢复和无级联计划。 | 它不能确保无死锁的调度。 |
| 6. | 它不能确保严格的时间表。 | 它确保生成的时间表是[严格的](https://www.geeksforgeeks.org/types-of-schedules-in-dbms/)。 |
| 7. | 与 Strict 2-PL 相比，它不太受欢迎。 | 它是 2-PL 最流行的变体。 |
| 8. | 它没有在实践中使用。 | 它是 2-PL 最流行的变体。 |
| 9. | 在保守 2-PL 中，事务可以读取未提交事务的值。 | 在严格 2-PL 中，事务只读取提交事务的值。 |

</center>