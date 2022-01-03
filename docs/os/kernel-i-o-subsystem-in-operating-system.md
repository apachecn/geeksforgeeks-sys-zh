# 操作系统中的内核输入输出子系统

> 原文:[https://www . geesforgeks . org/kernel-I-o-子系统-in-operating-system/](https://www.geeksforgeeks.org/kernel-i-o-subsystem-in-operating-system/)

先决条件–[微内核](https://www.geeksforgeeks.org/operating-system-microkernel/)
内核提供许多与输入/输出相关的服务。一些服务，如调度、缓存、假脱机、设备预留和错误处理，由内核提供，输入/输出子系统建立在硬件和设备驱动程序基础设施上。输入/输出子系统还负责保护自己免受错误进程和恶意用户的攻击。

1.  **I/O Scheduling –** 
    To schedule a set of I/O requests means to determine a good order in which to execute them. The order in which the application issues the system call is the best choice. Scheduling can improve the overall performance of the system, can share device access permission fairly to all the processes, reduce the average waiting time, response time, turnaround time for I/O to complete. 

    操作系统开发人员通过为每个设备维护一个请求等待队列来实现时间表。当应用程序发出阻塞输入/输出系统调用时，该请求将被放入该设备的队列中。输入输出调度器重新排列顺序，以提高系统的效率。

2.  **缓冲–**
    一个*缓冲区*是一个存储区域，用于存储在两个设备之间或设备与应用程序之间传输的数据。做缓冲有三个原因。
    1.  首先是处理数据流生产者和消费者之间的速度不匹配。

    2.  缓冲的第二个用途是为具有不同数据传输大小的数据提供适应性。

    3.  缓冲的第三个用途是支持应用程序 I/O 的复制语义，“复制语义”的意思是，假设一个应用程序想要在磁盘上写入存储在其缓冲区中的数据。它调用 **write()** 系统的调用，提供一个指向缓冲区的指针和指定要写入的字节数的整数。

3.  **Caching –** 
    A *cache* is a region of fast memory that holds a copy of data. Access to the cached copy is much easier than the original file. For instance, the instruction of the currently running process is stored on the disk, cached in physical memory, and copied again in the CPU’s secondary and primary cache. 

    缓冲区和高速缓存之间的主要区别在于，缓冲区可能只保存数据项的现有副本，而根据定义，高速缓存保存驻留在别处的项的更快存储上的副本。

4.  **Spooling and Device Reservation –** 
    A *spool* is a buffer that holds the output of a device, such as a printer that cannot accept interleaved data streams. Although a printer can serve only one job at a time, several applications may wish to print their output concurrently, without having their output mixes together. 

    操作系统通过阻止所有输出继续到打印机来解决这个问题。所有应用程序的输出都暂存在单独的磁盘文件中。当应用程序完成打印时，假脱机系统将相应的假脱机文件排队，以便输出到打印机。

5.  **Error Handling –** 
    An Os that uses protected memory can guard against many kinds of hardware and application errors so that a complete system failure is not the usual result of each minor mechanical glitch, Devices, and I/O transfers can fail in many ways, either for transient reasons, as when a network becomes overloaded or for permanent reasons, as when a disk controller becomes defective. 
6.  **I/O Protection –** 
    Errors and the issue of protection are closely related. A user process may attempt to issue illegal I/O instructions to disrupt the normal function of a system. We can use the various mechanisms to ensure that such disruption cannot take place in the system. 

    为了防止非法的输入/输出访问，我们将所有的输入/输出指令定义为特权指令。用户不能直接发出输入输出指令。