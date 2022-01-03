# 计算机组织中的微处理器通信

> 原文:[https://www . geesforgeks . org/MPU-计算机中的通信-组织/](https://www.geeksforgeeks.org/mpu-communication-in-computer-organization/)

**MPU 借助一些被称为输入输出设备的外部设备与外界进行通信**。微处理器接受来自键盘和模拟/数字转换器等输入设备的二进制数据，并将数据发送到打印机和发光二极管等输出设备。为了执行这个任务，微处理器首先需要识别输入/输出设备。

有两种不同的方法可以识别输入/输出设备:使用 8 位地址和使用 16 位地址。这些方法将在以下章节中简要介绍:

1.  **I/Os with 8-bit addresses –**
    This is also known as **peripheral-mapped I/O or I/O-mapped-I/O**. In this type of I/O, MPU uses eight address lines to identify an input or an output devices. This is an 8-bit numbering system for I/Os used in conjunction with the input and output instructions. This is also known as I/O space that is separate from the memory space which is 16-bit numbering system. The eight address lines have 2^8 combinations which is total 256 addresses; therefore MPU can identify 256 input devices and 256 output devices with addresses ranging from 00H to FFH.

    通过使用控制线输入/输出读取和输入/输出写入，可以区分输入和输出设备。微处理器使用输入设备的输入输出读控制信号和输出设备的输入输出写控制信号。输入/输出映射的单个地址被称为输入/输出端口号。这些输入/输出设备不能直接连接到数据总线或地址总线；所有连接必须通过三态接口设备进行，因此只有当微处理器选择与它们通信时，它们才会被启用并连接到总线。

2.  **16 位地址的输入/输出–**
    这也被称为**内存映射输入/输出**。在这种类型的输入输出中，微处理器使用十六条地址线来识别一个输入或一个输出设备；一个输入/输出被连接，就好像它是一个内存寄存器。微处理器使用与存储器相同的控制信号(存储器读取和存储器写入)和指令。在一些微处理器中，如摩托罗拉 6800，所有的输入/输出都有 16 位地址；I/o 和内存共享相同的内存映射(64K)。对于 8 位和 16 位地址，与输入/输出设备通信的步骤是相似的。这些步骤总结如下:
    1.  微处理器在地址总线上放置一个 8 位地址(或 16 位地址)，由外部解码逻辑解码。
    2.  微处理器发送控制信号(输入/输出读取或输入/输出写入)并启用输入/输出设备。
    3.  数据通过数据总线传输。