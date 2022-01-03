# 信号量及其类型

> 原文:[https://www.geeksforgeeks.org/semaphores-and-its-types/](https://www.geeksforgeeks.org/semaphores-and-its-types/)

**概述:**
[信号量](https://www.geeksforgeeks.org/semaphores-in-process-synchronization/)是有两个字段的复合数据类型一个是非负整数 S.V，第二个是队列 S.L 中的一组进程，用来解决关键段问题，通过两个原子操作来解决。在这种情况下，等待并发出用于进程同步的信号。

**流程的状态:**
让我们来看看流程在其生命周期中的各个阶段。这将有助于理解信号量。

1.  **运行–**
    它表示正在执行的流程。
2.  **就绪–**
    表示进程想要运行。
3.  **空闲–**
    进程在没有进程运行时运行
4.  **阻塞–**
    未准备好的进程不是正在运行的进程的候选。它可以被一些外部动作唤醒。
5.  **非活动–**
    流程的初始状态。该过程在某个时刻被激活并准备就绪。
6.  **完成–**
    当一个进程执行它的最终语句时。

**信号量的初始化:**
信号量 S 必须用 S.V. > 0 的值和空的 S.L 初始化

```
Semaphore S <- (k,φ)
```

**信号量中的原子操作:**
这里我们将讨论如下两个原子操作等待和信号。

**Operation-1:**
**Wait(S):**
根据 S.V .的值，如果是非 0，递减其值，进程 p 可以继续执行，如果是 0，进程 p 被添加到 set 组件，进程 p 的状态变为阻塞，在这种情况下，进程 p 在信号量上被称为阻塞。

**算法–**

```
if(S.V > 0)
{
  S.V. = S.V -1
}
else{
       S.L. = S.L. U p
       p.state = blocked
     }
```

**操作-2 :**
**信号(S) :**
根据 S.L .的值，如果为空，则递增整数的值，如果为非空，则解除阻塞 q .一组进程中任意一个进程阻塞 o . S . l .并将 p .的状态更改为就绪。

**算法–**

```
   if(S.L. ==  φ){

                 S.V. = S.V.+1
                }
   else{
          Let q be some process in S.L. S
          S.L. = S.L. - {q}
          q.state = ready
      }
```

**信号量的类型:**
这里我们将讨论信号量的类型如下。

**Type-1 :**
**通用信号量:**
一种信号量，其整数部分可以取任意非负值，这些被称为通用信号量。它们有点弱信号。

**Type-2 :**
**二进制信号量:**
其整数部分只取值 0 和 1 的信号量称为二进制信号量。这也被称为“互斥体”，代表互斥。

**初始化–**

```
S <- (0, φ) or S <- (1, φ)
```

**等待操作–**
保持如上不变。

**信号操作–**
略有变化如下

**算法:**

```
Signal(S)
   :

   if (S.V.== 1)
{

   // Undefined

   // Return
}

else if (S.L == empty) { S.V.= 1 }

else
{

   Let q be some process in
       S.L.

       S.L.
       = S.L.
         - { q }

           q.state
       = ready
}
```

**Type-3 :**
**强信号量:**
在强信号量中，S.L .和弱信号量一样保持不变，而 S.V .被队列代替。因为在弱信号量中移除任意进程可能导致饥饿，而在这种情况下，它仍然没有饥饿。

**初始化–**

```
 S <- (0,empty)
```

**等待操作–**
**算法:**

```
Wait(S) :   
if (S.V > 0)
{

   S.V.= S.V - 1
}

else
{

   S.L.= S.L.U p

             p.state
       = blocked
}
```

**信号操作–**
**算法:**

```
Signal(S)
   :

   if (S.L.== empty)
{

   S.V.= S.V.+ 1
}

else
{

   q = head(S.L.)

           S.L.
       = S.L.
         - { q }

           q.state
       = ready
}
```

**Type-4:**
**Busy- Wait Semaphore:**
它没有组件 S.L .而 Semaphore S 仅由 S.V .标识。Busy-Wait Semaphore 适用于多处理器系统，在该系统中，等待进程有自己的处理器，不会浪费可用于计算的 CPU 时间。

**等待操作–**
**算法:**

```
Wait(S):
await S>0
S = S - 1
```

**信号操作–**
**算法:**

```
Signal(S):
S = S + 1
```

**结论:**
在这一节中，我们讨论了信号量及其类型，也讨论了它的原子操作。这些是信号量的基础，用于解决关键部分的问题。