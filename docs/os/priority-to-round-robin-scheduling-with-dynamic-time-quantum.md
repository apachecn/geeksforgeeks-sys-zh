# 具有动态时间段的循环调度的优先级

> 原文:[https://www . geeksforgeeks . org/优先级循环调度动态时间量/](https://www.geeksforgeeks.org/priority-to-round-robin-scheduling-with-dynamic-time-quantum/)

先决条件–[循环调度程序](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/)
进程根据其在该调度算法中的优先级执行。流程在到达时具有特定的优先级。当一个进程到达时，它的优先级与就绪队列中的其他进程进行比较，如果它的优先级更高，那么它就成为正在运行的进程。在非抢占算法的情况下，即使到达的进程具有更高的优先级，如果运行的进程没有被完全执行，即一旦被调度的进程将运行直到完成，则运行的进程不会被抢占。

为了避免具有较低优先级的进程的[饥饿](https://www.geeksforgeeks.org/starvation-and-aging-in-operating-systems/)，正在运行的进程和就绪队列中的进程的优先级被改变。

考虑一种抢占式优先级调度算法，其中每个进程到达就绪队列，优先级为零，并且就绪队列(等待时)的优先级以α的速率变化，CPU(运行时)的优先级以α的速率变化，那么可能有两种情况:

*   **(a)α>>0:**
    如果就绪队列中进程的优先级增加率大于 CPU，那么经过一段时间后，就绪队列中的进程将具有更高的优先级，因此正在运行的进程将被抢占，下一个具有更高优先级的进程将被转移到 CPU。它基本上变成了具有动态时间量的循环调度。
*   **(b)>α>0:**
    如果就绪队列中进程的优先级增加率小于正在运行的进程，则正在运行的进程的优先级将始终高于就绪队列中的进程。流程其实和[先到先得(FCFS)](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/) 调度差不多。随着正在运行的进程的优先级增加，它具有最高的优先级，因此它继续运行，如果α太大，那么它将被执行直到完成。