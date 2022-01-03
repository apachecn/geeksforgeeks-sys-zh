# 最后一分钟笔记–操作系统

> 原文:[https://www . geesforgeks . org/最后一分钟-笔记-操作系统/](https://www.geeksforgeeks.org/last-minute-notes-operating-systems/)

参见所有科目的最后一分钟笔记[所有科目在此](https://www.geeksforgeeks.org/lmns-gq/)。

**操作系统:**是用户和计算机硬件之间的接口。

[**操作系统类型:**](https://www.geeksforgeeks.org/operating-system-types-operating-systems-awaiting-author/)

1.  **批处理操作系统–**一组类似的作业存储在主内存中执行。只有当前一个作业的执行完成时，作业才会被分配给中央处理器。
2.  **多道程序操作系统–**主存由等待 CPU 时间的作业组成。操作系统选择其中一个进程，并将其分配给中央处理器。每当正在执行的进程需要等待任何其他操作(如输入/输出)时，操作系统都会从作业队列中选择另一个进程，并将其分配给中央处理器。这样，中央处理器就永远不会闲置，用户也可以同时完成多个任务。
3.  **多任务操作系统–**多任务操作系统结合了多道程序操作系统和中央处理器调度的优势，可以在作业之间快速切换。切换非常快，用户可以在每个程序运行时与其交互
4.  **分时操作系统–**分时系统需要与用户进行交互，以指示操作系统执行各种任务。操作系统以输出作为响应。指令通常是通过键盘这样的输入设备给出的。
5.  **实时操作系统–**实时操作系统通常是为专用系统构建的，用于在截止日期内完成一组特定的任务。

[**线程:**](https://www.geeksforgeeks.org/operating-system-threads-types/)
线程是一个轻量级进程，构成了 CPU 利用率的基本单位。通过包含多个线程，一个进程可以同时执行多个任务。

*   线程有自己的程序计数器、寄存器组和堆栈
*   一个线程与同一进程的其他线程共享资源代码段、数据段、文件和信号。

通过使用 fork()系统调用，可以引入一个新线程或给定进程的子进程。具有 n 个 fork()系统调用的进程会生成 2 个 <sup>n 个</sup>–1 个子进程。
螺纹有两种类型:

*   用户线程
*   内核线程

*示例:* Java 线程，POSIX 线程。例如:视窗 Solaris。

| **用户级线程** | **内核级线程** |
| 用户线程由用户实现。 | 内核线程由操作系统实现。 |
| 操作系统无法识别用户级线程。 | 内核线程被操作系统识别。 |
| 用户线程的实现很容易。 | 内核线程的实现是复杂的。 |
| 上下文切换时间更少。 | 上下文切换时间比较多。 |
| 上下文切换不需要硬件支持。 | 需要硬件支持。 |
| 如果一个用户级线程执行阻塞操作，那么整个进程将被阻塞。 | 如果一个内核线程执行阻塞操作，那么另一个线程可以继续执行。 |

[**流程:**](https://www.geeksforgeeks.org/gate-notes-operating-system-process-management-introduction/)
流程是正在执行的程序。程序计数器(PC)的值表示正在执行的进程的下一条指令的地址。每个过程由一个过程控制块表示。

[**进程调度:**](https://www.geeksforgeeks.org/gate-notes-operating-system-process-scheduling/) 下面是一个进程的不同时间。

1.  **到达时间–**流程到达就绪队列的时间。
2.  **完成时间–**流程完成执行的时间。
3.  **突发时间–**进程执行 CPU 所需的时间。
4.  **周转时间–**完工时间和到达时间之间的时间差。

    ```
    Turn Around Time = Completion Time - Arrival Time 
    ```

5.  **等待时间–**周转时间和突发时间之间的时间差。

    ```
    Waiting Time = Turn Around Time - Burst Time 
    ```

**我们为什么需要排班？**
一个典型的过程涉及到 I/O 时间和 CPU 时间。在像微软操作系统这样的单一编程系统中，等待输入输出的时间被浪费了，在此期间中央处理器是空闲的。在多道程序设计系统中，一个进程可以使用中央处理器，而另一个进程正在等待输入输出。这只有通过进程调度才能实现。

**流程调度算法的目标:**

*   最大 CPU 利用率(尽可能保持 CPU 繁忙)
*   CPU 的公平分配。
*   最大吞吐量(单位时间内完成执行的进程数)
*   最短周转时间(流程完成执行所需的时间)
*   最小等待时间(进程在就绪队列中等待的时间)
*   最小响应时间(流程产生第一个响应的时间)

**不同的调度算法:**

1.  [**【先到先得(FCFS)**](https://www.geeksforgeeks.org/program-fcfs-scheduling-set-1/) :最简单的调度算法，根据流程到达时间进行调度。
2.  [**【最短作业优先(SJF)**](https://www.geeksforgeeks.org/program-shortest-job-first-sjf-scheduling-set-1-non-preemptive/) :突发时间最短的进程先调度。
3.  [**【最短剩余时间优先(SRTF)**](https://www.geeksforgeeks.org/program-shortest-job-first-scheduling-set-2srtf-make-changesdoneplease-review/) :是 SJF 算法的抢占模式，按照最短剩余时间调度作业。
4.  [**循环调度**](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) :每个进程都被分配一个固定的时间，以循环的方式。
5.  [**【基于优先级的调度(非抢占式)**](https://www.geeksforgeeks.org/program-priority-scheduling-set-1/) :在这种调度中，进程按照优先级进行调度，即优先级最高的进程优先调度。如果两个进程的优先级匹配，那么调度就是根据到达时间。
6.  [**最高响应率下一个(HRRN)**](https://www.geeksforgeeks.org/operating-system-highest-response-ratio-next-hrrn-scheduling/) :在这个调度中，调度响应率最高的进程。这种算法避免了饥饿。

    ```
    Response Ratio = (Waiting Time + Burst time) / Burst time
    ```

7.  [**【多级队列调度(MLQ)**](https://www.geeksforgeeks.org/operating-system-multilevel-queue-scheduling/) :根据流程的优先级，流程被放置在不同的队列中。通常，高优先级进程被放在顶层队列中。只有在顶级队列中的进程完成后，才会调度较低级别的排队进程。
8.  [**多级反馈队列(MLFQ)调度**](https://www.geeksforgeeks.org/multilevel-feedback-queue-scheduling/) :允许流程在队列之间移动。这个想法是根据进程的中央处理器突发的特征来分离进程。如果一个进程使用了太多的 CPU 时间，它就会被移到一个低优先级的队列中。

**一些关于调度算法的有用事实:**

1.  FCFS 会导致长时间等待，尤其是当第一个作业占用太多 CPU 时间时。
2.  SJF 算法和最短剩余时间优先算法都可能导致饥饿。考虑这样一种情况:就绪队列中有一个较长的进程，而较短的进程不断到来。
3.  如果循环调度的时间量非常大，那么它的行为与 FCFS 调度相同。
4.  就一组给定进程的平均等待时间而言，SJF 是最优的。SJF 给出了最短的平均等待时间，但 SJF 的问题是如何知道/预测下一份工作的时间。

**临界区问题:**

1.  **临界区–**程序中共享变量被访问和/或更新的代码部分。
2.  **剩余部分–**程序的剩余部分，不包括关键部分。
3.  **在条件下竞争–**代码的最终输出取决于变量的访问顺序。这被称为绕场赛跑。

临界截面问题的解决方案必须满足以下三个条件:

1.  **互斥–**如果进程 Pi 在其临界区执行，则不允许其他进程进入临界区。
2.  **进度–**如果在关键部分没有进程正在执行，那么一个进程进入关键部分的决定不能由正在其剩余部分执行的任何其他进程做出。该进程的选择不能无限期推迟。
3.  **有界等待–**在一个进程请求访问临界区之后，在请求被批准之前，其他进程可以进入临界区的次数是有界限的。

**同步工具:**
A **信号量**是一个整型变量，只能通过两个原子操作来访问，等待()和信号()。原子操作在单个 CPU 时间片中执行，没有任何优先权。信号量有两种类型:

1.  **计数信号量–**计数信号量是一个整数值变量，其值可以在不受限制的域内变化。
2.  **Mutex –** A mutex provides mutual exclusion, either producer or consumer can have the key (mutex) and proceed with their work. As long as the buffer is filled by producer, the consumer needs to wait, and vice versa.

    在任何时候，只有一个线程可以使用整个缓冲区。这个概念可以用信号量来概括。

    **误解:**
    二进制信号量和互斥量之间存在歧义。我们可能会发现互斥体是二进制信号量。*但他们不是！*互斥和信号量的目的不同。由于它们实现的相似性，互斥可能被称为二进制信号量。

[**死锁**](https://www.geeksforgeeks.org/operating-system-process-management-deadlock-introduction/) :
一组进程被阻塞的情况，因为每个进程都持有一个资源，并等待其他进程获取另一个资源。如果以下四个条件同时成立，可能会出现死锁(必要条件):

1.  **互斥–**一个或多个资源不可共享(一次只能使用一个进程)。
2.  **保持并等待–**一个进程至少保持一个资源并等待资源。
3.  **无抢占–**除非进程释放资源，否则不能从进程中获取资源。
4.  **循环等待–**一组进程以循环形式相互等待。

**处理死锁的方法:**处理死锁有三种方法

1.  [**死锁预防或避免**](https://www.geeksforgeeks.org/deadlock-prevention/) :想法是不让系统进入死锁状态。
2.  [**死锁检测与恢复**](https://www.geeksforgeeks.org/deadlock-detection-recovery/) :让死锁发生，一旦发生就做抢占处理。
3.  **一起忽略问题–**:如果死锁很少见，那就让它发生，重启系统。这是 Windows 和 UNIX 都采用的方法。

[**庄家算法:**](https://www.geeksforgeeks.org/operating-system-bankers-algorithm/)
该算法处理同一资源的多个实例。

**内存管理:**
这些技术允许多个进程共享内存。

*   **覆盖–**内存应该只包含给定时间所需的指令和数据。
*   **交换–**在多道程序设计中，使用时间片的指令从内存中交换出去。

[**内存管理技术:**](https://www.geeksforgeeks.org/operating-system-memory-management-partition-allocation-method/)

**(a)单分区分配方案–**
内存分为两部分。一部分保留给操作系统使用，另一部分保留给用户使用。

**(b)多分区方案–**

1.  **固定分区–**内存被划分为固定大小的分区。
2.  **可变分区–**内存被划分为大小可变的分区。

可变分区分配方案:

1.  **第一次拟合–**到达的进程被分配了第一个内存洞，在这个内存洞中它完全适合。
2.  **最佳匹配–**到达的进程被分配了最适合的内存空洞，将最小内存留空。
3.  **最差匹配–**到达进程被分配了内存空洞，在这个空洞中它留下了最大的间隙。

**注:**

*   最佳匹配不一定能为内存分配带来最佳结果。
*   外部碎片的原因是固定分区和可变分区中的条件，即整个进程应该分配在一个连续的内存位置。因此使用**分页**。

1.  **分页–**
    物理内存被分成大小相等的帧。主存分为固定大小的页面。物理内存帧的大小等于虚拟内存帧的大小。
2.  **分段–**
    分段的实现是为了给用户提供内存的视图。逻辑地址空间是段的集合。分段可以在使用或不使用分页的情况下实现。

[**页面故障:**](https://www.geeksforgeeks.org/operating-system-page-fault-handling/) 
页面故障是一种中断类型，当正在运行的程序访问映射到虚拟地址空间但未加载到物理内存中的内存页面时，由硬件引发。

[**页面替换算法:**](https://www.geeksforgeeks.org/page-replacement-algorithms-in-operating-systems/)

1.  **First In First Out (FIFO) –**
    This is the simplest page replacement algorithm. In this algorithm, operating system keeps track of all pages in the memory in a queue, oldest page is in the front of the queue. When a page needs to be replaced page in the front of the queue is selected for removal.

    例如，考虑页面引用字符串 1、3、0、3、5、6 和 3 个页面槽。最初，所有插槽都是空的，因此当 1、3、0 出现时，它们被分配给空插槽—> 3 页故障。当 3 出现时，它已经在内存中，因此—> 0 页错误。然后是 5，它在内存中不可用，所以它会替换最旧的页槽，即 1。—> 1 页错误。最后，6 来了，它在内存中也不可用，所以它取代了最旧的页槽，即 3 —> 1 页故障。

    **Belady 的异常:**
    Belady 的异常证明了在使用先进先出(FIFO)页面替换算法的同时，增加页面帧数时，有可能出现更多的页面错误。例如，如果我们考虑引用字符串 3 2 1 0 3 2 4 3 2 1 0 4 和 3 个槽，我们总共得到 9 个页面错误，但是如果我们将槽增加到 4 个，我们得到 1 0 个页面错误。

2.  **Optimal Page replacement –**
    In this algorithm, pages are replaced which are not used for the longest duration of time in the future.

    让我们考虑页面引用字符串 7 0 1 2 0 3 0 4 2 3 0 3 2 和 4 个页面槽。最初，所有插槽都是空的，因此当 7 0 1 2 被分配给空插槽时—> 4 页故障。0 已经存在，因此—> 0 页面错误。当 3 到来时，它将取代 7，因为它不会在未来最长的时间内使用。—> 1 页错误。0 已经存在，因此—> 0 页面错误。4 将发生 1 —> 1 页错误。现在是进一步的页面引用字符串—> 0 页面错误，因为它们已经在内存中可用。

    最佳页面替换是完美的，但实际上是不可能的，因为操作系统无法知道未来的请求。最佳页面替换的用途是建立一个基准，以便可以根据它分析其他替换算法。

3.  **Least Recently Used (LRU) –**
    In this algorithm, the page will be replaced which is least recently used.

    假设页面引用字符串 7 0 1 2 0 3 0 4 2 3 0 3 2。最初，我们有 4 页的空位。最初，所有插槽都是空的，因此当 7 0 1 2 被分配给空插槽时—> 4 页故障。0 已经是他们的 so —> 0 页面错误。当 3 出现时，它将取代 7，因为它是最近最少使用的—> 1 页故障。0 已在内存中，因此—> 0 页错误。4 将发生 1 —> 1 页错误。现在是进一步的页面引用字符串—> **0 页面错误**，因为它们已经在内存中可用。

    [**文件系统**](https://www.geeksforgeeks.org/file-system-operating-systems/) :文件是记录在二级存储器上的相关信息的集合。Or 文件是逻辑相关实体的集合。

    [**文件目录**](https://www.geeksforgeeks.org/file-system-operating-systems/) :文件的集合就是一个文件目录。该目录包含有关文件的信息，包括属性、位置和所有权。这些信息中的大部分，尤其是与存储相关的信息，都是由操作系统管理的。

    1.  **单级目录**:在这种情况下，为所有用户维护一个目录
    2.  **两级目录**:由于两级，每个文件都有一个路径名来定位该文件。
    3.  **TREE-STRUCTURED DIRECTORY** :目录以树的形式维护。搜索是有效的，也有分组能力。

    [**文件分配方式**](https://www.geeksforgeeks.org/file-system-operating-systems/) :

    1.  **连续分配**:在文件创建时，将一组连续的块分配给一个文件。
    2.  **链接分配(非连续分配)**:分配基于单个块。每个块包含一个指向链中下一个块的指针。
    3.  **索引分配**:它解决了连续和链式分配的许多问题。在这种情况下，文件分配表为每个文件包含一个单独的一级索引

    [**磁盘调度**](https://www.geeksforgeeks.org/disk-scheduling-algorithms/) :
    磁盘调度是由操作系统来调度到达磁盘的 I/O 请求。磁盘调度也称为输入/输出调度。

    1.  **寻道时间:**寻道时间是将磁盘臂定位到要读取或写入数据的指定磁道所需的时间。
    2.  **旋转延迟时间:**旋转延迟时间是指磁盘的所需扇区旋转到可以访问读/写磁头的位置所需的时间。
    3.  **传输时间:**传输时间是传输数据的时间。这取决于磁盘的转速和要传输的字节数。
    4.  **磁盘访问时间:**寻道时间+旋转延迟+传输时间
    5.  **磁盘响应时间:**响应时间是请求等待执行其 I/O 操作所花费的平均时间。平均响应时间是所有请求的响应时间。

    [**磁盘调度算法**](https://www.geeksforgeeks.org/disk-scheduling-algorithms/) :

    1.  **FCFS:** FCFS 是所有磁盘调度算法中最简单的。在 FCFS 中，请求按照到达磁盘队列的顺序进行处理。
    2.  **SSTF:** 在 SSTF(最短寻道时间优先)，寻道时间最短的请求首先执行。因此，每个请求的寻道时间都是在队列中预先计算的，然后根据计算出的寻道时间进行调度。因此，磁盘臂附近的请求将首先被执行。
    3.  **SCAN:** 在 SCAN 算法中，磁盘臂移动到一个特定的方向，并为其路径中的请求提供服务，到达磁盘末端后，它反转方向，再次为其路径中的请求提供服务。因此，这种算法的工作原理类似于电梯，因此也被称为电梯算法。
    4.  **CSCAN:** 在 SCAN 算法中，磁盘臂在反转方向后，再次扫描已扫描的路径。因此，可能有太多的请求在另一端等待，或者可能有零个或很少的请求在扫描区域等待。
    5.  **LOOK:** 与 SCAN 磁盘调度算法类似，只是不同的是，磁盘臂尽管到达磁盘的末端，但只到达磁头前面要服务的最后一个请求，然后只从那里反向。因此，它防止了由于不必要的盘尾遍历而产生的额外延迟。
    6.  **CLOOK:** 由于 LOOK 类似于 SCAN 算法，以类似的方式，CLOOK 类似于 CSCAN 磁盘调度算法。在 CLOOK 中，磁盘臂尽管走到最后，但只到达磁头前面要服务的最后一个请求，然后从那里到达另一端的最后一个请求。因此，它还防止了由于不必要的到磁盘末端的遍历而产生的额外延迟。