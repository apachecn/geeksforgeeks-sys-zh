# 操作系统|流程管理|问题 6

> 原文:[https://www . geesforgeks . org/operating-systems-process-management-question-8/](https://www.geeksforgeeks.org/operating-systems-process-management-question-8/)

三个并发进程 X、Y 和 Z 执行三个不同的代码段，这些代码段访问和更新某些共享变量。进程 X 对信号量 a、b 和 c 执行 P 操作(即等待)；进程 Y 对信号量 b、c、d 执行 P 操作；进程 Z 在进入各自的代码段之前，对信号量 c、d 和 a 执行 P 操作。在完成其代码段的执行后，每个进程在其三个信号量上调用 V 操作(即信号)。所有信号量都是初始化为 1 的二进制信号量。以下哪一项代表进程调用 P 操作的无死锁顺序？(GATE CS 2013)
**(A)**X:P(A)P(B)P(C)Y:P(B)P(C)P(D)Z:P(C)P(D)P(A)
**(B)**X:P(B)P(A)P(C)Y:P(B)P(C)P(D)Z:P(A)P(C)P(D)
**(C)**想象一个情况，流程 X 获得了 a，流程 Y 获得了 b，流程 Z 获得了 c 和 d，现在有循环等待。

选项 C 也可能导致死锁。想象一个情况，进程 X 获得了 b，进程 Y 获得了 c，进程 Z 获得了 a，现在有循环等待。

选项 D 也可能导致死锁。想象一个情况，进程 X 获得了 a 和 b，进程 Y 获得了 c，X 和 Y 循环等待对方。

见[http://www . eee . metu . edu . tr/~ hali ci/courses/442/Ch5 % 20 deadlocks . pdf](http://www.eee.metu.edu.tr/~halici/courses/442/Ch5%20Deadlocks.pdf)

考虑选项 A)例如，这里所有 3 个进程都是并发的，所以 X 会得到信号量 A，Y 会得到 b，Z 会得到 c，现在 X 被 b 阻塞了，Y 被 c 阻塞了，Z 得到 d，被 A 阻塞了，这样就会导致死锁。

类似地，我们可以计算出，对于 B)，完成顺序是 Z，X，然后是 y

本问题重复[http://geeksquiz.com/gate-gate-cs-2013-question-16/](http://geeksquiz.com/gate-gate-cs-2013-question-16/)

观看极客博客视频讲解:

[本题小考](https://www.geeksforgeeks.org/operating-systems-gq/process-synchronization-gq/)