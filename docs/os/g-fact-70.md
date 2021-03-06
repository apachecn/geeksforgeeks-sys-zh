# 同步临界区

> 原文:[https://www.geeksforgeeks.org/g-fact-70/](https://www.geeksforgeeks.org/g-fact-70/)

[**【临界段】**](http://en.wikipedia.org/wiki/Critical_section) **:**
当多个进程访问同一个代码段时，该段称为临界段。关键部分包含需要同步以保持数据变量一致性的共享变量或资源。
简单来说，关键部分是一组需要原子执行的指令/语句或代码区域([阅读本文](https://www.geeksforgeeks.org/g-fact-57/)了解原子性)，例如访问资源(文件、输入或输出端口、全局数据等)。).

在并发编程中，如果一个线程试图改变共享数据的值，同时另一个线程试图读取该值(即线程间的数据竞争)，结果是不可预测的。

对要同步的共享变量(共享内存、共享文件、共享端口等)的访问。很少有编程语言内置同步支持。

在编写内核模式编程(设备驱动程序、内核线程等)时，理解竞争条件的重要性至关重要。).因为程序员可以直接访问和修改内核数据结构。

![](img/b115b801a9d2ec2448b65cb19db3d4c9.png)

关键部分的简单解决方案可以如下所示:

```
acquireLock();
Process Critical Section
releaseLock();
```

线程必须在执行关键部分之前获取锁。锁只能由一个线程获取。在上面的伪代码中有各种方法来实现锁。让我们在以后的文章中讨论它们。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。