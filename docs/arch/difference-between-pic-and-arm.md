# PIC 和 ARM 的区别

> 原文:[https://www . geesforgeks . org/pic 和 arm 的区别/](https://www.geeksforgeeks.org/difference-between-pic-and-arm/)

先决条件–[微控制器(C)和微处理器(P)的区别](https://www.geeksforgeeks.org/whats-difference-between-microcontoller-%C2%B5c-and-microprocessor-%C2%B5p/)

微控制器是一个单一的集成电路，相当于一台小型的独立计算机，它被设计来管理嵌入式系统中的特定操作。一个微控制器包含处理单元和少量内存( [ROM、RAM](https://www.geeksforgeeks.org/random-access-memory-ram-and-read-only-memory-rom/) 等)。)，用于外设、定时器等的输入/输出端口较少。我们可以说它是一台小而低成本的微型计算机。ARM 和 PIC 属于微控制器家族。PIC 微控制器和 ARM 微控制器在不同的体系结构和不同的指令集、速度、转换、内存、功耗、总线宽度等方面有所不同。现在让我们详细了解它们之间的区别。

**1。PIC 微控制器:**
PIC 微控制器最初被称为外设接口控制器，现在被称为可编程智能计算机。它属于微芯片技术制造的微控制器家族。它最初是由通用仪器微电子公司在 1993 年开发的。它可以被编程来执行大量的任务。PIC 微控制器有 8 位、16 位和 32 位三种。它基于 [RISC 指令集架构](https://www.geeksforgeeks.org/computer-organization-risc-and-cisc/)和哈弗内存架构。

**2。ARM 微控制器:**
ARM 微控制器是由 Acron 电脑机构推出的高级 RISC 机，由苹果、英伟达、高通、摩托罗拉、ST 微电子、三星电子、TI 等公司制造。ARM 处理器属于基于精简指令集计算机(RISC)的 CPU 家族，ARM 微处理器与 RAM、ROM 等外设集成在一个芯片上，我们得到了一个 ARM 微控制器。LPC2148 是 ARM 微控制器的一个例子。它基于精简指令集架构。它是成本敏感的高性能器件，广泛应用于工业仪表控制系统等嵌入式应用。

**PIC 和 ARM 的区别:**

<center>

| 没有。 | 电影 | 手臂ˌ武器ˌ袖子ˌ装备 |
| 01. | PIC 微控制器指外围接口控制器。 | ARM 微控制器指的是高级 RISC 机。 |
| 02. | PIC 微控制器有 8 位、16 位和 32 位三种。 | ARM 微控制器有 32 位版本，大多数也有 64 位版本。 |
| 03. | 它支持 PIC、UART、USART、CAN、LIN、以太网、SPI、I2S 通信协议。 | 它支持 UART、USART、SPI、CAN、LIN、I2C、以太网、I2S、DSP、SAI 通信协议。 |
| 04. | 它的有效指令速率为每条指令 4 个时钟周期。 | 它的有效指令速率为每条指令 1 个时钟周期。 |
| 05. | 它使用静态随机存取存储器，闪存。 | 它使用闪存、软件随机存取存储器、可编程只读存储器。 |
| 06. | 它基于 RISC 的一些特性。 | 它基于 RISC 指令集架构。 |
| 07. | 它基于哈佛的内存架构。 | 它基于修改后的哈佛建筑。 |
| 08. | PIC 微控制器系列包括 PIC16、PIC17、PIC18、PIC24、PIC32。 | ARM 微控制器系列包括 ARMv4、5、6、7 和系列。 |
| 09. | 它有很好的社区支持。 | 它拥有广泛的社区支持。 |
| 10. | 它的制造商是微芯片公司。 | 其制造商有苹果、英伟达、高通、三星电子、TI 等。 |
| 11. | 与功能相比，它的平均成本更低。 | 与这些特性相比，它的成本较低。 |
| 12. | 流行的微控制器包括 PIC18fXX8、PIC16f88X、PIC32MXX。 | 流行的微控制器有 LPC2148、ARM Cortex-M0 到 ARM Cortex-M7 等。 |

</center>