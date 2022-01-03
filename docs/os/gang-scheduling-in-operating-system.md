# 操作系统中的联动调度

> 原文:[https://www . geesforgeks . org/gang-操作系统中的调度/](https://www.geeksforgeeks.org/gang-scheduling-in-operating-system/)

调度是管理资源(主要是硬件资源，如输入/输出、中央处理器、内存等)的过程。)有效地完成给定的一组任务。调度方式多为[先到先服务(FCFS)](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/)[最短作业优先(SJF)](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/)[循环赛(RR)](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) 等流程调度。有许多任务需要多个进程或线程同时工作——只有一个进程在工作，而其他进程在等待，这会危及系统。即使执行一个进程并在另一个进程上先发制人地停止，也会导致系统受到危害。

**什么是任务？**

任务是最小的逻辑工作单位。一个任务可以由多个作业组成。作业可以是子任务(类似于任务)或流程。为了完成一项任务，所有的作业必须按照特定的顺序作为一个块来工作。这些作业可能会并行或顺序运行，或者两者兼而有之。

例如——打开汽车。驾驶员必须踩下离合器和制动器，然后转动钥匙。这三个过程都必须发生，否则汽车将无法启动。在计算机科学中，我们可以在神经网络中找到类似的例子；所有边的权重必须在一个片段中更新。

**什么是帮派？**

帮派意味着任务。所以，帮派调度就是以高效的方式调度帮派。将组调度与其他调度区分开来的一点是，它将组(任务)视为一个量，并对它们进行调度。一个组可能需要多个进程或线程，或者两者的组合(线程和进程)。

成组调度使用 Outsterhout 矩阵作为数据结构来促进所有的调度任务。它是一个二维矩阵，其中一行代表一个时间片，一列代表一个进程或线程。

<figure class="table">

|   | 第一亲代 | P2 | P3 | P4 | 孕烯醇酮 |
| 时间片 0 | J1 | J1 | J1 | J1 | J1 |
| 时间片 1 | J2 | J2 | J2 | J2 | J2 |
| 时间片 2 | JBOY3 乐队 | JBOY3 乐队 | J4 | J4 | J4 |

上表演示了如何形成外包矩阵和安排作业。J1-J4 代表帮派，P1-P5 代表流程。请注意，一些文献也有以行和时间片为列的过程。

由于成组调度包括多个进程和线程，因此需要同步。大体上有两种同步方法。

1.  并发分组调度:同步模块协调所有的调度。所有的帮派运行一段特定的时间间隔' t '，然后它被解释，另一个帮派可以开始。
2.  共享调度系统:资源利用率相同的帮派被收集并执行一段固定的时间。固定周期每次都可能改变，并且该时间大于或等于任务的最小时间，直到这些任务不可抢占。

与进程调度一样，也有各种类型的调度组，即:

1.  帮派包(BoG)
2.  先到先得(AFCFS)
3.  最大的帮派先到先得(LGFS)
4.  成对成组调度
5.  调度算法

在[链接中可以找到更多关于组调度类型的详细信息。](https://en.wikipedia.org/wiki/Gang_scheduling#:~:text=In%20computer%20science%2C%20gang%20scheduling,run%20simultaneously%20on%20different%20processors.&text=During%20execution%2C%20coordinated%20context%20switching,those%20in%20the%20next%20row.)

</figure>