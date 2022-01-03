# 克雷 T3E 架构

> 原文:[https://www.geeksforgeeks.org/cray-t3e-architecture/](https://www.geeksforgeeks.org/cray-t3e-architecture/)

**Cray T3E 架构**是用于超算系统的微处理器。Cray T3E 是一种 RISC(精简指令集计算机)架构，是非常强大的微处理器。T3E 系统包含大量的处理元素(PE)。每个 PE 由一个 DEC Alpha EV5 RISC 微处理器组成。

**Cray T3E 架构的设计特点如下:**

*   CRAY T3E 是一款可扩展的共享内存多处理器
*   系统架构旨在容忍延迟并增强可扩展性。
*   T3E 系统完全自主托管，运行 UNICOS/mk 分布式操作系统。
*   Cray T3E 的可扩展性可以处理增加的处理器和内存，以及更大的 I/O 和互连带宽。
*   大范围实施
*   Cray T3E 系统有自己的本地内存。

**Cray T3E 架构:**

1.  **内存:**
    T3E 有自己的本地内存，容量从 64 兆到 2gb。所有地址都用字节表示。两个连续的字节组成一个字，四个字节组成一个长字，八个字节组成一个四字。

*   **Register:**
    The Alpha architecture includes 32 general-purpose register from R0 to R31\. R31 always contain the value zero. Each general-purpose register in Alpha architecture of Cray T3E system is 64-bit long. Other than 32 general-purpose register there are also 32 floating-point registers from F0 to F31 and F31 always contain zero value. Each floating-point register have 64-bit length.*   **Data Formats:**
    *   整数存储为长词或四词。
    *   字符用 8 位 ASCII 码表示。
    *   浮点用两种不同的浮点格式表示。*   **Instruction Formats:**
    In Cray T3E architecture there are basically five instruction formats. All of these formats are 32 bit long and first 6 bits of the instruction word represents the opcode. Some instruction formats also have an “functional” field in which function of different registers are specified.*   **Addressing Modes:**
    Just like in most of the RISC architectures, the only instructions that deals with memory are load, store and branch instructions.
    There are two modes to address operands in memory:

    ```
    Mode                      Target address(TA) calculation
    PC-relative               TA=(PC) + displacement

    Register indirect         TA=(register) + displacement
    with displacement 
    ```

    **移位模式间接寄存器**用于加载、存储和子程序跳转操作。
    **PC-相对模式**用于条件分支和无条件分支。

    *   **Instruction Set:**
    Cray T3E architecture has approximately 130 machine instructions. Cray T3E architecture uses a large number of instructions to do the implementation of operations as fast as possible.*   **输入输出:**
    Cray T3E 架构使用多个端口执行 I/O，这些多个端口有一个或多个 I/O 通道，集成到互连处理节点的网络中。所有这些通道都是可控制的，并且可以从所有处理单元访问。