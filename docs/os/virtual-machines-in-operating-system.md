# 操作系统中的虚拟机

> 原文:[https://www . geesforgeks . org/虚拟机操作系统/](https://www.geeksforgeeks.org/virtual-machines-in-operating-system/)

**虚拟机**根据我们的需求，将我们个人电脑的硬件如 CPU、磁盘驱动器、内存、NIC(网络接口卡)等抽象成很多不同的执行环境，从而给我们一种每个执行环境都是一台电脑的感觉。比如 VirtualBox。

当我们在一个操作系统上运行不同的进程时，在中央处理器调度和虚拟内存技术的帮助下，它会产生一种错觉，即每个进程都在一个有自己虚拟内存的不同处理器上运行。一个进程还有一些额外的功能，如系统调用和文件系统，是硬件无法单独提供的。虚拟机方法不提供这些附加功能，但它只提供与基本硬件相同的接口。每个进程都有一个底层计算机系统的虚拟副本。

我们创建虚拟机有几个原因，所有这些原因都与共享相同基本硬件的能力有着根本的关系，但也可以支持不同的执行环境，即同时支持不同的操作系统。

虚拟机方法的主要缺点涉及磁盘系统。让我们假设物理机只有三个磁盘驱动器，但希望支持七个虚拟机。显然，它不能为每个虚拟机分配一个磁盘驱动器，因为虚拟机软件本身需要大量磁盘空间来提供虚拟内存和假脱机。解决方案是提供虚拟磁盘。

因此，用户可以拥有自己的虚拟机。之后，他们可以运行底层机器上可用的任何操作系统或软件包。虚拟机软件涉及将多个虚拟机多编程到一个物理机上，但它不需要考虑任何用户支持软件。这种安排可以提供一种有用的方法，将设计多用户交互系统的问题分成两个更小的部分。

**优势:**

1.  There is no protection problem because each virtual machine is completely isolated from all other virtual machines.
2.  Virtual machines can provide instruction set architectures different from real computers.
3.  Simple maintenance, availability and easy recovery.

**缺点:**

1.  When multiple virtual machines are running on a host at the same time, one virtual machine may be affected by other running virtual machines, depending on the workload.
2.  Virtual machines are not as efficient as real machines when accessing hardware.