# 操作系统|第 17 集

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-17/](https://www.geeksforgeeks.org/operating-systems-set-17/)

GATE 2012 CS 考试问了以下问题。

**Fetch_And_Add(X，I)是一个原子的读-修改-写指令，它读取内存位置 X 的值，将其递增值 I，并返回 X 的旧值。它在下面显示的伪代码中用于实现忙等待锁。l 是初始化为 0 的无符号整数共享变量。值 0 对应锁可用，而任何非零值对应锁不可用。** 

```
  AcquireLock(L){
         while (Fetch_And_Add(L,1))
               L = 1;
   }
  ReleaseLock(L){
         L = 0;
   } 
```

**这个实现**
(A)失败是因为 L 可以溢出
(B)失败是因为当锁实际可用时 L 可以取非零值
(C)工作正常但是可能会饿死一些进程
(D)工作正常没有饿死

回答(B)
边循环边仔细看下面。

```
     while (Fetch_And_Add(L,1))
               L = 1;  // A waiting process can be here just after 
                       // the lock is released, and can make L = 1.

```

考虑这样一种情况，一个进程刚刚释放了锁，并使 L = 0。让多一个进程等待锁，意味着执行 AcquireLock()函数。就在 L 被设为 0 之后，让等待进程执行 L = 1 的行。现在，锁是可用的，L = 1。因为 L 是 1，所以等待过程(以及任何其他未来到来的过程)不能从 while 循环中出来。

上述问题可以通过将 AcuireLock()更改为以下内容来解决。

```
  AcquireLock(L){
         while (Fetch_And_Add(L,1))
         { // Do Nothing }
   }

```

所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见 [GATE Corner](http://geeksquiz.com/gate-corner-2/) 。

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。