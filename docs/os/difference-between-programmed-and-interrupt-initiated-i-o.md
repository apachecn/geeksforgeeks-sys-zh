# 编程输入输出和中断启动输入输出的区别

> 原文:[https://www . geesforgeks . org/编程和中断启动 i-o 之间的区别/](https://www.geeksforgeeks.org/difference-between-programmed-and-interrupt-initiated-i-o/)

先决条件–[输入/输出接口(中断和直接存储器存取模式)](https://www.geeksforgeeks.org/io-interface-interrupt-dma-mode/)
中央处理器和输入/输出设备之间的数据传输可以在多种模式下完成。这是三种可能的模式:

1.  编程输入输出
2.  中断启动的输入输出
3.  直接存储器存取

在本文中，我们将只讨论前两种模式。

**1。编程输入/输出:**
在这种模式下，数据传输由写在计算机程序中的指令启动。将数据从设备存储到中央处理器需要输入指令，将数据从中央处理器传输到设备需要存储指令。通过这种模式的数据传输需要中央处理器持续监控外围设备，并在传输开始后监控新传输的可能性。因此，中央处理器一直处于循环状态，直到输入/输出设备指示它准备好进行数据传输。因此，编程输入/输出是一个耗时的过程，会使处理器不必要地忙碌，并导致 CPU 周期的浪费。
这可以通过使用中断设施来克服。这构成了中断启动输入/输出的基础

**2。中断启动的输入/输出:**
该模式使用中断工具和特殊命令来通知接口在数据可用且接口准备好数据传输时发出中断命令。同时，中央处理器继续执行其他任务，不需要检查标志。当标志置位时，接口被通知并启动中断。该中断导致中央处理器偏离其响应输入/输出传输的方式。中央处理器通过将程序计数器的返回地址存储到内存堆栈中来响应信号，然后分支到处理输入/输出请求的服务。传输完成后，中央处理器返回到它正在执行的前一个任务。服务的分支地址可以通过两种方式选择，即矢量中断和非矢量中断。在矢量中断中，中断源向中央处理器提供分支信息，而在非矢量中断的情况下，分支地址被分配给存储器中的一个固定位置。

**编程输入输出和中断启动输入输出的区别:**

<figure class="table">

| 编程输入输出 | 中断启动的输入输出 |
| --- | --- |
| 数据传输是通过存储在计算机程序中的指令来启动的。每当有输入输出传输请求时，指令就从程序中执行。 | 输入/输出传输由向中央处理器发出的中断命令启动。 |
| 中央处理器停留在循环中，以了解设备是否准备好传输，并且必须持续监控外围设备。 | 当设备准备好进行数据传输时，由于中断命令会中断中央处理器，因此中央处理器不需要停留在循环中。 |
| 这导致了 CPU 周期的浪费，因为 CPU 不必要地保持忙碌，从而降低了系统的效率。 | 在此期间，由于中央处理器继续进行其他工作，因此不会浪费中央处理器周期，因此这种方法更有效。 |
| 在传输完成之前，中央处理器不能做任何工作，因为它必须留在循环中以持续监控外围设备。 | CPU 可以做任何其他工作，直到它被指示设备准备好进行数据传输的命令中断 |
| 它的模块被视为慢速模块。 | 它的模块比编程的输入输出模块更快。 |
| 它很容易编程和理解。 | 如果一个人使用低级语言，理解起来会很棘手和复杂。 |
| 系统的性能严重下降。 | 系统的性能得到了一定程度的提升。 |

</figure>