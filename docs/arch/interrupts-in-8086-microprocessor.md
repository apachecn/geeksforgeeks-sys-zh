# 8086 微处理器中的中断

> 原文:[https://www . geesforgeks . org/interrupts-in-8086-微处理器/](https://www.geeksforgeeks.org/interrupts-in-8086-microprocessor/)

中断是一种暂时停止微处理器执行不同任务，然后返回到前一个任务的情况。中断是请求中央处理器注意的事件或信号。这种暂停允许外围设备访问微处理器。

每当发生中断时，处理器就完成当前指令的执行，并开始执行中断服务例程或中断处理程序。ISR 是一个程序，它告诉处理器当中断发生时该做什么。ISR 执行后，控制返回到中断的主程序。

在 8086 微处理器中，当微处理器遇到中断时，执行下列任务:

1.  标志寄存器的值被推入堆栈。这意味着首先 SP(堆栈指针)的值减 2，然后标志寄存器的值被推到堆栈段的内存地址。
2.  CS(代码段)的起始内存地址值被推入堆栈。
3.  IP(指令指针)的值被推入堆栈。
4.  从字位置加载 IP(中断类型)* 04。
5.  从下一个单词位置加载 CS。
6.  中断和陷阱标志重置为 0。

8086 微处理器中存在的不同类型的中断由下式给出:

1.  **硬件中断–**
    硬件中断是由任何外围设备通过指定引脚向微处理器发送信号而引起的中断。8086 微处理器有两个硬件中断。它们是:
    *   *(A) NMI(不可屏蔽中断)–*这是一个无法禁用的单引脚不可屏蔽硬件中断。它是 8086 微处理器中优先级最高的中断。执行后，该中断产生一个类型 2 中断。IP 从字位置 00008 H 加载，CS 从字位置 0000A H 加载。
    *   *(B) INTR(中断请求)–*它提供单个中断请求，并由输入/输出端口激活。该中断可以被屏蔽或延迟。这是一个电平触发中断。它可以接收任何中断类型，因此 IP 和 CS 的值将根据接收到的中断类型而变化。
2.  **Software Interrupts –** These are instructions that are inserted within the program to generate interrupts. There are 256 software interrupts in 8086 microprocessor. The instructions are of the format INT type where type ranges from 00 to FF. The starting address ranges from 00000 H to 003FF H. These are 2 byte instructions. IP is loaded from type * 04 H and CS is loaded from the next address give by (type * 04) + 02 H. Some important software interrupts are:
    *   (A) *TYPE 0* 对应于除以零(0)。
    *   (二)*类型 1* 用于程序调试的单步执行。
    *   (C) *TYPE 2* 代表 NMI，用于停电情况。
    *   (D) *类型 3* 代表断点中断。
    *   (E) *TYPE 4* 是溢出中断。

    参见–8085 微处理器中的[中断](https://www.geeksforgeeks.org/interrupts-8085-microprocessor/)