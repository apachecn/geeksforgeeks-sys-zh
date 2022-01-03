# 输入输出接口(中断和直接存储器存取模式)

> 原文:[https://www . geesforgeks . org/io-interface-interrupt-DMA-mode/](https://www.geeksforgeeks.org/io-interface-interrupt-dma-mode/)

用于在内部存储和外部输入/输出设备之间传输信息的方法称为输入/输出接口。连接到任何计算机系统的外围设备使用特殊的通信链路连接中央处理器。这些通信链路用于解决中央处理器和外围设备之间的差异。在中央处理器和外围设备之间存在特殊的硬件组件来监控和同步所有的输入和输出传输，称为接口单元。

## 转移方式:

从外部设备接收的二进制信息通常存储在存储单元中。从中央处理器传输到外部设备的信息来自存储单元。中央处理器只是处理信息，但源和目标始终是存储单元。中央处理器和输入/输出设备之间的数据传输可以在不同的模式下完成。

进出外围设备的数据传输可以通过三种可能的方式中的任何一种来完成

1.  编程输入输出
2.  中断启动的输入输出
3.  直接存储器存取。

现在让我们逐一讨论每种模式。

1.  **Programmed I/O:** It is due to the result of the I/O instructions that are written in the computer program. Each data item transfer is initiated by an instruction in the program. Usually the transfer is from a CPU register and memory. In this case it requires constant monitoring by the CPU of the peripheral devices.

    **编程输入/输出示例:**在这种情况下，输入/输出设备不能直接访问存储单元。从输入/输出设备到内存的传输需要中央处理器执行几条指令，包括将数据从设备传输到中央处理器的输入指令和将数据从中央处理器传输到内存的存储指令。在编程输入/输出中，中央处理器保持在程序循环中，直到输入/输出单元表明它准备好进行数据传输。这是一个耗时的过程，因为它不必要地使中央处理器保持忙碌。这种情况可以通过使用中断工具来避免。这将在下面讨论。

2.  **Interrupt- initiated I/O:** Since in the above case we saw the CPU is kept busy unnecessarily. This situation can very well be avoided by using an interrupt driven method for data transfer. By using interrupt facility and special commands to inform the interface to issue an interrupt request signal whenever data is available from any device. In the meantime the CPU can proceed for any other program execution. The interface meanwhile keeps monitoring the device. Whenever it is determined that the device is ready for data transfer it initiates an interrupt request signal to the computer. Upon detection of an external interrupt signal the CPU stops momentarily the task that it was already performing, branches to the service program to process the I/O transfer, and then return to the task it was originally performing.

    **注意:**编程 I/O 和中断驱动 I/O 这两种方法都需要
    处理器的主动干预才能在内存和 I/O 模块之间传输数据，任何数据传输都必须横穿
    一条通过处理器的路径。因此，这两种形式的输入/输出都有两个固有的缺点。

    *   输入/输出传输速率受处理器测试和服务
        设备的速度限制。
    *   处理器忙于管理输入/输出传输；每次输入输出传输必须执行若干指令
        。
3.  **Direct Memory Access**: The data transfer between a fast storage media such as magnetic disk and memory unit is limited by the speed of the CPU. Thus we can allow the peripherals directly communicate with each other using the memory buses, removing the intervention of the CPU. This type of data transfer technique is known as DMA or direct memory access. During DMA the CPU is idle and it has no control over the memory buses. The DMA controller takes over the buses to manage the transfer directly between the I/O devices and the memory unit.

    ![](img/7c683c087431c3aa0b6acc472e3a555f.png)

    **总线请求:**由 DMA 控制器使用，请求 CPU 放弃对总线的控制。

    **总线授权:**由中央处理器激活，通知外部 DMA 控制器总线处于高阻抗状态，请求 DMA 可以控制总线。一旦直接存储器存取控制了总线，它就传输数据。这种转移可以通过多种方式进行。

    **使用 DMA 控制器的 DMA 传输类型:**

    **突发传输:**
    DMA 完成数据传输后返回总线。寄存器用作字节计数，
    在每次字节传输时递减，当字节计数达到零时，DMAC 将
    释放总线。当 DMAC 在突发模式下运行时，中央处理器在数据
    传输期间暂停。
    涉及的步骤有:

    1.  总线授权请求时间。
    2.  以设备的传输速率传输整个数据块，因为设备通常比数据传输到中央处理器的速度慢。
    3.  将总线控制释放回中央处理器
        因此，传输 N 个字节
        所花费的总时间=总线授权请求时间+ (N) *(内存传输速率)+总线释放控制时间。

    ```
    Where,
    X µsec =data transfer time or preparation time (words/block)
    Y µsec =memory cycle time or cycle time or transfer time (words/block)
    % CPU idle (Blocked)=(Y/X+Y)*100
    % CPU Busy=(X/X+Y)*100
    ```

    **循环窃取:**
    一种替代方法，其中 DMA 控制器一次传输一个字，之后必须将总线的控制权返回给 CPU。中央处理器仅将其操作延迟一个内存周期，以允许直接内存输入/输出传输“窃取”一个内存周期。
    涉及的步骤有:

    1.  将字节缓冲到缓冲区中
    2.  通知中央处理器设备有 1 个字节要传输(即总线授权请求)
    3.  传输字节(以系统总线速度)
    4.  Release the control of the bus back to CPU.

        在继续传输下一字节数据之前，设备再次执行步骤 1，这样总线就不会被占用，并且
        传输不会依赖于设备的传输速率。
        因此，对于 1 字节的数据传输，使用周期窃取模式所花费的时间(T)。
        =总线授权所需时间+ 1 个总线周期传输数据+释放总线所需时间，将为
        N x T

    在周期窃取模式下，我们始终遵循流水线概念，即当一个字节被传输时，设备并行准备下一个字节。如果询问“CPU 时间与数据传输时间的比例”，则使用周期窃取模式。

    ```
    Where,
    X µsec =data transfer time or preparation time
    (words/block)
    Y µsec =memory cycle time or cycle time or transfer
    time (words/block)
    % CPU idle (Blocked) =(Y/X)*100
    % CPU busy=(X/Y)*100 

    ```

    **交错模式:**在这种技术中，当
    微处理器不使用时，DMA 控制器接管系统总线。交替半周期，即半周期 DMA +半周期处理器。

    **注意:**在门考中你可以直接将以上公式应用于不同模式的 DMA 传输。

    本文由**纳米塔·辛格**供稿。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。