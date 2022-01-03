# 【8051 和 ARM 的区别

> 原文:[https://www . geesforgeks . org/difference-8051-and-arm/](https://www.geeksforgeeks.org/difference-between-8051-and-arm/)

先决条件–[微控制器(C)和微处理器(P)](https://www.geeksforgeeks.org/whats-difference-between-microcontoller-%C2%B5c-and-microprocessor-%C2%B5p/)

一个**微控制器**是一个单一的集成电路(IC)，相当于很少的独立计算机，它被设计来执行嵌入式系统的特定任务。8051 和 ARM 属于微控制器家族。 **8051 微控制器**和 **ARM 微控制器**在不同的架构和不同的指令集、速度、cast、内存、功耗、总线宽度等方面各不相同。现在让我们详细了解它们到底是什么，以及它们之间的区别。

**1。 [8051 微控制器](https://www.geeksforgeeks.org/introduction-to-8051-microcontroller/) :**
它是一个 8 位系列的微控制器。它是一款入门级微控制器，用于全球大多数基本应用，功耗低，可用预算低。它是英特尔在 1981 年开发的。8051 微控制器具有串行通信、定时器、中断等多种功能。这种微控制器用于各种设备，主要领域包括汽车、医疗设备和能源管理。现在，8051 微控制器可能看起来有点过时，但仍然建议将其作为用 8051 微控制器开始微控制器概念工作的最佳平台，尽管随着 AVR 社区 Arduino 的引入，这一趋势似乎已经改变。

**2。 [ARM 微控制器](https://www.geeksforgeeks.org/arm-processor-and-its-features/) :**
ARM 微控制器由 Acron 电脑机构推出，由苹果、英伟达、高通、摩托罗拉、ST 微电子、三星电子、TI 等制造。ARM 处理器属于基于精简指令集计算机(RISC)的 CPU 家族，ARM 微处理器与 RAM、ROM 等外设集成在一个芯片上，我们得到了一个 ARM 微控制器，例如 LPC2148。它基于 [RISC 指令集架构(ISA)](https://www.geeksforgeeks.org/computer-organization-risc-and-cisc/) 也叫高级 RISC 机。它是最受欢迎的微控制器，大多数行业将其用于嵌入式系统，因为它提供了大量功能，有利于生产外观出色的设备。

**8051 和 ARM 的区别:**

<center>

| 没有。 | Eight thousand and fifty-one | 手臂ˌ武器ˌ袖子ˌ装备 |
| 1. | 8051 微控制器中有 8 位标准核心总线宽度。 | 大多数 32 位总线宽度出现在 ARM 微控制器中，也有 64 位可用。 |
| 2. | 它的速度是每机器周期 12 个时钟周期。 | 它的速度是每机器周期 1 个时钟周期。 |
| 3. | 使用了 UART、USART、I2C、SPI、通信协议。 | 使用了通用异步收发器、通用异步收发器、以太网、I2S、数字信号处理器、串行接口、CAN、LIN、I2C 通信协议。 |
| 4. | 8051 微控制器采用闪存、只读存储器、静态随机存储器。 | ARM 微控制器采用闪存、EEPROM、SDRAM 存储器。 |
| 5. | 它基于 CISC 指令集架构。 | 它基于 RISC 指令集架构。 |
| 6. | 8051 微控制器是基于哈佛的架构，但它允许我们连接外部存储器，模拟冯·诺依曼的架构。 | pic 微控制器基于哈佛架构。 |
| 7. | 8051 微控制器功耗一般。 | ARM 微控制器功耗低。 |
| 8. | 它的家族包括 8051 个变种。 | 其系列包括 ARMv4、5、6、7 和 cortex 系列。 |
| 9. | 其制造商有 Atmel、恩智浦、硅实验室、达拉斯、塞浦路斯、英飞凌等。 | 其制造商有英伟达、高通、苹果、三星电子、TI 等。 |
| 10. | 与所提供的功能相比，8051 微控制器的成本非常低。 | 与所提供的功能相比，ARM 微控制器的成本较低。 |
| 11. | 流行的微控制器有 AT89C51、P89v51 等。 | 流行的微控制器包括 ARM Cortex-M0 到 ARM Cortex-M7 等。 |

</center>