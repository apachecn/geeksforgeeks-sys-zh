# 机器指令类型

> 原文:[https://www . geesforgeks . org/机器指令类型/](https://www.geeksforgeeks.org/types-of-machine-instructions/)

**概述:**
根据执行的操作，机器指令可分为以下几类:

*   [数据传输指令](https://www.geeksforgeeks.org/data-transfer-instructions-8085-microprocessor/)。
*   [数据处理指令(计算)](https://www.geeksforgeeks.org/data-manipulation-instructions-in-computer-organization/) : [算术和逻辑指令](https://www.geeksforgeeks.org/arithmetic-instructions-8085-microprocessor/)。
*   [程序控制指令](https://www.geeksforgeeks.org/types-of-program-control-instructions/)。

**1。数据传输说明:**

将数据从一个位置(寄存器/存储器)传输到另一个位置(寄存器/存储器)而不改变数据的指令。支持的数据传输操作如下:

*   ***LOAD :*** 数据从内存传输到寄存器。
*   ***STORE :*** 数据从寄存器传输到存储器。
*   ***移动:*** 寄存器之间的数据传输。
*   ***输入:*** 将数据从输入设备传输到寄存器。
*   ***输出:*** 将数据从寄存器传输到输出设备。
*   ***PUSH :*** 从寄存器或内存获取数据到堆栈顶部。
*   ***POP :*** 从栈顶获取数据到内存或寄存器。
*   ***XCHG :*** 在内存和寄存器之间交换数据。

**2。** [**数据处理指令**](https://www.geeksforgeeks.org/data-manipulation-instructions-in-computer-organization/) **:**

*   **算术指令:**
    执行算术运算，如加、减、乘、除、增、减等。
    *例:* ADD、SUB、MUL、DIV、INC、DEC 等。
*   **逻辑指令:**
    执行位逻辑运算，如与、或、异或、非、移位、旋转等。
    *例:* AND、OR、NOT、XOR、SHL、SHR、ROL、ROR 等。
*   **算术和逻辑指令:**
    执行算术左移、算术右移等操作。
    *例:* SAL、SAR 等。

**3。程序控制说明:**

**- >比较测试指令:**要比较和测试状态标志，我们需要条件码寄存器的支持。 ***条件码寄存器(CCR)*** 具有以下标志位:

**(i) 5 个状态位:**表示算术逻辑运算后的情况。

*   **进位标志(C) :** 表示加法的进位和减法的借用
*   **溢出标志(V) :** 当操作结果超出可表示的范围时，CPU 将“V”标志设置为逻辑“1”。
*   **负标志(N) :** 也叫标志标志。指示以前的结果是负的还是正的。
*   **半进位(H) :** 仅用于 BCD(二进制编码十进制)运算。
*   **零标志(Z) :** 当结果为“0”时，Z 位设置为逻辑“1”，否则 Z=0。请注意，零是正数

**(ii)两个中断屏蔽位**

**(iii)一个停止禁用位**

**- >无条件分支指令:**导致执行顺序无条件改变到新位置。**例:** JUMP，goto 等。

**- >条件转移指令:**这些指令用于检查存储在条件代码寄存器中的值，以确定特定代码是否存在，如果存在，则进行转移。示例:

*   BL–分支小于–(
*   BGE–分支大于等于–(> =)
*   BNE–分支如果不相等–(！=)等。

**- >子程序:**它是一个存在于用户空间的程序片段，如果被另一个用户程序调用，它会执行一个定义良好的任务，并在完成时将控制权返回给调用程序。**例:** CALL，RET 指令。子程序用于:

*   常用代码段
*   库例程

**- >停止和中断指令:**如下–

**1。NOP 指令:**
表示无操作，不引起处理器状态的变化，除了程序计数器的前进。它可以用来同步时间。

**2。暂停指令:**
它使处理器有序暂停，保持空闲状态，直到被中断、跟踪、复位或外部动作重新启动。

**3。中断指令:**
它是一种机制，通过这种机制，输入/输出或指令可以暂停处理器的正常执行，并使自己得到服务。通常，特定的任务被分配给该中断信号。在微处理器中，中断用于外围设备和微处理器之间数据传输。说明是–

*   **RESET–**
    它重置处理器，这可能包括将寄存器设置为初始值、将程序计数器设置为初始位置、清除或设置中断以及向外部设备发送重置信号中的任何一项或全部。
*   **TRAP–**
    不可屏蔽，边沿触发中断。在矢量中断中，TRAP 的优先级最高。在突然断电的情况下，它会执行一个中断服务程序，并将数据从主存储器发送到备份存储器。使用保持信号可以延迟。它们可以通过重置微处理器来屏蔽。他们没有别的办法掩盖它。
*   **INTR–**
    这是一个等级触发且可屏蔽的中断。收到指令后，中央处理器将下一条指令的地址保存在堆栈上，并执行收到的指令。它的优先级最低。可以通过重置微处理器或 DI/SIM 指令将其禁用。