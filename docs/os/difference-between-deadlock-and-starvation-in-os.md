# 操作系统中死锁和饥饿的区别

> 原文:[https://www . geesforgeks . org/OS 中死锁和饥饿的区别/](https://www.geeksforgeeks.org/difference-between-deadlock-and-starvation-in-os/)

**[死锁](https://www.geeksforgeeks.org/introduction-of-deadlock-in-operating-system/) :**
当每个进程持有一个资源，并等待任何其他进程持有的其他资源时，就会发生死锁。死锁发生的必要条件是互斥、保持和等待、不抢占和循环等待。在这种情况下，没有进程持有一个资源并等待另一个资源被执行。例如，在下图中，流程 1 持有资源 1，等待流程 2 获取的资源 2，流程 2 等待资源 1。因此，进程 1 和进程 2 都处于死锁状态。

![](img/45dfd5dd6cc5b4174c4bcd0dff6c5611.png)

**[饥饿](https://www.geeksforgeeks.org/starvation-and-aging-in-operating-systems/) :**
饥饿是高优先级进程持续执行，低优先级进程无限期阻塞时出现的问题。在高负载的计算机系统中，稳定的高优先级进程流会阻止低优先级进程获得 CPU。在饥饿状态下，高优先级进程持续利用资源。饥饿的问题可以通过老化来解决。在老化中，长等待过程的优先级逐渐增加。

**死锁和饥饿的区别:**

<center>

| S.NO | 僵局 | 饿死 |
| 1. | 所有进程都在等待对方完成，没有一个得到执行 | 高优先级进程继续执行，低优先级进程被阻止 |
| 2. | 资源被进程阻塞 | 高优先级进程持续利用资源 |
| 3. | 必要条件互斥、保持和等待、不抢占、循环等待 | 优先级被分配给流程 |
| 4. | 也称为循环等待 | 也被称为活锁 |
| 5. | 可以通过避免死锁的必要条件来防止 | 它可以通过老化来呈现 |

</center>