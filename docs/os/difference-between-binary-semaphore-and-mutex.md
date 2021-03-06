# 二进制信号量和互斥量的区别

> 原文:[https://www . geesforgeks . org/二进制信号量和互斥量之间的差异/](https://www.geeksforgeeks.org/difference-between-binary-semaphore-and-mutex/)

先决条件–[流程同步](https://www.geeksforgeeks.org/introduction-of-process-synchronization/)

**1。[二进制信号量](https://www.geeksforgeeks.org/semaphores-in-process-synchronization/) :**
二进制信号量是只能取值 0 和 1 的信号量。它们用于通过使用信令机制实现互斥来实现锁。

这里，如果信号量的值为 0，则意味着它被锁定，因此锁定不可用。
如果信号量的值为 1，则表示它已解锁，因此锁定可用。

**2。[互斥体](https://practice.geeksforgeeks.org/problems/what-is-mutex-in-os) :**
互斥体提供互斥，生产者或消费者都可以拥有密钥(互斥体)并继续工作。只要缓冲区由生产者填充，消费者就需要等待，反之亦然。

在任何时候，只有一个线程可以使用整个缓冲区。这个概念可以用信号量来概括。

**二进制信号量和互斥量的区别:**

<center>

| 二元信号量 | 互斥（体）… |
| 它的功能基于信号机制 | 它的功能基于锁定机制 |
| 优先级高于当前线程的线程也可以释放二进制信号量并获取锁。 | 获得互斥锁的线程只有在退出临界区时才能释放互斥锁。 |
| 信号量值根据 wait()和 signal()操作进行更改。 | 互斥值可以像锁定或解锁一样修改。 |
| 多个线程可以同时获取二进制信号量。 | 一次只能有一个线程获取互斥体 |
| 二进制信号量没有所有权。 | 互斥体有所有权，因为只有所有者才能释放锁。 |
| 它们比互斥快，因为任何其他线程/进程都可以解锁二进制信号量。 | 它们比二进制信号量慢，因为只有已经获取的线程必须释放锁。 |
| 如果您有许多资源实例，最好使用二进制信号量。 | 如果资源只有一个实例，最好使用互斥体。 |

</center>