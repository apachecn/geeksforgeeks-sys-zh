# 在 Java 中使用信号量的生产者-消费者解决方案|第 2 集

> 原文:[https://www . geesforgeks . org/生产者-消费者-解决方案-使用-信号量-java/](https://www.geeksforgeeks.org/producer-consumer-solution-using-semaphores-java/)

先决条件–[Java 中的信号量](https://www.geeksforgeeks.org/semaphore-in-java/)、[进程间通信](https://www.geeksforgeeks.org/inter-process-communication/)、[生产者消费者使用信号量的问题|集合 1](https://www.geeksforgeeks.org/producer-consumer-problem-using-semaphores-set-1/)

在计算中，生产者-消费者问题(也称为有界缓冲区问题)是多进程同步问题的经典例子。这个问题描述了两个进程，生产者和消费者，它们共享一个公共的、固定大小的缓冲区作为队列。

*   生产者的工作是生成数据，将其放入缓冲区，然后重新开始。
*   与此同时，消费者正在消耗数据(即从缓冲区中删除数据)，一次一个。

**问题:**确保生产者不会试图在缓冲区已满时向缓冲区添加数据，消费者不会试图从空缓冲区移除数据。

**解决方案:**如果缓冲区已满，生产者要么进入睡眠状态，要么丢弃数据。下一次消费者从缓冲区中移除一个项目时，它会通知生产者，生产者会再次开始填充缓冲区。同样，如果消费者发现缓冲区是空的，他可以进入睡眠状态。生产者下一次将数据放入缓冲区时，会唤醒沉睡的消费者。
**不充分的解决方案可能会导致僵局**，两个进程都在等待被唤醒。

在帖子[使用 Java 中线程的生产者-消费者解决方案中，](https://www.geeksforgeeks.org/producer-consumer-solution-using-threads-java/)我们已经通过使用[线程间通信](https://www.geeksforgeeks.org/inter-thread-communication-java/) (wait()、notify()、sleep())讨论了上述解决方案。在这篇文章中，我们将使用[信号量](https://www.geeksforgeeks.org/semaphore-in-java/)来实现同样的功能。

**下面的解由四类组成:**

1.  **Q** :你正在尝试同步的队列
2.  **生成器:**正在生成队列条目的线程对象
3.  **消耗者:**消耗队列条目的线程对象
4.  **PC :** 创建单个 Q、生产者和消费者的驱动程序类。

```
// Java implementation of a producer and consumer
// that use semaphores to control synchronization.

import java.util.concurrent.Semaphore;

class Q {
    // an item
    int item;

    // semCon initialized with 0 permits
    // to ensure put() executes first
    static Semaphore semCon = new Semaphore(0);

    static Semaphore semProd = new Semaphore(1);

    // to get an item from buffer
    void get()
    {
        try {
            // Before consumer can consume an item,
            // it must acquire a permit from semCon
            semCon.acquire();
        }
        catch (InterruptedException e) {
            System.out.println("InterruptedException caught");
        }

        // consumer consuming an item
        System.out.println("Consumer consumed item : " + item);

        // After consumer consumes the item,
        // it releases semProd to notify producer
        semProd.release();
    }

    // to put an item in buffer
    void put(int item)
    {
        try {
            // Before producer can produce an item,
            // it must acquire a permit from semProd
            semProd.acquire();
        }
        catch (InterruptedException e) {
            System.out.println("InterruptedException caught");
        }

        // producer producing an item
        this.item = item;

        System.out.println("Producer produced item : " + item);

        // After producer produces the item,
        // it releases semCon to notify consumer
        semCon.release();
    }
}

// Producer class
class Producer implements Runnable {
    Q q;
    Producer(Q q)
    {
        this.q = q;
        new Thread(this, "Producer").start();
    }

    public void run()
    {
        for (int i = 0; i < 5; i++)
            // producer put items
            q.put(i);
    }
}

// Consumer class
class Consumer implements Runnable {
    Q q;
    Consumer(Q q)
    {
        this.q = q;
        new Thread(this, "Consumer").start();
    }

    public void run()
    {
        for (int i = 0; i < 5; i++)
            // consumer get items
            q.get();
    }
}

// Driver class
class PC {
    public static void main(String args[])
    {
        // creating buffer queue
        Q q = new Q();

        // starting consumer thread
        new Consumer(q);

        // starting producer thread
        new Producer(q);
    }
}
```

输出:

```
Producer produced item : 0
Consumer consumed item : 0
Producer produced item : 1
Consumer consumed item : 1
Producer produced item : 2
Consumer consumed item : 2
Producer produced item : 3
Consumer consumed item : 3
Producer produced item : 4
Consumer consumed item : 4

```

**说明:**如您所见，对 **put()** 和 **get( )** 的调用是同步的，即对 put()的每个调用后面都有一个 get()的调用，没有遗漏任何项目。如果没有信号量，在没有匹配的 get()调用的情况下，将会发生多次 put()调用，导致项目丢失。(为了证明这一点，移除信号量代码并观察结果。)

**put()和 get()调用的顺序由两个信号量处理:** **semProd** 和 **semCon** 。

*   在 put()可以生产一个项目之前，它必须获得 semProd 的许可。生产完产品后，它会发布 semCon。
*   在 get()可以消费一个项目之前，它必须获得 semCon 的许可。消耗完项目后，它会释放 semProd。
*   这种“给予和接受”机制确保了对 put()的每个调用之后必须有对 get()的调用。
*   还要注意，semCon 是在没有可用许可的情况下初始化的。这确保 put()首先执行。设置初始同步状态的能力是信号量更强大的方面之一。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。