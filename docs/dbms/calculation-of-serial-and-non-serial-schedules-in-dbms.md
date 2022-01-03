# 数据库管理系统中串行和非串行计划的计算

> 原文:[https://www . geeksforgeeks . org/计算数据库中的串行和非串行计划/](https://www.geeksforgeeks.org/calculation-of-serial-and-non-serial-schedules-in-dbms/)

事务的连续执行被定义为调度。它由许多事务组成，每个事务由许多指令组成。

**[时刻表类型](https://www.geeksforgeeks.org/types-of-schedules-in-dbms/)–**

*   串行计划
*   非连续计划

**计划数的计算:**
考虑有 N 个交易 T1、T2、t3、…。，tN 带 k1，k2，k3，…..，kN 操作次数分别为。

1.  **计划总数–**

    ```
    (N1 + N2 + N3 + ..... + Nn)! / (N1! * N2! * N3! * ... * Nn!)
    ```

2.  **连续时间表的数量–**

    ```
    It is all possible permutations of n transactions = N!
    ```

3.  **非连续计划数量–**
    总计划=连续计划+非连续计划
    非连续计划数量=计划总数–连续计划数量

    ```
    ((N1 + N2 + N3 + ..... + Nn)! / (N1! * N2! * N3! * ... * Nn!)) - (N!)
    ```

**例–**
假设有三个交易，分别有 1、2 和 3 个操作。
我们必须找到–

*   可能的计划总数。
*   可能的串行计划和非串行计划的总数。

**解决方案–**
计划总数，

```
= (1 + 2 + 3)! / (1! + 2! + 3!) = 6! / 9 = 120

Number of Serial Schedules,
= 3! = 6

Number of Non-Serial Schedules,
= Total Number of Schedules - Number of Serial Schedules 
= 120 - 6 
= 114 
```