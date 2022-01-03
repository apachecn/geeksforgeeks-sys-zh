# 生产者消费者使用信号量的问题|集合 1

> 原文:[https://www . geesforgeks . org/生产者-消费者-问题-使用-信号量-set-1/](https://www.geeksforgeeks.org/producer-consumer-problem-using-semaphores-set-1/)

**先决条件–**[操作系统中的信号量](https://www.geeksforgeeks.org/semaphores-operating-system/)、[进程间通信](https://www.geeksforgeeks.org/inter-process-communication/)
生产者消费者问题是经典的同步问题。我们可以通过使用信号量来解决这个问题。

A [**信号量**](https://www.geeksforgeeks.org/semaphores-in-process-synchronization/) S 是一个整数变量，只能通过两个标准操作访问:wait()和 signal()。
wait()操作将信号量的值减少 1，signal()操作将其值增加 1。

```
wait(S){
while(S<=0);   // busy waiting
S--;
}

signal(S){
S++;
}
```

信号量有两种类型:

1.  **二元信号量–**这和互斥锁类似，但不是一回事。它只能有两个值-0 和 1。它的值被初始化为 1。用于实现多工序临界截面问题的求解。

2.  **计数信号量–**它的值可以在不受限制的域范围内变化。它用于控制对具有多个实例的资源的访问。

**问题陈述–**我们有一个固定大小的缓冲区。生产者可以生产一个项目，并可以放入缓冲区。消费者可以挑选物品并消费它们。我们需要确保当生产者将一个项目放入缓冲区时，消费者不应该消费任何项目。在这个问题中，缓冲区是关键部分。

为了解决这个问题，我们需要两个计数信号量——满和空。“满”跟踪任何给定时间缓冲区中的项目数，“空”跟踪未占用的插槽数。

**信号量初始化–**
互斥= 1
满= 0 //最初，所有槽都是空的。因此，满槽为 0
空= n //所有槽最初都是空的

**生产商解决方案–**

```
do{

//produce an item

wait(empty);
wait(mutex);

//place in buffer

signal(mutex);
signal(full);

}while(true)
```

当生产者生产一个项目，那么“空”的值减少 1，因为一个槽将被填满。互斥量的值也被减少，以防止消费者访问缓冲区。现在，生产者已经放置了物品，因此“满”的值增加 1。互斥量的值也增加了 1，因为生产者的任务已经完成，消费者可以访问缓冲区。

**消费者解决方案–**

```
do{

wait(full);
wait(mutex);

// remove item from buffer

signal(mutex);
signal(empty);

// consumes item

}while(true)
```

由于消费者正在从缓冲区中删除一个项目，因此“full”的值减少了 1，mutex 的值也减少了，因此生产者此时无法访问缓冲区。现在，消费者已经消费了该物品，因此“空”的值增加了 1。互斥量的值也增加了，这样生产者就可以访问缓冲区了。

参见实现–[在 Java 中使用信号量的生产者-消费者解决方案|第 2 集](https://www.geeksforgeeks.org/producer-consumer-solution-using-semaphores-java/)