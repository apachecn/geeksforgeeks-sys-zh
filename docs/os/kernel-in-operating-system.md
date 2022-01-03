# 操作系统内核

> 原文:[https://www.geeksforgeeks.org/kernel-in-operating-system/](https://www.geeksforgeeks.org/kernel-in-operating-system/)

**[内核](https://www.geeksforgeeks.org/kernel-i-o-subsystem-in-operating-system/)** 是管理计算机和硬件操作的操作系统的核心组件。它基本上管理内存和 CPU 时间的操作。它是操作系统的核心组件。内核作为应用程序和数据处理之间的桥梁，通过进程间通信和系统调用在硬件级执行。

当操作系统被加载时，内核首先加载到内存中，并保持在内存中，直到操作系统再次关闭。它负责各种任务，如磁盘管理、任务管理和内存管理。

它决定哪个进程应该分配给处理器执行，哪个进程应该保存在主内存中执行。它基本上充当用户应用程序和硬件之间的接口。内核的主要目标是管理软件(即用户级应用程序)和硬件(即中央处理器和磁盘存储器)之间的通信。

**内核目标:**

*   在用户级应用程序和硬件之间建立通信。
*   决定传入进程的状态。
*   控制磁盘管理。
*   控制内存管理。
*   控制任务管理。

**籽粒类型:**

**1。[单片内核](https://www.geeksforgeeks.org/monolithic-kernel-and-key-differences-from-microkernel/)–**
它是所有操作系统服务都在内核空间运行的内核类型之一。它在系统组件之间有依赖关系。它有大量复杂的代码行。

**示例:**

```
Unix, Linux, Open VMS, XTS-400 etc.
```

*   **优势:**
    表现不错。
*   **劣势:**
    它在系统组件和百万行代码之间有依赖关系。

**2。[微内核](https://www.geeksforgeeks.org/microkernel-in-operating-systems/)–**
这是具有极简主义方法的内核类型。它有虚拟内存和线程调度。它更稳定，内核空间中的服务更少。它让用户空间得到休息。

**示例:**

```
Mach, L4, AmigaOS, Minix, K42 etc.
```

*   **优势:**
    比较稳定。

*   **Disadvantage :**
    There are lots of system calls and context switches.

    **3。**
    混合内核是单片内核和微内核的结合。它具有单片内核的速度和设计，以及微内核的模块化和稳定性。

    **示例:**

    ```
    Windows NT, Netware, BeOS etc.
    ```

    *   **优势:**
        它结合了单片内核和微内核。
    *   **劣势:**
        还是类似于单片内核。

    **4。exo Kernel–**
    它是遵循端到端原则的内核类型。它有尽可能少的硬件抽象。它将物理资源分配给应用程序。

    **示例:**

    ```
    Nemesis, ExOS etc.
    ```

    *   **优势:**
        硬件抽象最少。
    *   **劣势:**
        应用开发者的工作更多。

    **5。nano Kernel–**
    它是提供硬件抽象但没有系统服务的内核类型。微内核也没有系统服务，因此微内核和纳米内核变得相似。

    **示例:**

    ```
    EROS etc.
    ```

    *   **优势:**
        提供没有系统服务的硬件抽象。
    *   **缺点:**
        与微核相同，因此使用较少。