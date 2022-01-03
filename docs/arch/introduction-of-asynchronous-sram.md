# 异步 SRAM 介绍

> 原文:[https://www . geesforgeks . org/异步 sram 介绍/](https://www.geeksforgeeks.org/introduction-of-asynchronous-sram/)

随机存取存储器，即[随机存取存储器](https://www.geeksforgeeks.org/random-access-memory-ram/)是计算机存储存储设备的主要数据来源。该内存有两种形式，命名为–

*   [[static random access memory]](https://www.geeksforgeeks.org/different-types-ram-random-access-memory/)
*   [[dynamic random access memory]](https://www.geeksforgeeks.org/difference-between-sram-and-dram/)

而静态随机存取存储器也大致分为两种形式，分别是–

*   Synchronous Static Random Access Memory
*   Asynchronous random access memory

在本文中，我们将研究什么是异步静态随机存取存储器。这里需要注意的一点是，同步动态随机存取存储器不同于异步静态随机存取存储器。

**异步 SRAM :**

*   首先，让我们看看异步在这里是什么意思。不依赖外部时钟脉冲工作的器件称为异步器件，不依赖外部时钟工作的静态随机存取存储器称为异步静态随机存取存储器。
*   它使用锁存电路，尤其是触发器。由于该静态随机存取存储器不依赖于任何外部时钟脉冲，因此一旦接收到指令，它就可以根据指令要求进行读取、写入。
*   通常优选用作小型高速缓存嵌入式处理器。它位于易失性存储器之下，因为只要持续向系统供电，它就可以存储该值。所以异步静态随机存取存储器中的数据本质上是非常不稳定的。动态随机存取存储器将数据作为电荷存储在电容器上。
*   用于构建异步静态随机存取存储器的电路架构本质上是复杂的，因此用于构建其拓扑的组件数量会更多，这一因素使得静态随机存取存储器比动态随机存取存储器更昂贵。在许多家用电脑中，都使用 DRAMS，如 DDR3、DDR5 等。
*   现在，由于数据被静态存储在这个静态随机存取存储器中，所以静态随机存取存储器所需的功率比动态随机存取存储器少。静态随机存取存储器是静态存储数据的，因此与动态随机存取存储器相比，它存储数据的速度更快。

**异步静态随机存取存储器的状态:**

它可以处于 3 种状态，即–

*   **–** Standby is a state in SRAM, in which the SRAM circuit is idle and the specific SRAM is not working. It may not fully utilize the capacity of available resources.
*   **Read-** This is a situation in which data is requested in SRAM. It makes the circuit of SRAM in working state.
*   **Write-** When the data stored in the asynchronous SRAM must be updated or overwritten, this is a C state in the SRAM. This state will also make the circuit of SRAM in working state.

**异步 SRAM 的应用:**

*   Widely used in making CPU cache, hard disk buffer, etc., which is more common in small memory applications.
*   For the manufacture of network equipment, asynchronous static random access memory is frequently used in the hardware implementation of network equipment. Such as switches, routers, etc.
*   The design of programmable logic controller adopts asynchronous static random access memory.
*   Used for printers with multiple functions.

**异步静态随机存取存储器的优势:**

*   Because asynchronous static random access memory has three operating states, the communication of asynchronous static random access memory becomes very effective in essence.
*   The fast execution function of asynchronous random access memory makes it the first choice in network architecture.

虽然异步静态随机存取存储器似乎是最好的选择，但它也有一些缺点。其中一些如下。

**异步 SRAM 的缺点:**

*   The cost of implementing asynchronous SRAM is higher, which makes the embedded cost in our system higher.
*   Asynchronous dual ports are generally slower than synchronous dual ports.
*   Asynchronous SRAM has less bandwidth than synchronous SRAM.