# 简化教学计算机(SIC)

> 原文:[https://www . geesforgeks . org/简体-教学-计算机-sic/](https://www.geeksforgeeks.org/simplified-instructional-computer-sic/)

*简化教学计算机(SIC)* 是一种假设的计算机，具有在真实机器中经常发现的硬件特征。这台机器有两个版本:

1.  标准模型
2.  碳化硅/氙(额外设备或昂贵)

SIC 的目标程序可以在 SIX/XE 上正确执行，这就是所谓的向上兼容。

**SIC 机器架构/组件–**

**1。内存–**

*   内存是字节可寻址的，也就是说，字是通过其最低编号字节的位置来寻址的。
*   计算机内存中有 2^15 字节(1 字节= 8 位)
    3 个连续字节= 1 个字(24 位= 1 个字)

**2。寄存器–**

SIC 中有 5 个寄存器。每个寄存器都有一个与之关联的地址，称为寄存器号。每个寄存器的大小为 3 字节。基于寄存器大小，整数大小是依赖的。
I. A(累加器-0):用于数学运算。
二。x(索引寄存器-1):用于寻址。
三世。l(链接寄存器-2):在子程序的情况下，它存储指令的返回地址。
四。程序计数器 8:保存下一条要执行的指令的地址。
V. SW(状态字-9):包含多种信息

状态字寄存器:

![33333](img/08fabdbeb6bbb90332a8a74485186119.png)

*   **模式**位指用户模式(值=0)或监控模式(值=1)。它占用 1 位。[0]
*   **状态**位是指进程是处于运行状态(值=0)还是空闲状态(值=1)。它也占用 1 位。[1]
*   **id** 位指进程 id(PID)。它占用 3 位。[2-5]
*   **CC** 位指条件码，即告知设备是否准备好。它占用 2 位。【6-7】
    **屏蔽**位指中断屏蔽。它占用 4 位。[8-11]
*   **X** 指未使用的位。它也占用 4 位。[12-15]
*   **ICode** 指中断代码，即中断服务程序。它占据剩余的位。[16-23]

**3。数据格式–**

*   整数由 24 位表示。
*   负数用 2 的补码表示。
*   字符由 8 位 ASCII 值表示。
*   没有可用的浮点表示。

**4。指令格式–**
SIC 中的所有指令都是 24 位格式。

![666666](img/1dadd711b3ba207b6a791b3b8672eecd.png)

*   如果 x=0，则表示直接寻址模式。
*   如果 x=1，则表示索引寻址模式。

**5。指令集–**

*   加载和存储指令:将数据从累加器移动或存储到存储器，反之亦然。例如 LDA、STA、LDX、STX 等。
*   比较指令:用于根据累加器的内容比较内存中的数据。例如 COMP 数据。
*   算术指令:用于对累加器和存储器进行运算，并将结果存储在累加器中。例如 ADD、SUB、MUL、DIV 等。
*   条件跳转:比较累加器和内存的内容，根据条件执行任务。例如 JLT、JEQ、JGT
*   子程序链接:与子程序相关的指令。例如 JSUB、RSUB

**6。输入和输出–**
它是通过每次从累加器最右边的 8 位传输 1 个字节来执行的。每个设备都有 8 位唯一代码。
有 3 个输入输出指令:

*   测试设备测试设备是否准备好。状态字寄存器中的条件代码用于此目的。如果 cc
*   读取数据(RD)从器件读取一个字节，并存储在寄存器 a 中。
*   写数据(WD)将寄存器 A 中的一个字节写入器件。

**参考文献:**

利兰。贝克:系统编程导论，第三版，爱迪生-卫斯理，1997。