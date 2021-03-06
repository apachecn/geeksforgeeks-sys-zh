# 操作系统功能

> 原文:[https://www . geesforgeks . org/functions-of-operating-system/](https://www.geeksforgeeks.org/functions-of-operating-system/)

先决条件–[操作系统介绍–第 1 集](https://www.geeksforgeeks.org/operating-system-introduction-operating-system-set-1/)
一个**操作系统**充当用户和计算机硬件之间的通信桥梁(接口)。操作系统的目的是提供一个平台，用户可以在这个平台上以方便有效的方式执行程序。

操作系统是一种管理计算机硬件分配的软件。硬件的协调必须适当，以确保计算机系统的正确工作，并防止用户程序干扰系统的正常工作。
示例:就像老板给员工下订单一样，我们以类似的方式请求或传递订单给操作系统。操作系统的主要目标是使计算机环境更方便使用，次要目标是以最有效的方式使用资源。

**什么是** **操作系统？**
操作系统是执行应用程序的程序，充当用户和计算机硬件之间的通信桥梁(接口)。

操作系统执行的主要任务是资源和服务的分配，例如内存、设备、处理器和信息的分配。操作系统还包括管理这些资源的程序，如流量控制器、调度程序、内存管理模块、输入/输出程序和文件系统。

**操作系统的重要功能:**

1.  **安全–**
    操作系统使用密码保护来保护用户数据和类似的其他技术。它还可以防止未经授权访问程序和用户数据。

2.  **控制系统性能–**
    监控整体系统运行状况，帮助提高性能。记录服务请求和系统响应之间的响应时间，以获得系统运行状况的完整视图。这可以通过提供解决问题所需的重要信息来帮助提高性能。

3.  **作业核算–**
    操作系统跟踪各种任务和用户使用的时间和资源，这些信息可用于跟踪特定用户或用户组的资源使用情况。

4.  **错误检测辅助工具–**
    操作系统不断监控系统，以检测错误并避免计算机系统出现故障。

5.  **其他软件和用户之间的协调–**
    操作系统还协调和分配解释器、编译器、汇编器和其他软件给计算机系统的不同用户。

6.  **Memory Management –** 
    The operating system manages the Primary Memory or Main Memory. Main memory is made up of a large array of bytes or words where each byte or word is assigned a certain address. Main memory is fast storage and it can be accessed directly by the CPU. For a program to be executed, it should be first loaded in the main memory. An Operating System performs the following activities for memory management: 

    它跟踪主内存，即哪个用户程序使用了哪些字节的内存。已经分配的内存地址和尚未使用的内存地址。在多道程序设计中，操作系统决定进程被授权访问内存的顺序以及访问时间。它在进程请求内存时将内存分配给进程，并在进程终止或正在执行输入/输出操作时释放内存。

7.  **Processor Management –** 
    In a multi-programming environment, the OS decides the order in which processes have access to the processor, and how much processing time each process has. This function of OS is called process scheduling. An Operating System performs the following activities for processor management. 

    跟踪流程的状态。执行这一任务的程序被称为交通控制器。将作为处理器的中央处理器分配给一个进程。当不再需要某个进程时，取消分配处理器。

8.  **设备管理–**
    操作系统通过各自的驱动程序管理设备通信。它执行以下设备管理活动。跟踪连接到系统的所有设备。指定负责每个设备的程序，称为输入/输出控制器。决定哪个进程可以访问某个设备以及访问多长时间。以有效且高效的方式分配设备。当不再需要设备时，取消分配设备。

9.  **文件管理–**
    文件系统被组织到目录中，以便高效或轻松地导航和使用。这些目录可能包含其他目录和其他文件。操作系统执行以下文件管理活动。它跟踪信息的存储位置、用户访问设置和每个文件的状态等等……这些设施统称为文件系统。

此外，操作系统还以某种形式向计算机系统提供某些服务。
操作系统向用户提供某些服务，这些服务可以通过以下方式列出:

1.  **程序执行**:操作系统负责所有类型程序的执行，无论是用户程序还是系统程序。操作系统利用各种可用资源来高效运行所有类型的功能。
2.  **处理输入输出操作**:操作系统负责处理各种输入，即来自键盘、鼠标、桌面等的输入。操作系统以最合适的方式对各种输入和输出进行所有接口。
    例如，所有类型的外围设备(如鼠标或键盘)的性质都有所不同，操作系统负责处理它们之间的数据。
3.  **操作文件系统**:操作系统负责决定所有类型数据或文件的存储，即软盘/硬盘/笔式驱动器等。操作系统决定如何操作和存储数据。
4.  **错误检测和处理**:操作系统负责检测任何任务时可能出现的任何类型的错误或 bug。安全良好的操作系统有时也可以作为一种对策，防止任何外部来源对计算机系统的任何形式的破坏，并可能对其进行处理。
5.  **资源分配:**操作系统通过决定哪些资源由谁使用多长时间来确保所有可用资源的正确使用。所有的决定都是由操作系统做出的。
6.  **记账:**操作系统跟踪一次在计算机系统中发生的所有功能的账户。操作系统会记录所有详细信息，如发生的错误类型。
7.  **信息和资源保护:**操作系统负责以最受保护的方式使用机器上所有可用的信息和资源。操作系统必须阻止任何外部资源阻碍任何类型的数据或信息的企图。

所有这些服务都由操作系统保证，以方便用户使编程任务更容易。所有不同类型的操作系统或多或少都提供相同的服务。