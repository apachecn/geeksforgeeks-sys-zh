# 抢占式和非抢占式 CPU 调度算法的区别

> 原文:[https://www . geesforgeks . org/抢先和不抢先 cpu 调度算法的区别/](https://www.geeksforgeeks.org/difference-between-preemptive-and-non-preemptive-cpu-scheduling-algorithms/)

在 [CPU 调度](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)中，我们有两种类型的调度，我们来看看它们:

**抢占式调度:**
在这种情况下，当高优先级进程进入就绪状态时，调度器可以随时抢占低优先级运行的进程。当调度发生在以下任一情况时，它是*优先调度*–

*   当进程从运行状态切换到就绪状态时(例如，当中断发生时)。
*   当进程从等待状态切换到就绪状态时(例如，在输入/输出完成时)。

**非抢占式调度:**
在这种情况下，一旦进程进入运行状态，它就不能被抢占，直到它完成它的分配时间。只有在以下情况下进行调度时，我们说调度方案是*非抢先*或*合作*。–

*   当进程从运行状态切换到等待状态时(例如，作为输入/输出请求或调用 wait()终止子进程的结果)。
*   当进程终止时。

让我们看看抢先调度和非抢先调度的区别:

<center>

| 没有。 | 抢先调度 | 非抢占式调度 |
| --- | --- | --- |
| 1. | 在一定时间内，中央处理器被分配给进程。 | 中央处理器被分配给进程，直到它结束执行或切换到等待状态。 |
| 2. | 这里的执行过程在执行过程中被中断。 | 这里的执行过程在执行过程中不会中断。 |
| 3. | 它通常将进程从就绪状态切换到运行状态，反之亦然，并维护就绪队列。 | 它不会将进程从运行状态切换到就绪状态。 |
| 4. | 这里，如果具有高优先级的进程频繁地到达就绪队列，那么具有低优先级的进程必须等待很长时间，并且它可能不得不挨饿。 | 这里，如果中央处理器被分配给具有较大突发时间的进程，那么具有较小突发时间的进程可能不得不挨饿。 | 5. | 它非常灵活，因为关键进程在进入就绪队列时被允许访问 CPU，无论当前正在执行什么进程。 | 它是刚性的，因为即使关键进程进入就绪队列，运行中央处理器的进程也不会受到干扰。 | 6. | 这是与成本相关的，因为它必须保持共享数据的完整性。 | 这与成本无关。 |

</center>

Preemptive scheduling is better than non-preemptive scheduling or vise-versa can’t be said definitely. It depends on how a scheduling minimizes the average waiting time of the processes and maximizes CPU utilization.