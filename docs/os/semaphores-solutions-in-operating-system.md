# 操作系统中的信号量解决方案

> 原文:[https://www . geesforgeks . org/信号量-操作系统中的解决方案/](https://www.geeksforgeeks.org/semaphores-solutions-in-operating-system/)

一个**信号量**可以描述为一个由计数器、进程等待列表、信号和等待功能组成的对象。信号量最基本的用途是将其初始化为 1。当一个线程想要进入一个关键部分时，它会向下调用并进入该部分。当另一个线程试图做同样的事情时，操作系统会让它进入睡眠状态，因为信号量的值由于之前的 down 调用已经为零。当第一个线程完成关键部分时，它会调用，这将唤醒等待进入的另一个线程。

逻辑上，信号量 S 是一个整数变量，除了初始化之外，只能通过两个原子操作来访问:

*   **等待(S)或 P :** 如果信号量值大于 0，则递减该值。否则，请等到该值大于 0，然后递减它。
*   **信号或电压:**增加信号量的值

**占线等待信号量解决方案:**

如果一个进程处于临界区，另一个试图进入其临界区的进程必须在入口代码中连续循环。等待和信号的经典定义是–

```
wait (S) {
while (S<=0);
S--;
}
signal (S) {
S++;
}
```

**实现信号量:**n 个进程问题的关键部分

```
Shared Data : semaphore mutex ;   // initially mutex=1
Process P :
do {
wait (mutex) ;
<critical section>
signal (mutex) ;
<remainder section>
} while (1)
```

**带阻塞和唤醒的信号量解决方案:**
在繁忙等待问题中，进程在等待进入其关键部分时会浪费 CPU 周期。将等待操作修改为阻塞操作。这个过程可以自我封闭，而不是等车。将进程放入与关键部分关联的等待队列中。将信号操作修改为唤醒操作。将进程状态从等待更改为就绪。

当进程执行等待操作并发现信号量值不是正数时，进程可以阻塞自己。阻塞操作将进程置于与信号量相关联的等待队列中。在等待信号量时被阻塞的进程应该在另一个进程执行信号操作时重新启动。阻塞的进程应该通过唤醒操作重新启动，唤醒操作会将该进程置于就绪队列中。

**为了实现信号量，我们将信号量定义为记录:**

```
typedef struct {
int value ;
struct process *L ;
} semaphore ;
```

**假设两个操作:**

*   **块:**暂停调用它的进程。
*   **唤醒(P) :** 恢复被阻塞进程的执行(P)

**信号量操作定义为:**

```
wait (S) {
S.value -- ;                 
if ( S.value < 0 ) {
add this process to S.L ;
block ;
}  }
```

```
signal (S) {
S.value ++ ; 
if ( S.value <= 0 ) {
removes a process P from S.L ;
wakeup (P) ;
} }
```

**优势:**

*   信号量易于实现，并且与机器无关
*   更正很容易确定
*   信号量同时获取许多资源
*   可以有许多具有不同信号量的不同关键部分
*   不会因为繁忙的等待而浪费资源

**缺点:**

*   对信号量的访问可以来自程序中的任何地方
*   信号量和信号量控制访问的数据之间没有语言联系
*   信号量的不当使用将导致死锁或饥饿
*   没有适当使用的控制或保证