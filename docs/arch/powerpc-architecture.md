# PowerPC 架构

> 原文:[https://www.geeksforgeeks.org/powerpc-architecture/](https://www.geeksforgeeks.org/powerpc-architecture/)

**PowerPC 架构**是个人电脑的微处理器。PowerPC 是一种精简指令集计算机(RISC)架构，是非常强大和低成本的微处理器。RISC 架构试图让处理器尽可能忙碌。

PowerPC 的设计特点如下:

*   大范围实施
*   简单的处理器设计
*   超标量体系结构
*   多处理器功能
*   64 位架构
*   支持大端和小端模式下的操作。PowerPC 可以在运行时从一种模式切换到另一种模式。
*   浮点指令的独立浮点寄存器组

**PowerPC 机器架构:**

*   **内存:**
    内存由 8 位字节组成。两个连续的字节形成一个半字，四个字节形成一个字，八个字节形成一个双字，十六个字节形成一个四字。PowerPC 程序可以使用**虚拟地址空间** (2 <sup>64</sup> 字节)编写。地址空间被分成固定长度的段，这些段被进一步分成页。
*   **寄存器:**
    从 GPR0 到 GPR31 共有 32 个通用寄存器(GPR)。每个寄存器的长度为 64 位。通用寄存器用于存储和处理数据和地址。由于 PowerPC 机器支持浮点数据格式，因此它具有用于计算的浮点单元。
    PowerPC 架构支持的一些寄存器包括:

```
Register                   Operations
Link Register(LR)          Contain address to return at 
                           the end of the function call

Condition Register         Signify the result of an
(CR)                       instruction

Count Register             For Loop count
(CTR) 
```

*   **数据格式:**
    *   整数存储为 8 位、16 位、32 位或 64 位二进制数。
    *   字符用 8 位 ASCII 码表示。
    *   浮点用两种不同的浮点格式表示，即单精度格式和双精度格式。
*   **指令格式:**
    PowerPC 支持七种基本指令格式。所有这些指令格式都是 32 位长。与 SPARC 等其它 RISC 系统相比，PowerPC 体系结构指令格式具有更多的多样性和复杂性。PowerPC 的位编号与大多数其他定义相反:

```
bit 0 is the most significant bit, and 
bit 31 is the least significant bit 
```

指令首先被称为主操作码的字段中的高 6 位解码。其余 26 位包含操作数说明符、立即操作数和扩展操作码的字段，这些可能是保留位或字段。

*   **寻址模式:**
    加载和存储操作根据操作数值使用以下三种寻址模式之一:

```
Mode                      Target address(TA) calculation
Register indirect         TA=(register)

Register indirect         TA=(register-1) + (register-2)
with index

Register indirect         TA=(register) + displacement
with immediate
index 
```

分支指令使用以下三种寻址模式之一:

```
Mode                      Target address(TA) calculation
Absolute                  TA=actual address

Relative                  TA=current instruction address + displacement

Link Register             TA=(LR) 

Count Register            TA=(CR) 
```

*   **指令集:**
    PowerPC 架构比其他 RISC 系统更复杂。因此 PowerPC 架构大约有 200 条机器指令。该体系结构遵循指令的流水线执行，这意味着当一个指令被执行时，下一个指令被从存储器中取出并解码。
*   **Input and Output:** 
    PowerPC architecture follows two different methods for performing I/O operations. In one approach Virtual address space is used while in the other approach I/O is performed using Virtual memory management.