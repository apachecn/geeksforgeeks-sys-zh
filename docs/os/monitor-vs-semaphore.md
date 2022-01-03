# 监视器 vs 信号量

> 原文:[https://www.geeksforgeeks.org/monitor-vs-semaphore/](https://www.geeksforgeeks.org/monitor-vs-semaphore/)

信号量和监视器都用于解决[临界区](https://www.geeksforgeeks.org/g-fact-70/)问题(因为它们允许进程访问[互斥](https://practice.geeksforgeeks.org/problems/what-is-mutual-exclusion)中的共享资源)，并在多处理环境中实现[进程同步](https://www.geeksforgeeks.org/introduction-of-process-synchronization/)。

**[监视器](https://www.geeksforgeeks.org/monitors-in-process-synchronization/) :**
一个监视器类型的高级同步构造。它是一种抽象数据类型。监视器类型包含共享变量和对共享变量进行操作的一组过程。

当任何进程想要访问监视器中的共享变量时，它需要通过过程来访问它。这些进程排成一个队列，只有在前一个进程释放共享变量时才提供访问。一次只能有一个进程在监视器中处于活动状态。监视器有条件变量。

**语法:**

```
monitor  {

    //shared variable declarations
    data variables;
    Procedure P1() { ... }
    Procedure P2() { ... }
    .
    .
    .
    Procedure Pn() { ... }

} 
```

**[信号量](https://www.geeksforgeeks.org/semaphores-in-process-synchronization/) :**
信号量是低级对象。信号量是非负整数变量。信号量的值表示系统中可用的共享资源的数量。信号量的值只能通过两个函数修改，即 *wait()* 和 *signal()* 操作(初始化除外)。

当任何进程访问共享资源时，它对信号量执行 wait()操作，当进程释放共享资源时，它对信号量执行 signal()操作。信号量没有条件变量。当一个进程正在修改信号量的值时，没有其他进程可以同时修改信号量的值。

信号量进一步分为两类:

1.  二元信号量
2.  计数信号量

**语法:**

```
    // Wait Operation
    wait(Semaphore S) {   
        while (S<=0);
            S--;
    }
    // Signal Operation
    signal(Semaphore S) {
        S++;
    } 
```

**显示器的优势:**

*   监视器比信号量更容易实现。
*   监视器中的互斥是自动的，而在信号量中，互斥需要显式实现。
*   监视器可以克服使用信号量时出现的定时错误。
*   共享变量对监视器中的所有进程都是全局的，而共享变量隐藏在信号量中。

**信号量的优势:**

*   信号量是机器独立的(因为它们是在内核服务中实现的)。
*   与监视器不同，信号量允许多个线程访问关键部分。
*   在信号量中没有旋转，因此不会因为没有繁忙的等待而浪费资源。