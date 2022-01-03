# 操作系统中的进程创建和删除

> 原文:[https://www . geeksforgeeks . org/操作系统中的进程创建和删除/](https://www.geeksforgeeks.org/process-creation-and-deletions-in-operating-systems/)

先决条件–[操作系统中进程的状态](https://www.geeksforgeeks.org/states-of-a-process-in-operating-systems/)

可以对流程执行两个基本操作:创建和删除。它们被解释为

### **流程创建:**

1.创建新流程时，操作系统会为其分配唯一的流程标识符(PID)，并在主流程表中插入一个新条目。

2.然后，分配程序、数据和堆栈等流程所有元素所需的存储空间，包括其[流程控制块](https://www.geeksforgeeks.org/process-table-and-process-control-block-pcb/)(印刷电路板)的空间。

3.接下来，初始化印刷电路板中的各种值，例如，

1.  The process identification part is filled with the PID assigned to it in step (1) and its parent PID.
2.  Except for the stack pointer and program counter, the values of the processor registers are mostly filled with zeros. The stack pointer is filled with the address of the stack assigned to it in step (ii), and the program counter is filled with the address of its program entry point.
3.  The process status information will be set to "New".
4.  The default priority is the lowest, but the user can specify any priority during the creation process.

4.然后，操作系统会将该进程链接到调度队列，进程状态将从“新”更改为“就绪”。现在进程在争夺 CPU。

5.此外，操作系统将创建一些其他数据结构，如日志文件或会计文件，以跟踪进程活动。

### **流程删除:**

进程在执行完最后一条语句后自行终止，然后操作系统使用 exit()系统调用删除其上下文。然后，该进程拥有的所有资源，如物理和虚拟内存、10 个缓冲区、打开的文件等。，被操作系统收回。进程 P 可以被操作系统或进程 P 的父进程终止

由于以下原因之一，父进程可能会终止:

1.  When there is no need to assign tasks to child processes now.
2.  When children take more resources than the limit.
3.  The parent of this procedure is so exciting that all its children are deleted. This is called cascade termination.