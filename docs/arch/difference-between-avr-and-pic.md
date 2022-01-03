# AVR 和 PIC 的区别

> 原文:[https://www . geesforgeks . org/difference-AVR-and-pic/](https://www.geeksforgeeks.org/difference-between-avr-and-pic/)

A [**微控制器**](https://practice.geeksforgeeks.org/problems/what-is-a-micro-controller) 是一个单一的集成电路(IC)，相当于一个小小的单机，是为执行嵌入式系统的特定任务而设计的。微控制器包含处理单元和少量内存([只读存储器、随机存取存储器](https://www.geeksforgeeks.org/random-access-memory-ram-and-read-only-memory-rom/)等)。)，用于外设、定时器等的输入/输出端口较少。AVR 和 PIC 属于微控制器家族。PIC 微控制器和 AVR 微控制器在不同的体系结构和不同的指令集、速度、转换、内存、功耗、总线宽度等方面有所不同。现在让我们详细了解它们之间的区别。

**1。AVR 微控制器:**
AVR 微控制器由 Atmel 公司于 1996 年制造。它基于 RISC 指令集架构(ISA)，也称为高级虚拟 RISC。AT90S8515 是 AVR 系列的初始微控制器。AVR 微控制器是最受欢迎的控制器类别，而且价格便宜。它被用于许多机器人应用。

**2。PIC 微控制器:**
PIC 代表外设接口控制器。PIC 单片机采用单片机开发。从实现和性能的角度来看，这种微控制器是一种非常快速简单的微控制器。这种微控制器易于编程，也易于与其他外设接口。

**AVR 和 PIC 的区别:**

<figure class="table">

| 没有。 | 自动电压调整（automatic voltage regulation 的缩写） | 电影 |
| 01. | AVR 代表高级虚拟 RISC 微控制器。 | PIC 代表外围接口控制器微控制器。 |
| 02. | AVR 微控制器总线宽度为 8/32 位。 | PIC 微控制器总线宽度为 8/16/32 位。 |
| 03. | 它支持 UART、USART、SPI、I2C 通信协议。 | 支持 PIC、UART、USART、LIN、CAN、以太网、SPI 通信协议。 |
| 04. | 其速度为 1 个时钟/指令周期。 | 它的速度是 4 个时钟/指令周期。 |
| 05. | AVR 微控制器基于 RISC 指令集架构。 | PIC 微控制器是基于 RISC 指令集架构的一些特性。 |
| 06. | 它基于哈佛建筑。 | 它基于修改后的哈佛建筑。 |
| 07. | AVR 系列包括 Tiny、Atmega、Xmega、专用 AVR。 | PIC 系列包括 PIC16、PIC17、PIC18、PIC24、PIC32。 |
| 08. | AVR 微控制器的制造商是 Atmel。 | PIC 微控制器的制造商是微芯片公司。 |
| 09. | 它是非常便宜和有效的微控制器。 | 这是非常便宜的微控制器。 |
| 10. | 最受欢迎的微控制器是阿杜伊诺社区的 Atmega8，16，32。 | 流行的微控制器有 PIC18fXX8、PIC16f88X、PIC32MXX。 |

</figure>