# 运行时存储组织

> 原文:[https://www . geesforgeks . org/run-time-storage-organization/](https://www.geeksforgeeks.org/run-time-storage-organization/)

[运行时环境](https://www.geeksforgeeks.org/runtime-environments-in-compiler-design/)是目标计算机寄存器和内存的结构，用于管理内存和维护指导程序执行过程所需的信息。

**运行时环境的类型–**

1.  **Fully Static :**
    Fully static runtime environment may be useful for the languages in which pointers or dynamic allocation is not possible in addition to no support for recursive function calls.
    *   每个过程只有一个激活记录，该记录是在执行之前分配的。
    *   变量通过固定地址直接访问。
    *   记账开销小；即至多返回地址可能必须存储在激活记录中。
    *   调用序列包括计算每个参数地址，并将其存储到适当的参数位置，保存返回地址，然后进行跳转。

2.  **Stack Based :**
    In this, activation records are allocated (push of the activation record) whenever a function call is made. The necessary memory is taken from the stack portion of the program. When program execution return from the function the memory used by the activation record is deallocated (pop of the activation record). Thus, the stack grows and shrinks with the chain of function calls.
3.  **Fully Dynamic :**
    Functional language such as Lisp, ML, etc. use this style of call stack management. Silently, here activation record is deallocated only when all references to them have disappeared, and this requires the activation records to dynamically freed at arbitrary times during execution. Memory manager (garbage collector) is needed.

    处理这种管理的数据结构是堆，这也称为堆管理。

**[【激活记录】](https://www.geeksforgeeks.org/runtime-environments-in-compiler-design/)–**
单次执行过程所需的信息通过一个名为“激活记录”的连续存储块进行管理。

当进入一个过程时分配一个激活记录，当退出该过程时释放该记录。它包含临时数据、本地数据、机器状态、可选访问链接、可选控制链接、实际参数和返回值。

*   **[程序计数器(PC)](https://practice.geeksforgeeks.org/problems/what-is-program-counter)–**其值是下一条要执行的指令的地址。
*   **堆栈指针(SP)–**的值是(堆栈顶部，ToS)的顶部。
*   **指向当前激活的帧指针(FP)–**。

**注:**
激活记录从静态区(如 Fortran 77)、堆栈区(如 C 或 Pascal)和堆区(如 lisp)中的一个分配。