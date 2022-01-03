# 操作系统| CPU 调度|问题 2

> 原文:[https://www . geesforgeks . org/operating-systems-process-synchronization-question-4/](https://www.geeksforgeeks.org/operating-systems-process-synchronization-question-4/)

考虑三个进程，都在时间零点到达，总执行时间分别为 10、20 和 30 个单元。每个进程前 20%的执行时间用于 I/O，后 70%的时间用于计算，最后 10%的时间再次用于 I/O。操作系统使用最短剩余计算时间优先调度算法，并在正在运行的进程在输入/输出上被阻塞或正在运行的进程完成其计算突发时调度新进程。假设所有的输入输出操作都可以尽可能重叠。CPU 保持空闲的时间百分比是多少？
**(A)**0%
**(B)**10.6%

**(C)** 30.0%

**(D)** 89.4%

**回答:** **(B)**

**说明:**设三个过程为 p0、p1、p2。他们的执行时间分别是 10、20、30。p0 前 2 个时间单位花在 I/O 上，7 个时间单位花在 CPU 上，最后 1 个时间单位花在 I/O 上，p1 前 4 个时间单位花在 I/O 上，14 个时间单位花在 CPU 上，最后 2 个时间单位花在 I/O 上，p2 前 6 个时间单位花在 I/O 上，21 个时间单位花在 CPU 上，最后 3 个时间单位花在 I/O 上

```
 idle   p0    p1     p2    idle
0    2     9     23     44     47

```

花费的总时间= 47
空闲时间= 2 + 3 = 5
空闲时间百分比= (5/47)*100 = 10.6 %

[本题竞猜](https://www.geeksforgeeks.org/cpu-scheduling-gq/)