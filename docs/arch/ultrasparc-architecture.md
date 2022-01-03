# UltraSPARC 架构

> 原文:[https://www.geeksforgeeks.org/ultrasparc-architecture/](https://www.geeksforgeeks.org/ultrasparc-architecture/)

**UltraSPARC 架构**属于 SPARC(可扩展处理器架构)处理器家族。这种体系结构适用于各种微型计算机和超级计算机。UltraSPARC 是精简指令集计算机的一个例子。

**UltraSPARC 架构:**

1.  **Memory:**
    Memory consists of 8 bit-bytes. Two consecutive bytes form a halfword, four bytes form a word, eight bytes form a doubleword. UltraSPARC programs operates on **Virtual Address Space** (2<sup>64</sup> bytes). Virtual Address Space is divided into pages and these pages are stored in the physical memory or on disk.

2.  **Registers:**
    UltraSPARC architecture include a large file of registers that have more than 100 general purpose registers. Any procedure can access only 32 registers only. The SPARC hardware uses window into registers file to manage all the operations of different procedures.
    Beside these register files, UltraSPARC also uses Program Counter, code register, and other control registers.
3.  **Data Formats:**
    *   整数存储为 8 位、16 位、32 位或 64 位二进制数。
    *   字符用 8 位 ASCII 码表示。
    *   浮点用三种不同的格式表示，即单精度格式、双精度格式和四精度格式。
4.  **Instruction Formats:**
    SPARC architecture use three basic instruction formats. All the instructions are of 32-bit long and first two bits are used to identify which format is being used.

    **格式 1-** 用于调用指令。

    ![](img/6d95a6b4e9eb0ffe07b22bdb912bdb77.png)

    **格式 2-** 用于分支指令。

    ![](img/4db0b634bfb9ae522f3238c1497ccd1e.png)

    **格式 3-** 由所有剩余指令使用，如寄存器加载和存储。

    ![](img/ac631f9ca0a2afd5b32521e3dd85fcbe.png)

    哪里，

    ```
    n=Indirect mode, 
    i=Immediate addressing, 
    x=Index addressing, 
    b=Base addressing, 
    p= Program counter, 
    e=Exponential addressing 
    ```

5.  **Addressing Modes:**
    Operands in memory are addressed using one of the following three modes:

    ```
    Mode                      Target address(TA) calculation
    PC-relative               TA=(PC) + displacement

    Register indirect         TA=(register) + displacement
    with displacement

    Register indirect         TA=(register-1) + (register-2)
    indexed

    ```

    *PC-relative 仅用于分支指令。*

6.  **Instruction Set:**
    This architecture have less number of instructions as compared to CISC machines. The only instructins that access memory are load and stores. All other instructions operates on register only. Instruction execution on a SPARC system is pipelined which means while one instruction is executed next one is being fetched from memory and decoded.
7.  **输入输出:**
    I/O 设备之间的通信和 SPARC 运算都是通过内存完成的。输入和输出可以用计算机的常规指令集来执行，不需要特殊的输入输出指令。