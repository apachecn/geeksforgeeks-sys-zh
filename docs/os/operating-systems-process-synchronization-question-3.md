# 操作系统| CPU 调度|问题 1

> 原文:[https://www . geesforgeks . org/operating-systems-process-synchronization-question-3/](https://www.geeksforgeeks.org/operating-systems-process-synchronization-question-3/)

考虑具有计算时间突发 2、4 和 8 个时间单位的三个进程(分别是进程 id 0、1、2)。所有过程都在时间零点到达。考虑最长剩余时间优先(LRTF)调度算法。在 LRTF，通过给予具有最低进程 id 的进程优先权来打破联系。平均掉头时间为:
**(A)** 13 台
**(B)** 14 台
**(C)** 15 台
**(D)** 16 台

**答案:****(A)**

**解释:**让流程为 p0、p1、p2。这些过程将按以下顺序执行。

```
  p2  p1  p2  p1  p2  p0  p1   p2   p0   p1   p2
0   4   5   6   7   8   9   10    11   12   13   14 

```

流程的周转时间是从流程提交到完成的总时间。
P0 = 12(12-0)的掉头时间
P1 = 13(13-0)的掉头时间
p2 = 14(14-0)的掉头时间

平均周转时间为(12+13+14)/3 = 13。

[本题小考](https://www.geeksforgeeks.org/cpu-scheduling-gq/)