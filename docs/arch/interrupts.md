# 中断

> 原文:[https://www.geeksforgeeks.org/interrupts/](https://www.geeksforgeeks.org/interrupts/)

[中断](https://www.geeksforgeeks.org/purpose-of-an-interrupt-in-computer-organization/)是进程或事件需要立即关注时，硬件或软件发出的信号。它会提醒处理器某个高优先级进程需要中断当前工作进程。在输入/输出设备中，一条总线控制线专用于此目的，称为*中断服务程序(ISR)* 。

当一个设备在比如说进程 I 上发出中断时，处理器首先完成指令 I 的执行，然后它用中断服务程序的第一条指令的地址加载程序计数器。在用地址加载程序计数器之前，被中断指令的地址被移到一个临时位置。因此，处理中断后，处理器可以继续处理 i+1。

当处理器处理中断时，它必须通知设备它的请求已被识别，以便它停止发送中断请求信号。此外，保存寄存器以便中断的进程可以在将来恢复，会增加从收到中断到 ISR 开始执行之间的延迟。这被称为中断延迟。

**硬件中断:**
在硬件中断中，所有设备都连接到中断请求线。一条请求线用于所有 n 个设备。要请求中断，设备会关闭其关联的开关。当一个设备请求中断时，INTR 值是来自各个设备的请求的逻辑或。

**处理内部评级时涉及的事件顺序:**

1.  设备会发出内部评级。
2.  处理器中断当前正在执行的程序。
3.  设备被告知其请求已被识别，并且设备去激活请求信号。
4.  执行请求的操作。
5.  中断被启用，中断的程序被恢复。

**处理多个设备:**
当多个设备发出中断请求信号时，需要额外的信息来决定首先考虑哪个设备。以下方法用于决定选择哪个设备:轮询、矢量中断和中断嵌套。这些解释如下。

1.  **轮询:**
    在轮询中，遇到的第一个设置了 IRQ 位的设备是首先要服务的设备。请适当的 ISR 为其提供服务。这很容易实现，但询问所有器件的 IRQ 位会浪费大量时间。

2.  **矢量中断:**
    在矢量中断中，请求中断的设备通过总线向处理器发送特殊代码来直接识别自己。这使处理器能够识别产生中断的设备。特殊代码可以是 ISR 的起始地址，也可以是 ISR 在内存中的位置，称为中断向量。

3.  **中断嵌套:**
    在这种方法中，I/O 设备以优先级结构组织。因此，来自较高优先级设备的中断请求被识别，而来自较低优先级设备的请求不被识别。为了实现这一点，每个进程/设备(甚至处理器)都必须这样做。处理器只接受优先级高于它的设备/进程的中断。

处理器优先级编码在进程状态寄存器的几个位中。它可以通过写入 PS 的程序指令来改变。处理器仅在执行操作系统例程时处于监督模式。它在执行应用程序之前切换到用户模式。