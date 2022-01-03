# 硬件同步算法:解锁和锁定、测试和设置、交换

> 原文:[https://www . geesforgeks . org/硬件-同步-算法-解锁-锁定-测试-设置-交换/](https://www.geeksforgeeks.org/hardware-synchronization-algorithms-unlock-and-lock-test-and-set-swap/)

[进程同步](https://www.geeksforgeeks.org/introduction-of-process-synchronization/)当两个并发运行的进程共享相同的数据或相同的变量时，就会出现问题。该变量的值在被第二个进程使用之前可能无法正确更新。这种情况被称为绕场赛跑。这个问题有软件也有硬件解决方案。在本文中，我们将讨论处理同步问题的最有效的硬件解决方案及其实现。

解决进程同步问题的硬件方法有三种算法:

1.  测试和设置
2.  交换
3.  解锁并锁定

许多操作系统中的硬件指令有助于有效解决关键部分的问题。

**1。测试和设置:**
这里，共享变量是锁，初始化为假。TestAndSet(lock)算法是这样工作的——它总是返回发送给它的任何值，并将 lock 设置为 true。第一个进程将立即进入临界区，因为 TestAndSet(锁)将返回 false，它将脱离 while 循环。其他进程现在无法进入，因为 lock 设置为 true，所以 while 循环继续为 true。相互排斥得到保证。一旦第一个进程脱离了临界区，lock 就被更改为 false。所以，现在其他流程可以一个一个进入了。也确保了进展。然而，在第一个过程之后，任何过程都可以进入。没有维护队列，因此任何发现锁再次为假的新进程都可以进入。所以有界等待是不确定的。

**测试并设置伪代码–**

```
//Shared variable lock initialized to false
boolean lock;

boolean TestAndSet (boolean &target){
    boolean rv = target;
    target = true;
    return rv;
}

while(1){
    while (TestAndSet(lock));
    critical section
    lock = false;
    remainder section
}

```

**2。交换:**
交换算法很像 TestAndSet 算法。不是在交换功能中直接将 lock 设置为 true，而是将 key 设置为 true，然后与 lock 交换。所以，同样，当一个进程处于临界区时，没有其他进程可以进入它，因为 lock 的值是真的。相互排斥得到保证。同样，在临界区之外，lock 被更改为 false，因此任何找到它的进程都无法进入临界区。确保取得进展。然而，同样的原因也不能保证有界限的等待。

**交换伪代码–**

```
// Shared variable lock initialized to false 
// and individual key initialized to false;

boolean lock;
Individual key;

void swap(boolean &a, boolean &b){
    boolean temp = a;
    a = b;
    b = temp;
}

while (1){
    key = true;
    while(key)
         swap(lock,key);
    critical section
    lock = false;
    remainder section
} 
```

**3。解锁和锁定:**
解锁和锁定算法使用 TestAndSet 来调节锁定的值，但是它为每个进程添加另一个值，等待[i]，该值检查一个进程是否一直在等待。一个就绪队列被维护在临界区的进程中。接下来进入的所有进程都根据它们的进程号被添加到就绪队列中，不一定按顺序。一旦 ith 进程离开临界区，它就不会将 lock 设置为 false，这样任何进程现在都可以使用临界区，这是以前算法的问题。相反，它检查队列中是否有任何进程在等待。该队列被认为是循环队列。j 被认为是该行中的下一个进程，while 循环检查从 jth 进程到最后一个进程，以及从 0 到第(i-1)个进程是否有任何进程等待访问临界区。如果没有进程在等待，那么锁定值将变为假，接下来的任何进程都可以进入临界区。如果有，则该进程的等待值变为假，这样第一个 while 循环变为假，它可以进入临界区。这确保了有限的等待。因此，通过该算法可以解决进程同步问题。

**解锁和锁定伪代码–**

```
// Shared variable lock initialized to false 
// and individual key initialized to false

boolean lock;
Individual key;
Individual waiting[i];

while(1){
    waiting[i] = true;
    key = true;
    while(waiting[i] && key)
        key = TestAndSet(lock);
    critical section
    j = (i+1) % n;
    while(j != i && !waiting[j])
         j = (j+1) % n;
    if(j == i)
         lock = false;
    else
         waiting[j] = false;
    remainder section
} 
```