# 实时监控全表

> 原文:[https://www.geeksforgeeks.org/rtc-full-form/](https://www.geeksforgeeks.org/rtc-full-form/)

**RTC 代表远程时钟**。它是一种基于计算机的时钟，由集成电路形成，用于记录时间。这些时钟不同于硬件时钟，因为硬件时钟不以人为单位使用时间。如今，几乎每个电子设备都使用实时时钟来跟上精确的时间。

1984 年， **IBM** 推出 PC 兼容的 RTC，采用摩托罗拉的 MC146818 RTC。后来，**达拉斯半导体**开始大规模生产兼容旧个人电脑的 RTC。一些微控制器有内置的实时时钟，而较新的系统将它们与南桥芯片集成在一起。

**RTC 的特性:**

*   **低功耗–**
    RTC 的一个重要特性就是功耗。尽管主系统断电，但 RTC 仍能正常工作。相对于微处理器设置的绝对参考时间，RTC 能够保持它们。
*   **常用–**
    许多电子设备使用 RTC 来保持精确的时间。它们很容易与汽车应用等其他设备集成。
*   **无时钟信号–**
    RTC 不依赖硬件时钟的时钟信号，因为它使用晶体振荡器。因此，RTC 显示时间准确无误。
*   **报警功能–**
    RTCs 也可以具有针对特定任务触发的报警功能。
*   **切换–**
    当系统工作正常时，RTC 从数字电路中获取电能。但是在断电的情况下，它们会切换到连续电源。
*   **寿命–**
    RTC 的电池至少可以使用三年或更长时间。因此，RTC 的寿命比其他器件更长。

**优势:**

*   实时时钟确保系统内发生的进程同步，因为系统时钟间接依赖于它。
*   它不会让任何时间关键任务(任何受时间限制的关键任务)影响主系统的功能。
*   它比其他程序和设备更准确有效地维护时间。
*   与其他器件相比，RTC 功耗更低，因此效率更高。四

**劣势:**

*   RTC 需要持续的电源来维持自身的运行。