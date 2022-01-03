# N 进程彼得森算法

> 原文:[https://www.geeksforgeeks.org/n-process-peterson-algorithm/](https://www.geeksforgeeks.org/n-process-peterson-algorithm/)

**本主题的先决条件**包括关于进程间[同步](https://www.geeksforgeeks.org/introduction-of-process-synchronization/)以及如何获得它的想法。此外，一些关于[生产商-消费者](https://www.geeksforgeeks.org/producer-consumer-problem-using-semaphores-set-1/)问题的知识以及[彼得森算法](https://www.geeksforgeeks.org/petersons-algorithm-in-process-synchronization/)的想法也是至关重要的。

**概述:**
任何操作系统中各种进程的执行之间的同步是至关重要的。哪个过程将被允许执行它们的关键部分，在那里它们可能会改变一些重要的变量，在其他过程中，知道这一点是非常重要的，因为忽略它会导致不希望的结果或结果。因此，为了获得进程间的同步，人们讨论和发展了许多技术，其中彼得森算法就是其中之一。生产者-消费者问题是最著名的临界区问题之一。在这种情况下，如果同步没有正确实现，那么缓冲区中存在的项目数将会不断受到阻碍，并将导致不必要的结果。

**描述:**
皮特森的解决方案是一种基于软件的解决比赛条件或关键路段问题的方案。它通常不会在现代计算机中实现，但这种解决方案提供了一种基本的算法方法来解决临界区问题。在本文中，我们将主要考虑生产者-消费者问题。最初，该算法很容易提出，目标是仅在两个进程之间建立同步。因此，通过对它进行一个小的更改，它可以进一步扩展到考虑 N 个进程之间的同步。

**Peterson 对 2 个进程的解决方案:**
让我们考虑在一个操作系统中并行工作的 2 个进程。这些过程修改了相同的变量，因此它们都有进入竞争状态的风险。我们认为，每个进程都有一个剩余部分，在这个剩余部分中，它们不修改可能导致竞争条件的变量，还有一个称为临界部分的部分，在这个临界部分中，进程可能有机会进入竞争条件。下面给出了这种情况下的基本彼得森算法。

**步骤-1 :**
我们来考虑一下被命名为 P <sub>0</sub> 和 P <sub>1</sub> 的两个进程。因此，我们可以使用一个简单的公式在这两个过程之间切换，即 1- <过程的基础>。要将指针从 P <sub>1</sub> 更改为 P <sub>0</sub> ，应通过公式更改为 idx = 1-1(P<sub>1</sub>的基数)= 0。因此，在任何时候 idx 都将指向 P <sub>1</sub> 或 P <sub>0</sub> 。

**步骤-2 :**
该算法需要两个数据项在进程间共享。

```
int turn;
```

该变量指示轮到谁执行其程序的关键部分。如果 turn == 1，那么轮到 P <sub>1</sub> 进入临界截面区域。

```
boolean flag[2];
```

这个数组表示一个进程是否准备好进入它的临界区。flag[0]==true 表示 P <sub>0</sub> 准备执行其程序的关键部分。

**步骤-3 :**
下面给出这个算法的主要部分。这个过程如果想进入程序的关键部分，那么他们必须执行以下两件事。

1.  设置标志[idx] = true。如果 P <sub>1</sub> 想进入比它应该设置标志[1]=真。
2.  设置转弯= 1-idx，即如果 P <sub>1</sub> 想要进入，那么它应该根据另一个过程来设置转弯，因为这意味着如果另一个过程想要进入临界区部分，可以在 P <sub>1</sub> 已经执行了它的部分之后这样做。

**第 4 步:**
算法介绍如下。任何进程都被禁止进入程序的关键部分，直到发生以下两种情况。

```
1) if flag[1-idx]==true
2) if turn == 1-idx.
```

现在，直到上述两个条件都为真，进程在 while 循环中等待，不做任何事情，如果任何条件变为非真，进程进入临界区，如果需要，下一个进程(即 1-idx)在循环中等待执行临界区部分。这也保证了没有两个进程同时执行关键部分。

**伪码–**
因此，算法的伪码可以给出如下。

```
idx=0;

do{    

// preparing to enter the critical section part
flag[idx] = TRUE;
turn = 1-idx;

while(flag[1-idx]==TRUE and turn == 1-idx)        
// checking the two variables continuously. This is a waste of time.
;   
// continues in the loop till chance cames

/*
Critical section part
*/

flag[idx] = FALSE;

/*
Remainder section part
*/
}
```

因此，通过这种方式，两个进程之间存在同步。上述算法保证了两个进程之间始终存在互斥和同步。

**Peterson 的 N-Process 算法:**
该算法采用与上面讨论的相同的数据结构。它唯一的修改是它使用了一个 N 大小的数组，变量 turn 可以有从 0 到 N-1 的值。在这个算法中也有一个非常大的变化，因为在上面的算法中，在 while 条件下，我们连续地引用转弯变量来包含互补过程的数。但是在这个算法中，情况并非如此，因为有 2 个以上的进程。

**实现–**
实现上述算法的思路如下。

**步骤-1 :**
让我们考虑一个大小为 N 的队列，用于放置 N 个进程。现在假设我们编写了一个算法，每个进程在某个时间将自己推入队列，来到队列的末尾，然后它们将被允许执行它们的关键部分并离开队列。通过这种方式，我们可以保证每个进程一旦进入队列并到达它的末端(前端)，就被允许执行它们的关键部分。直到过程到达前线，它应该等待，因为可能有两种情况发生在那一刻。

*   有些进程可能在队列的下一个索引处，正在等待其他进程。
*   或者如果任何后台进程(它很晚才进入队列)没有移动到当前进程的位置。(这意味着后面的进程会检查前面是否已清空，并希望将队列向前推。)

第一种情况很清楚，但第二种情况中有一个技巧(或者我们可以说一个想法)。读完第二点你就会明白了。

**步骤-2 :**
算法的数据结构与 2 个进程 1 的数据结构相同，但是现在 Turn 变成了 N 大小的数组，Flag 也是 N 大小的数组

```
Flag[PID] 
// has size N  and PID always ranges from 0---N-1 since there are N processes.
```

指示 PID<sup>进程在队列中的位置。</sup>

```
Turn[i] = PID // has size N
```

*   为了标记这一点，到目前为止，没有进程说它在位置 I(因为如果任何进程这样说，那么它意味着有来自后面进程的反推，因此当前进程应该改变它的位置)。
*   回推之所以发生，是因为队列中较晚进入的一些进程应该被给予进入的位置，因此存在一个推到队列前面的等待进程。由于系统工作在多处理器环境中，同时执行多个进程，因此产生了后推。
*   此外，队列的大小可能会慢慢减小，因为某些进程在执行其关键部分后可能会被终止，或者离开队列，或者进入另一个关键部分的另一个队列。

因此，下面解释 N 进程彼得森算法的伪代码。

*   我们将创建两个名为 lock()和 unlock()的函数。在 lock()函数中，进程等待直到到达队列的末尾，在 unlock()函数中，它标记退出队列。
*   关键部分的执行发生在进程处于队列末尾时，即在锁定和解锁方法之间。
*   这两种方法描述如下。

```
LOCK( Process PID){
    for( int i = 0;i<N;++i){        
        //Looping through position from 0 to end (N) of queue.

        Turn[i]=PID;            
        // Tells that PID process is at ith position.

        Flag[PID]=i;            
        // Tells that till now there is no back push

        while((for all k != PID, Flag[k]<i) or (Turn[i] != PID))
        ;            
        //Wait till either there is no process 
        //at the top of queue or there is a back push.
    }
}

UNLOCK(Process PID){
    Flag[PID]=-1  
    //process exists or terminates or goes to another queue 

    else
    Flag[PID]=0   
    // If process enter the first position at the queue.    
} 
```

因此，下面给出了上述算法的伪码。

```
LOCK( Process PID){
    for( int i = 0;i<N;++i){        
        Turn[i]=PID;            
        Flag[PID]=i;            
        while((for all k != PID, Flag[k]<i) or (Turn[i] != PID))
        ;            
    }
}
/* Critical Section */ 
UNLOCK(Process PID){
    Flag[PID]=-1  
    else
    Flag[PID]=0 
}
```

**结论:**
可以清楚地看到，上述算法遵守任何多处理器环境中同步和并发进程需要满足的所有规则。因此，我们能够获得关于彼得森算法如何对 N 进程工作的知识。