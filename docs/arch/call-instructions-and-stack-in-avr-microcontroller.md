# 调用 AVR 微控制器中的指令和堆栈

> 原文:[https://www . geesforgeks . org/call-instructions-and-stack-in-AVR-microcontroller/](https://www.geeksforgeeks.org/call-instructions-and-stack-in-avr-microcontroller/)

CALL 是一种控制转移指令，用于调用特定的子程序。子程序是需要频繁执行的指令块。

在 AVR 中，调用子程序有如下 4 条指令。

1.  **[CALL(调用子程序)](https://www.geeksforgeeks.org/subroutine-subroutine-nesting-and-stack-memory/)**
2.  **RCALL(相对调用子程序)**
3.  **ICALL(间接呼叫 Z)**
4.  **EICALL(延伸间接呼叫 Z)**

**[CALL](https://www.geeksforgeeks.org/subroutine-subroutine-nesting-and-stack-memory/) :**
在这个 4 字节指令中，10 位用于操作码，另外 22 位用于目标子程序的地址，就像 JMP 指令一样。在这种情况下，AVR 的 4M 地址空间为 000000-$3FFFFF，它可以用来调用给定地址范围内的子程序。

为了确保 AVR 知道子程序执行后从哪里回来，微控制器会自动将指令的地址保存在堆栈中 CALL 指令的正下方。在完成子程序的执行后，RET 指令将控制权转移回调用者。因此，每个子程序的最后都有一个 RET 指令。

**[栈](https://www.geeksforgeeks.org/subroutine-subroutine-nesting-and-stack-memory/) :**
栈是 CPU RAM 中临时存储信息的部分。中央处理器需要这个存储，因为只有有限数量的寄存器。用于访问堆栈的寄存器称为堆栈指针(SP)寄存器。
在 I/O 内存空间中，有 2 个寄存器分别为 SPL(SP 的低字节)和 SPH(即
SP 的高字节)。SP 由这两个寄存器实现。

在内存超过 256 字节的 AVR 中，有两个 8 位寄存器。另一方面，如果内存小于 256 字节，SP 仅由 SPL 组成，因为 8 位寄存器只能寻址 256 字节的内存。

将中央处理器信息存储在堆栈上称为推送操作，将堆栈内容加载回中央处理器称为弹出操作。

**推栈:**
栈指针(SP)指向栈顶。当我们将数据推送到堆栈上时，数据会保存在 SP 指向的位置，并且 SP 会递减 1。

要将寄存器推入堆栈，我们使用 push 指令。

```
PUSH  Rr; 
Rr can be any general-purpose register (R0 - R31)

```

**从堆栈中弹出:**
将堆栈中的内容弹出回寄存器是推送的相反功能。当执行 POP 指令时，SP 递增 1，堆栈的顶部位置被复制回寄存器。这意味着堆栈是后进先出的。

为了从堆栈中取回数据，我们使用了 POP 指令。

```
POP  Rr; 
Rr can be any general-purpose register (R0 - R31)

```

**初始化堆栈指针:**
不同的 AVR 有不同的内存量。在 AVR 汇编程序中，RAMEND 指定最后一个 RAM 位置的地址。因此，如果我们想要初始化 SP，使其指向最后一个内存位置，我们可以简单地将 RAMEND 加载到 SP 中。请注意，SP 由两个寄存器组成，SPH 和 SPL。因此，我们将 RAMEND 的高字节加载到 SPH，将 RAMEND 的低字节加载到 SPL。

**CALL 指令、RET 指令及栈的作用:**
CALL 指令执行时，CALL 指令下面的指令地址被推送到栈上。当子程序的执行结束并执行 RET 时，CALL 指令下面的指令地址被载入程序计数器并被执行。