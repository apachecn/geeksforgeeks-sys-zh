# RTS/CTS 和 DTR/DSR 流量控制的区别

> 原文:[https://www . geesforgeks . org/difference-RTS-cts-and-DTR-DSR-flow-control/](https://www.geeksforgeeks.org/difference-between-rts-cts-and-dtr-dsr-flow-control/)

**1。请求发送/清除发送:**
RTS/CTS 顾名思义，是一种流量机制，数据终端设备(DTE)即主机资产或向数据通信设备(DCE)发送 RTS。这样做只是为了表明主机已准备好发送数据，调制解调器可以启动或形成通信信道。然后，DCE 进一步声明或发送 CTS 以授予许可，即是的，您可以发送数据。RTS 只是表示主机想要发送一些数据，而 CTS 只是表示是的，您可以开始发送数据。这里，主机可以是计算机或任何其他设备，DCE 可以是调制解调器。

**2。数据终端就绪/数据集就绪:**
DTR/DSR 顾名思义，是一种流机制，其中 DTE 即主机断言或发送 DTR 到 DCE 即调制解调器，只是为了表明主机已准备好通信，调制解调器可以启动或创建通信信道。然后，DCE 进一步通知 DSR，简单地表明接收方已准备好通信。

**RTS/CTS 与 DTR/DSR 的区别:**

<center>

| RTS/CTS | DTR/DSR |
| --- | --- |
| 在使用 RTS/CTS 时，有大量的硬件缓冲。 | 使用 DTR/DSR 流量控制时，没有缓冲。 |
| 它用于不同的领域，如学术，自动售货机，工业等。 | 它用于不同的领域，如 POS(销售点)、打印机、EPOS(电子销售点)等。 |
| 它还可以用于控制主机和设备之间的数据流。 | 它还可以用于控制数据流、握手以及供电。 |
| RTS 只是表示它想向正在连接的设备发送数据。 | DTR 只是表示正在连接的设备准备接收数据。 |
| RTS 只启动和停止通信。 | DTR 还表示，目前有一些设备。 |
| RTS/CTS 线路不受固件驱动。相反，它们由硬件控制和驱动。 | DTR/DSR 线路通常由适配器中的固件驱动。 |

</center>