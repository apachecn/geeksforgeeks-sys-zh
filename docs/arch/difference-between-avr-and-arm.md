# AVR 和 ARM 的区别

> 原文:[https://www . geesforgeks . org/AVR 和 arm 的区别/](https://www.geeksforgeeks.org/difference-between-avr-and-arm/)

先决条件–[微控制器(C)和微处理器(P)的区别](https://www.geeksforgeeks.org/whats-difference-between-microcontoller-%C2%B5c-and-microprocessor-%C2%B5p/)

A **[微控制器](https://practice.geeksforgeeks.org/problems/what-is-a-micro-controller)** 是一个单一的集成电路(IC)，相当于一个小小的单机，是为执行嵌入式系统的特定任务而设计的。微控制器包含处理单元，但只有少量内存(只读存储器、随机存取存储器等)。)，用于外设、定时器等的 IO 端口很少。AVR 和 ARM 属于微控制器家族。但是 ARM 既可以用作微控制器，也可以用作微处理器。 **ARM 微控制器**和 **AVR 微控制器**在不同的架构和不同的指令集、速度、cast、内存、功耗、总线宽度等方面各不相同。现在让我们详细了解它们之间的区别。

**1。AVR 微控制器:**
AVR 微控制器由 Atmel 公司于 1996 年制造。它基于 RISC 指令集架构(ISA)，也称为高级虚拟 RISC。AT90S8515 是 AVR 系列的初始微控制器。AVR 微控制器是最受欢迎的控制器类别，而且价格便宜。它被用于许多机器人应用。

**2。 [ARM 微控制器](https://www.geeksforgeeks.org/arm-processor-and-its-features/) :**
ARM 微控制器由 Acron 电脑机构推出，由苹果、英伟达、高通、摩托罗拉、ST 微电子、三星电子、TI 等制造。它基于 [RISC 指令集架构(ISA)](https://www.geeksforgeeks.org/computer-organization-risc-and-cisc/) 也叫高级 RISC 微控制器。它是最受欢迎的微控制器，大多数行业将其用于嵌入式系统，因为它提供了大量功能，有利于生产外观出色的设备。

**AVR 和 ARM 的区别:**

<center>

| 没有。 | 自动电压调整（automatic voltage regulation 的缩写） | 手臂ˌ武器ˌ袖子ˌ装备 |
| 01. | AVR 微控制器是指高级虚拟 RISC (AVR)。 | ARM 微控制器是指高级 RISC 微控制器(ARM)。 |
| 02. | 它的总线宽度为 8 位或 32 位。 | 它的总线宽度为 32 位，也有 64 位。 |
| 03. | 它使用 ART、USART、SPI、I2C 通信协议。 | 它采用了 SPI、CAN、以太网、I2S、DSP、SAI、UART、USART 通信协议。 |
| 04. | 它的速度是每个指令周期 1 个时钟。 | 它的速度也是每个指令周期 1 个时钟。 |
| 05. | 它的制造商是 Atmel 公司。 | 其制造商有苹果、英伟达、高通、三星电子和 TI 等。 |
| 06. | 它使用闪存、静态随机存取存储器、可编程只读存储器。 | 它使用闪存、软件随机存取存储器、可编程只读存储器。 |
| 07. | 它的家族包括 Tiny、Atmega、Xmega、专用 AVR。 | 其系列包括 ARMv4、5、6、7 和系列。 |
| 08. | 既便宜又有效。 | 它提供高速操作。 |
| 09. | 受欢迎的微控制器包括 16 岁的 Atmega8 和 32 岁的 Arduino 社区。 | 流行的微控制器有 LPC2148、ARM Cortex-M0 到 ARM Cortex-M7 等。 |

</center>