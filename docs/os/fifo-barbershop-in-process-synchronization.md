# 先进先出理发店正在同步

> 原文:[https://www . geesforgeks . org/FIFO-进程中理发店-同步/](https://www.geeksforgeeks.org/fifo-barbershop-in-process-synchronization/)

**概述:**
在进程同步中，存在睡眠理发师问题，这里讨论[。](https://www.geeksforgeeks.org/sleeping-barber-problem-in-process-synchronization/)但是在上面的解决方案中，并不能保证顾客按照他们到达理发店的顺序被服务，即不能保证顾客以先进先出的方式进入。在上面讨论的解决方案中。

*   直到 *n* 顾客可以到达，然后给顾客发信号，等待理发师空闲或清醒。
*   一旦理发师空闲或醒来，任何顾客都可以继续。

**先决条件–**
[进程同步中的睡眠理发师问题](https://www.geeksforgeeks.org/sleeping-barber-problem-in-process-synchronization/)

**问题陈述:**
我们想要一个解决方案，按照顾客到达店内的顺序为他们提供服务。

**解决方案–**
为了维护客户的秩序，我们应该实现一个数据结构，称为队列，它遵循先进先出的原则。将使用信号量列表，而不是为客户使用单个信号量。从现在开始，我们将客户视为线索。因此对于线程，将使用一个信号量列表，命名为*队列。*这种方法背后的直觉是:

1.  当每个线程进入理发店时，它会创建一个线程并将其放入*队列。*
2.  每个线程都等待自己的信号量，而不是等待理发师空闲。
3.  每当理发师空闲或醒来时，他就从*队列*中取出线，并发出信号让它走向椅子。

**注意–**
理发师必须获得**互斥体**才能访问*队列*。因此，**互斥体**将使用一些信号量来控制线程对*队列的访问，*和理发师处理*队列。*

**先进先出理发店问题的算法:**

```
Semaphore customer = 0;
Semaphore mutex = 1;
Semaphore barberDone = 0;
Semaphore customerDone = 0;
customer = 0;
Queue queue;

/* Number of chairs available */
n = 4

Customer
{
/* Protects the seat, to mark the present customer */
    Semaphore self = 0;

    mutex.wait();

    if(customer == n){
    mutex.signal();

/* Invoke the barber */
    customer += 1;          

/* Adds the thread inside the queue */
    queue.push(self);

    mutex.signal();
    customer.signal();
    self.wait();

/* gets the hair cut */
    customerDone.signal();
    barberDone.wait();

/* Decrements the number of thread by one */
    mutex . wait ();
    customers -= 1;
    mutex . signal ();
}

Barber{
/* To store the current thread*/
    Semaphore curr;

    customer.wait();
    mutex.wait();

/* Gets the current thread*/
    curr = queue.pop();
    mutex.signal();

    curr.signal();

    /* gets the hair cut */
    customerDone.waitl();
    barberDone.signal();

}
```

**注意–**
*自身*和 *curr* 不过是指当前线程的信号量。