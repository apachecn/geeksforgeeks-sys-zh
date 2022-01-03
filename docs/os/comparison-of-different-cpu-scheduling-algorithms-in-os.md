# 操作系统中不同 CPU 调度算法的比较

> 原文:[https://www . geesforgeks . org/不同 cpu 调度算法比较 in-os/](https://www.geeksforgeeks.org/comparison-of-different-cpu-scheduling-algorithms-in-os/)

调度算法用于估计分配给进程和线程所需的 CPU 时间。任何 [CPU 调度算法](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)的首要目标都是让 CPU 尽可能忙碌，以提高 CPU 利用率。

## 调度算法

**1。** [**【先到先得(FCFS)**](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/) :顾名思义，作业是在先到先得的基础上执行的。这是一种基于先进先出的简单算法。在就绪队列中排在第一位的进程可以首先访问 CPU。如果到达时间少，那么进程很快就会得到 CPU。如果第一个进程的爆发时间是所有作业中最长的，它可能会受到护卫效应的影响。

**2。** [**【最短作业优先(SJF)**](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/) :又称最短作业优先或最短作业次优，是一种非抢占式算法，易于在批处理系统中实现，在最小化等待时间方面做得最好。它遵循的策略是，选择执行时间最短的进程进行下一次执行。

**3。** [**最长作业优先调度(LJF)**](https://www.geeksforgeeks.org/longest-job-first-ljf-cpu-scheduling-algorithm/) :最长作业优先(LJF)是非抢先版。该算法也基于进程的突发时间。根据突发时间，进程被放入就绪队列，具有最大突发时间的进程被首先处理。

**4。** [**最长剩余时间第一调度(LRTF)**](https://www.geeksforgeeks.org/longest-remaining-time-first-lrtf-cpu-scheduling-algorithm/) :抢先版的 LJF 是 LRTF。这里将首先考虑剩余 CPU 时间最长的进程，然后再进行处理。在一段时间间隔后，它将检查是否有另一个具有更多突发时间的进程到达该时间。如果任何其他进程有更多剩余的突发时间，那么正在运行的进程将被该进程抢先。

**5。** [**【最短剩余时间优先(SRTF)**](https://www.geeksforgeeks.org/introduction-of-shortest-remaining-time-first-srtf-algorithm/) :这个算法是基于 SJF 的，这是 SJF 的抢先版。在该调度算法中，具有最小剩余突发时间的进程首先被执行，并且它可能被以较短执行时间到达的新作业抢占。

**6。** [**循环调度(RR)**](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) :是一种抢占式的调度算法，给每个进程一个固定的时间，称为 quantum 来执行。此时，允许一个进程执行一个量程，然后抢占，然后执行另一个进程。通过这种方式，可以在进程之间进行上下文切换，以保存这些被抢占进程的状态。

**7。** [**优先级调度**](https://www.geeksforgeeks.org/program-for-priority-cpu-scheduling-set-1/) :是一种非抢占式算法，在批处理系统中工作，每个进程都被赋予优先级，优先级最高的进程先执行。这可能导致其他进程的饥饿。

**8。** [**多级队列调度**](https://www.geeksforgeeks.org/multilevel-queue-mlq-cpu-scheduling/) :在这个调度中，多个队列都有自己的调度算法，用具有相同特性的进程来维护。为此，将为要执行的作业的每个队列分配优先级。

**9。** [**多级-反馈-队列调度器**](https://www.geeksforgeeks.org/multilevel-feedback-queue-scheduling-mlfq-cpu-scheduling/) :它定义了多个队列以及每个队列的调度算法。该算法用于确定何时升级进程，何时降级进程，还用于确定进程将进入的队列以及该进程何时需要服务。

***注意:**SJF 调度算法是假设性的，不可实现，因为不运行它就不可能确定任何进程的突发时间。SJF 是一个基准算法，因为它提供了比任何其他调度算法*最短的等待时间

### 不同 CPU 调度算法的对比分析

下面简单对比一下不同的 CPU 调度算法:

<figure class="table">

| 算法 | 分配是 | 复杂性 | 平均等待时间 | 先占 | 饿死 | 表演 |
| --- | --- | --- | --- | --- | --- | --- |
| FirstCome | 根据进程的到达时间，分配 CPU。 | 不复杂 | 大的。 | 不 | 不 | 缓慢的性能 |
| SJF | 基于最低的 CPU 突发时间(BT)。 | 比 FCFS 更复杂 | 小于 FCFS | 不 | 是 | 最短平均等待时间 |
| LJFS | 基于最高 CPU 突发时间(BT) | 比 FCFS 更复杂 | 取决于一些度量，例如到达时间、过程大小等。 | 不 | 是 | 大周转时间 |
| LRTF(爱尔兰特种部队) | 与 LJFS 相同，CPU 的分配基于最高的 CPU 突发时间(BT)。但它是先发制人的 | 比 FCFS 更复杂 | 取决于一些度量，例如到达时间、过程大小等。 | 是 | 是 | 优先考虑较长的工作 |
| SRTF(外勤人员) | 与 SJF 相同，中央处理器的分配基于最低的中央处理器突发时间。但它是先发制人的。 | 比 FCFS 更复杂 | 取决于一些度量，例如到达时间、过程大小等 | 是 | 是 | 优先考虑短期工作 |
| 乡邮投递路线 | 根据进程的顺序，以固定的时间量到达 | 复杂性取决于 TQ 的大小 | 与“SJF”和“优先级”计划相比，该计划规模较大。 | 不 | 不 | 每个过程都有一个相当固定的时间 |
| 优先优先 | 按照优先级。优先级较高的任务首先执行 | 这种类型不太复杂 | 小于 FCFS | 是 | 是 | 性能良好，但存在饥饿问题 |
| 优先非优先 | 按照优先级。通过监视新进入的更高优先级的作业 | 这种类型没有优先级抢占复杂 | 比 FCFS 更小 | 不 | 是 | 最有利于批处理系统 |
| MLQ | 根据驻留在较大队列优先级中的进程 | 比优先级调度算法更复杂 | 小于 FCFS | 不 | 是 | 性能良好，但存在饥饿问题 |
| MFLQ | 按照流程排一个更大的优先级队列。 | 它是最复杂的，但是它的复杂程度取决于 TQ 的大小 | 在许多情况下小于所有调度类型 | 不 | 不 | 良好的性能 |

</figure>