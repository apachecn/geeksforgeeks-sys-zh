# 操作系统多线程架构的阶段

> 原文:[https://www . geeksforgeeks . org/stages-of-多线程架构 in-os/](https://www.geeksforgeeks.org/stages-of-multi-threaded-architecture-in-os/)

先决条件–[多线程架构](https://www.geeksforgeeks.org/introduction-to-multi-threaded-architectures-and-systems-in-os/)

多线程模型中线程的实现分为不同的阶段，每个阶段都执行一个独特的功能。

每个线程的各个执行阶段以及每个线程之间的关系如下所示:

**1。延续阶段:**

*   **(i)** Once a thread is initiated by its predecessor (or previous) thread, it starts executing its continuation stage. The important function of this stage is to calculate variables that are recurrence in nature.

    例如–移动下一个线程所需的循环索引变量。就在下一个线程被激活之前，这些变量的值将前进到下一个线程处理元素。

*   **(ii)** In the case of DO loop, the index variable, such as x=x+1 or y = y->, will be calculated next, and then forwarded to the next thread element (processing element). The continuation stage of a thread ends with a fork (divide) instruction, which is the real reason for the next thread to start.

**2。目标-存储-地址-生成阶段:**

*   **(i)** These threads can perform storage operations to be performed on concurrent threads later, and they can depend on data. This stage will store the operation and is called target storage (TS).
*   **(ii)** 这个阶段第二重要的工作是降低硬件复杂度，多线程模型的大多数实现都不允许假设数据依赖。为了使运行时数据相关性检查更容易，需要尽快计算这些目标存储的地址。

    TSAG(目标存储地址生成)阶段为这些目标存储执行地址计算。此外，这些地址将被存储在每个线程处理元件的存储缓冲器中，然后被转发到所有后续并发线程的存储缓冲器。

*   **(iii)** 一旦一个线程完成了 TSAG 阶段，那么所有的目标存储地址都已被转发，然后它将 tsag-done 标志发送给后续线程。那么这个标志将通知下一个线程，该线程可以开始依赖于前一个线程的计算。但是在收到 tsag_done 标志之前，线程只能执行不依赖于其活动的前置线程的任何目标存储的计算。但是为了增加线程之间的重叠，目标存储地址生成阶段可以进一步分为两部分。

    第一部分是让目标存储寻址对早期线程没有任何数据依赖的代，这些代被快速计算，然后转发给下一个线程。第二部分计算不安全的目标存储地址，这些地址可能依赖于早期线程的数据。在开始之前，这些计算必须等待来自前置线程的 tsag_done 标志。

**3。计算阶段:**

*   **(i)** 该阶段执行线程的主要计算，称为计算阶段。如果加载操作的地址与其内存缓冲区中的目标存储条目的地址相匹配，则线程可以从条目中读取数据(如果可用的话)，或者等待，直到数据从较早的并发线程转发。

    而另一方面，如果目标存储的值是在该阶段的实现期间计算的，则线程需要将地址和数据转发到其所有并发后续线程的内存缓冲区。

*   **(ii)** The calculation stage of the thread ends with a stop instruction.

**4。回写阶段:**

*   **(I)** If after the thread finishes (or finishes) the calculation stage it executes, completely clear the control dependency by writing all the data of the operation stored in its memory buffer into memory (actually including the data from the target and conventional storage).
*   **(ii)** When the data from the storage operation needs to be kept in the memory buffer until the write-back stage to protect the memory state from being changed by the hypothetical thread, the hypothetical thread is subsequently terminated by the earlier simultaneous thread due to the wrong control assumption.
*   **(iii)** In order to maintain the correct memory state, concurrent threads must execute the write-back phase in their inherent order. This means that a thread must wait for the wb_done flag of the previous thread before it can execute the writeback phase. It also needs to forward the wb_done flag to the next thread after completing its write-back phase. Because all stored data is submitted thread by thread, there is no threat of read-write-after-write and write-after-write at runtime.