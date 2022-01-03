# 在 Java 中使用线程的生产者-消费者解决方案

> 原文:[https://www . geesforgeks . org/生产者-消费者-解决方案-使用-线程-java/](https://www.geeksforgeeks.org/producer-consumer-solution-using-threads-java/)

在计算中，生产者-消费者问题(也称为有界缓冲区问题)是多进程同步问题的经典例子。这个问题描述了两个进程，生产者和消费者，它们共享一个公共的、固定大小的缓冲区作为队列。

*   生产者的工作是生成数据，将其放入缓冲区，然后重新开始。
*   与此同时，消费者正在消耗数据(即从缓冲区中删除数据)，一次一个。

**问题**
确保生产者不会试图在缓冲区已满时向缓冲区添加数据，消费者不会试图从空缓冲区移除数据。

**解决方案**
如果缓冲区已满，生产者要么进入睡眠状态，要么丢弃数据。下一次消费者从缓冲区中移除一个项目时，它会通知生产者，生产者会再次开始填充缓冲区。同样，如果消费者发现缓冲区是空的，他可以进入睡眠状态。生产者下一次将数据放入缓冲区时，会唤醒沉睡的消费者。
不充分的解决方案可能会导致死锁，两个进程都在等待被唤醒。
**推荐阅读-**[JAVA 多线程](https://www.geeksforgeeks.org/multithreading-in-java/)[JAVA 同步](https://www.geeksforgeeks.org/synchronized-in-java/)[线程间通信](https://www.geeksforgeeks.org/inter-thread-communication-java/)

**生产者消费者类的实现**

*   一个**链接列表**–存储队列中的作业列表。
*   **可变容量**–检查列表是否已满
*   一种控制从列表中插入和提取的机制，这样，如果列表已满，我们就不会插入，如果列表为空，我们就不会从列表中删除。

*注意:建议在离线 IDE 上测试以下程序，因为无限循环和休眠方法可能会导致其在任何在线 IDE 上超时*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement solution of producer
// consumer problem.

import java.util.LinkedList;

public class Threadexample {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Object of a class that has both produce()
        // and consume() methods
        final PC pc = new PC();

        // Create producer thread
        Thread t1 = new Thread(new Runnable() {
            @Override
            public void run()
            {
                try {
                    pc.produce();
                }
                catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        // Create consumer thread
        Thread t2 = new Thread(new Runnable() {
            @Override
            public void run()
            {
                try {
                    pc.consume();
                }
                catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        // Start both threads
        t1.start();
        t2.start();

        // t1 finishes before t2
        t1.join();
        t2.join();
    }

    // This class has a list, producer (adds items to list
    // and consumer (removes items).
    public static class PC {

        // Create a list shared by producer and consumer
        // Size of list is 2.
        LinkedList<Integer> list = new LinkedList<>();
        int capacity = 2;

        // Function called by producer thread
        public void produce() throws InterruptedException
        {
            int value = 0;
            while (true) {
                synchronized (this)
                {
                    // producer thread waits while list
                    // is full
                    while (list.size() == capacity)
                        wait();

                    System.out.println("Producer produced-"
                                       + value);

                    // to insert the jobs in the list
                    list.add(value++);

                    // notifies the consumer thread that
                    // now it can start consuming
                    notify();

                    // makes the working of program easier
                    // to  understand
                    Thread.sleep(1000);
                }
            }
        }

        // Function called by consumer thread
        public void consume() throws InterruptedException
        {
            while (true) {
                synchronized (this)
                {
                    // consumer thread waits while list
                    // is empty
                    while (list.size() == 0)
                        wait();

                    // to retrieve the ifrst job in the list
                    int val = list.removeFirst();

                    System.out.println("Consumer consumed-"
                                       + val);

                    // Wake up producer thread
                    notify();

                    // and sleep
                    Thread.sleep(1000);
                }
            }
        }
    }
}
```

**输出:**

```
Producer produced-0
Producer produced-1
Consumer consumed-0
Consumer consumed-1
Producer produced-2
```

**重要点**

*   在 **PC 类**(一个同时具有生产和消费方法的类)中，添加了一个作业的链接列表和列表的容量，以检查如果列表已满，生产者是否不生产。
*   在**生产者类**中，该值被初始化为 0。
    *   此外，我们有一个无限的外部循环来插入列表中的值。在这个循环中，我们有一个同步块，这样一次只有一个生产者或消费者线程运行。
    *   在将作业添加到列表之前，会有一个内部循环来检查作业列表是否已满，生产者线程会放弃 PC 上的固有锁并进入等待状态。
    *   如果列表为空，控件将传递到循环下方，并在列表中添加一个值。
*   在**消费者类**中，我们再次有一个无限循环来从列表中提取一个值。
    *   在内部，我们还有一个检查列表是否为空的内部循环。
    *   如果它是空的，那么我们让消费者线程放弃 PC 上的锁，并将控制权交给生产者线程，以产生更多的作业。
    *   如果列表不是空的，我们循环并从列表中移除一个项目。
*   在这两种方法中，我们都在所有语句的末尾使用 notify。原因很简单，一旦你有东西在列表中，你可以让消费线程消费它，或者如果你消费了东西，你可以让生产者生产一些东西。
*   两种方法末尾的 sleep()只是让程序的输出以分步的方式运行，而不是一次显示所有内容，这样您就可以看到程序中实际发生的事情。

**运动**:

*   建议读者使用 if 条件代替内环来检查边界条件。
*   试着让你的程序生产一个项目，然后在生产者生产任何其他项目之前让消费者立即消费它。

参考–[https://en . Wikipedia . org/wiki/Productor % E2 % 80% 93 consumer _ problem](https://en.wikipedia.org/wiki/Producer%E2%80%93consumer_problem)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。