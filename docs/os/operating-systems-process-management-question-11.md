# 操作系统|流程管理|问题 6

> 原文:[https://www . geesforgeks . org/operating-systems-process-management-question-11/](https://www.geeksforgeeks.org/operating-systems-process-management-question-11/)

初始化为零的共享变量 X 由四个并发进程 W、X、Y、Z 操作，如下所示。每个进程 W 和 X 从内存中读取 X，递增 1，将其存储到内存中，然后终止。每个进程 Y 和 Z 从内存中读取 x，递减 2，存储到内存中，然后终止。读取 x 之前的每个进程调用计数信号量 S 上的 P 操作(即等待)，并将 x 存储到内存后调用信号量 S 上的 V 操作(即信号)。信号量 S 初始化为 2。所有进程完成执行后，x 的最大可能值是多少？(GATE CS 2013)

**(A)**-2
**(B)**-1
**(C)**1
**(D)**2

**回答:****(D)**

**说明:**流程可以多种方式运行，以下是 x 达到最大值的情况之一

```
Semaphore S is initialized to 2

Process W executes S=1, x=1 but it doesn't update the x variable.

Then process Y executes S=0, it decrements x, now x= -2 and 
signal semaphore S=1

Now process Z executes s=0, x=-4, signal semaphore S=1
Now process W updates x=1, S=2

Then process X executes X=2 
```

所以正确的选项是(D)。

观看极客博客视频讲解:

[本题小考](https://www.geeksforgeeks.org/operating-systems-gq/process-synchronization-gq/)