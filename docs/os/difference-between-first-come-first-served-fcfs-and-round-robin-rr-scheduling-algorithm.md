# 先到先得(FCFS)和循环调度算法的区别

> 原文:[https://www . geeksforgeeks . org/先来后到-FCFS-和-round-robin-RR-scheduling-algorithm/](https://www.geeksforgeeks.org/difference-between-first-come-first-served-fcfs-and-round-robin-rr-scheduling-algorithm/)

[**【先到先得】调度算法**](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/) **:**
先到先得(FCFS)是最简单的[非抢占式调度算法](https://www.geeksforgeeks.org/preemptive-and-non-preemptive-scheduling/)。在先到先得(FCFS)中，进程按照到达的顺序分配给 CPU。使用队列数据结构来实现 FCFS 调度算法。当中央处理器空闲时，位于就绪队列头部的进程被分配给中央处理器。然后，正在运行的进程将从队列中删除。当一个新的进程进入就绪队列时，它被放在就绪队列的尾部。

[**循环调度算法**](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) **:**
循环调度算法是为分时系统设计的。这种算法就是抢占式调度算法。在循环调度算法中，一种称为时间段或时间片的小时间单位，CPU 为其提供给每个作业。CPU 分配给每个作业的持续时间等于循环顺序中的时间量。这个时间量、时间片或时间间隔通常在 10 到 100 毫秒的数量级。循环调度算法中的就绪队列被视为循环队列。

先到先得和循环调度算法的区别如下:

<figure class="table">

| 没有。 | 先到先得 | 循环赛 |
| --- | --- | --- |
| 1. | 先到先服务是一种非抢占式调度算法。 | 循环调度是抢占式调度算法。 |
| 2. | FCFS 的开销最小。 | 而 RR 开销较小，因为需要记录经过的时间，然后切换导致开销的进程。 |
| 3. | 先到先得的调度算法为进程提供了高响应时间。 | 在循环调度算法中，对于较短的进程，响应时间非常短。 |
| 3. | FCFS 在分时系统中使用不方便。 | 它主要是为分时系统设计的，因此使用方便。 |
| 5. | 在先到先得的调度算法中，平均等待时间通常不是最小的。 | 在循环调度算法中，平均等待时间最小。 |
| 6. | 该过程只是按照它们到达 FCFS 的顺序进行处理。 | 它在处理上类似于 FCFS，但使用了时间量子。 |

</figure>