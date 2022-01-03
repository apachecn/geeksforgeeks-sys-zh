# NTP 和 PTP 的区别

> 原文:[https://www . geesforgeks . org/NTP 和-ptp 之间的差异/](https://www.geeksforgeeks.org/difference-between-ntp-and-ptp/)

**1。** [**【网络时间协议(NTP)**](https://www.geeksforgeeks.org/network-time-protocol-ntp/) **:**
它是一种促进系统中计算机时钟时间同步的协议。该协议是一种应用协议，适用于 [TCP/IP](https://www.geeksforgeeks.org/tcp-ip-model/) 网络上的主机同步。1981 年，特拉华大学的大卫·米尔斯解释了 NTP。这在通信机制中是需要的，以便在机器之间开始无缝连接。

**NTP 的特点:**
NTP 的一些特点是–

*   NTP 服务器有高精度原子钟和 GPU 时钟的入口。
*   它利用协调世界时来同步中央处理器时钟时间

**2。** [**【精确时间协议(PTP)**](https://www.geeksforgeeks.org/precision-time-protocol-ptp/) **:**
它是一种在整个计算机网络中促进时钟同步的协议。该协议用于同步不同类型设备的时钟。PTP 在 1588 年由约翰·爱迪生领导标准化，并于 2002 年出版。这是在同步介质中通过通信介质实现消息交换所必需的。

**PTP 的特色:**
PTP 的一些特色是–

*   它使用一个大师时钟来同步通信。
*   它适用于主从架构。

**NTP 和 PTP 的区别:**

<figure class="table">

| 

南不

 | 

标准温度和压力

 | 

PTP

 |
| --- | --- | --- |
| 1. | 它是网络时间协议的简称。 | 它是精确时间协议的简称。 |
| 2. | NTP 提供毫秒级精度。 | PTP 提供亚微秒精度。 |
| 3. | 通过硬件实现，可以达到亚微秒级的精度。 | 使用更好的振荡器可以达到纳秒级的精度。 |
| 4. | 它设计用于公共网络和广域网([广域网](https://www.geeksforgeeks.org/types-of-area-networks-lan-man-and-wan/))。 | 它的设计版本包括局域网的版本 1 和广域网的版本 2。 |
| 5. | NTP 客户端可以轮询各种 NTP 服务器。 | 在组播模式下，单个特级大师将时间“推”给一个或多个从机。 |
| 6. | 它通过哈希代码和改进的时钟选择提供安全性。 | 它通过加密安全机制提供安全性。 |
| 7. | 用途:用于工业自动化、家庭网络、电信、军事等。 | 应用:用于信息技术应用、通用时间戳应用、计算机同步等。 |

</figure>