# 多级队列调度(MLQ)和先到先得(FCFS)的区别

> 原文:[https://www . geeksforgeeks . org/difference-multi-level-queue-scheduling-mlq-先到先得-fcfs/](https://www.geeksforgeeks.org/difference-between-multi-level-queue-scheduling-mlq-and-first-come-first-served-fcfs/)

**1。[多级队列调度(MLQ)](https://www.google.com/amp/s/www.geeksforgeeks.org/multilevel-queue-mlq-cpu-scheduling/amp/) :**
只有一个队列并调度所有进程是相当困难的。这是使用多级队列调度的地方。在这种情况下，根据进程的属性，如系统进程、输入输出进程等，进程被分为不同的类别。因此，我们得到了 n 类进程的“n”个队列。每个队列都被分配了优先级，并且可以使用自己的调度算法，这使得同时使用许多调度算法变得方便。一般来说，队列的最高层具有最高优先级，当我们移动到较低层时，优先级会降低。如果上层相对于下层具有绝对优先权，那么它是不可抢占的，否则如果时间片被划分在不同的队列中，那么它在本质上变成可抢占的。

*   **优势:**
    这个算法的主要优势是我们可以使用各种算法，比如 FCFS、SSJF、LJF 等。同时在不同的队列中。
*   **缺点:**
    最底层的进程存在饥饿问题。

**2。[先到先得(FCFS)调度算法](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/) :**
最简单的也是[非抢占式调度算法](https://www.geeksforgeeks.org/preemptive-and-non-preemptive-scheduling/)。在先到先得(FCFS)中，进程按照到达的顺序分配给 CPU。使用队列数据结构来实现 FCFS 调度算法。当中央处理器空闲时，位于就绪队列头部的进程被分配给中央处理器。然后，正在运行的进程将从队列中删除。当一个新的进程进入就绪队列时，它被放在就绪队列的尾部。

**FCFS 与多级队列调度的区别:**

<center>

| 先到先得 | 多级队列调度 |
| --- | --- |
| 先到先服务是一种非抢占式调度算法。 | MLQ 可以不先发制人，也可以根据情况先发制人。 |
| 它按照到达时间的升序执行过程。 | 进程的执行取决于该进程所属的特定队列级别的优先级。进程的进一步选择是基于特定队列中使用的算法类型。 |
| FCFS 的开销最小。 | MLQ 有一些 CPU 开销，因为它需要在队列之间切换。 |
| 先到先得的调度算法为进程提供了高响应时间。 | 响应时间可能高也可能低，这取决于多级队列中不同级别使用的算法。 |
| FCFS 在分时系统中使用不方便。 | 根据需要，它可以在任何系统中实现。 |
| 在先到先得的调度算法中，平均等待时间通常不是最小的。 | 平均等待时间取决于各级队列中使用的算法。 |
| 这是最简单的算法。 | 算法复杂，实现困难。 |
| 导致护航效应。 | 它会导致较低层次的进程饥饿。 |

</center>