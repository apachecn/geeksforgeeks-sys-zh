# 操作系统的需求和功能

> 原文:[https://www . geesforgeks . org/操作系统的需求和功能/](https://www.geeksforgeeks.org/need-and-functions-of-operating-systems/)

**操作系统的目标:**
计算机系统的基本目标是执行用户程序并使任务更容易。各种应用程序和硬件系统被用来完成这项工作。操作系统是管理和控制整套资源并有效利用计算机每一部分的软件。
该图显示了操作系统如何作为硬件单元和应用程序之间的媒介。

![](img/0cddebcf3d7433aaea3131933ec1acdc.png)

**操作系统需求:**

*   **OS 作为应用程序的平台:**
    操作系统提供了一个平台，在这个平台之上，可以运行其他的程序，叫做应用程序。这些应用程序帮助用户轻松执行特定任务。它充当计算机和用户之间的接口。它的设计方式是在计算机上操作、控制和执行各种应用程序。

*   **管理输入输出单元:**
    操作系统还允许计算机管理自己的资源，如内存、显示器、键盘、打印机等。有效利用这些资源需要对其进行管理。操作系统控制各种系统输入输出资源，并根据用户或程序的要求分配给它们。

*   **一致的用户界面:**
    操作系统为用户提供了一个易于操作的用户界面，因此用户不必每次都学习不同的 UI，可以专注于内容并尽快提高工作效率。操作系统提供模板、UI 组件，让电脑的工作，对用户来说真的很容易。

*   **Multitasking:** 
    Operating System manages memory and allows multiple programs to run in their own space and even communicate with each other through shared memory. Multitasking gives users a good experience as they can perform several tasks on a computer at a time.

**操作系统的功能:**
操作系统有多种功能需要执行。操作系统的一些突出功能可以概括为:

*   [**处理器管理**](https://www.geeksforgeeks.org/gate-notes-operating-system-process-management-introduction/) **:** 处理中央处理器(CPU)的管理。操作系统负责将 CPU 时间分配给不同的进程。当一个进程在执行了分配的时间后完成了它的中央处理器处理，这被称为调度。操作系统使用各种调度技术:
    1.  [**【最短作业优先】(SJF**](https://www.geeksforgeeks.org/operating-system-shortest-job-first-scheduling-predicted-burst-time/) **)** :首先调度需要最短 CPU 时间的进程。
    2.  [**【循环调度】**](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) **:** 以循环方式为每个进程分配固定的 CPU 执行时间。
    3.  [**【基于优先级的调度】(**](https://www.geeksforgeeks.org/operating-system-priority-scheduling-different-arrival-time-set-2/) 【非抢占式】 [**)**](https://www.geeksforgeeks.org/operating-system-priority-scheduling-different-arrival-time-set-2/) **:** 在该调度中，进程根据其优先级进行调度，即优先级最高的进程优先调度。如果两个进程的优先级匹配，则根据到达时间进行调度。

*   **设备管理:**
    操作系统与硬件和连接的设备通信，并在它们和中央处理器之间保持平衡。这一点尤为重要，因为 CPU 的处理速度比 I/O 设备要快得多。为了优化中央处理器时间，操作系统采用了两种技术——缓冲和假脱机。

*   **缓冲:**
    在这种技术中，输入和输出数据暂时存储在输入缓冲区和输出缓冲区中。一旦用于输入或输出的信号分别被发送到中央处理器或从中央处理器发送，操作系统通过设备控制器将数据从输入设备移动到输入缓冲器，并且将用于输出设备的数据移动到输出缓冲器。在输入的情况下，如果缓冲区已满，操作系统会向处理存储在缓冲区中的数据的程序发送一个信号。当缓冲区变空时，程序通知操作系统重新加载缓冲区，输入操作继续。

*   [**【假脱机(同时在线外围设备操作)**](https://www.geeksforgeeks.org/what-exactly-spooling-is-all-about/) **:**
    这是一种设备管理技术，用于在同一输入/输出设备上处理不同的任务。当网络上有不同的用户共享相同的资源时，可能会有多个用户在同一时间点向其发出命令。因此，操作系统将每个用户的数据临时存储在资源所连接的计算机的硬盘上。单个用户不需要等待执行过程完成。相反，操作系统将数据从硬盘逐一发送到资源。
    **示例:**打印机

*   [**内存管理**](https://www.geeksforgeeks.org/operating-systems-gq/memory-management-gq/) **:**
    在计算机中，CPU 和 I/O 设备都与内存交互。当一个程序需要被执行时，它被加载到主存储器中，直到执行完成。此后，该内存空间被释放，并可用于其他程序。操作系统使用的常见内存管理技术是分区和虚拟内存。

*   **分区:**
    总内存分为大小相同或大小不同的各种分区。这有助于在内存中容纳大量程序。分区可以是固定的，即对于存储器中的所有程序保持不变，或者是可变的，即当程序加载到存储器上时分配存储器。后一种方法造成的内存浪费较少，但随着时间的推移，它可能会变得支离破碎。

*   [**【虚拟内存】**](https://www.geeksforgeeks.org/virtual-memory-operating-systems/) **:**
    这是操作系统使用的一种技术，允许用户加载比计算机主内存大的程序。在这种技术中，即使整个程序不能加载到主内存中，程序也能执行，从而提高内存利用率。

*   **文件管理:**
    操作系统管理计算机上的文件、文件夹和目录系统。计算机上的任何数据都以文件的形式存储，操作系统使用文件分配表(FAT)保存所有数据的信息。FAT 存储文件的一般信息，如文件名、类型(文本或二进制)、大小、起始地址和访问模式(顺序/索引顺序/直接/相对)。操作系统的文件管理器帮助创建、编辑、复制文件，为文件分配内存，并更新 FAT。操作系统还会注意以正确的访问权限打开文件，以读取或编辑它们。