# 流量控制和误差控制的区别

> 原文:[https://www . geesforgeks . org/流量控制和错误控制的区别/](https://www.geeksforgeeks.org/difference-between-flow-control-and-error-control/)

**1。** [**流量控制**](https://www.geeksforgeeks.org/flow-control-in-data-link-layer/) **:**
它是[数据链路层](https://www.geeksforgeeks.org/data-link-layer-in-osi-model/)的一个重要功能。它指的是在等待接收方确认之前，告知发送方可以传输多少数据的一套程序。

**流量控制的目的:**
任何接收设备处理输入数据的速度都是有限的，存储输入数据的内存也是有限的。如果数据源发送数据的速度快于接收器的容量，接收器就有可能被淹没。接收器会不断丢失一些帧，只是因为它们到达得太快，缓冲区也被填满了。

这将在网络上产生废帧。因此，接收设备必须有某种机制来通知发送方发送更少的帧或暂时停止传输。通过这种方式，流量控制将把帧传输速率控制到接收机可以处理的值。

**示例–**[停止&等待协议](https://www.geeksforgeeks.org/stop-and-wait-protocol-its-problems-and-solutions/)

**2。** [**【差错控制】**](https://www.geeksforgeeks.org/error-control-in-data-link-layer/) **:**
数据链路层的差错控制功能检测传输帧中的差错，并重新传输所有的差错帧。

**差错控制的目的:**
数据链路层差错控制功能的功能有助于处理传输中损坏的数据帧、传输中丢失的数据帧以及传输中丢失的确认帧。用于错误控制的方法称为自动重复请求，用于噪声信道。

**示例–**[停止&等待 ARQ](https://www.geeksforgeeks.org/stop-and-wait-arq/) 和[滑动窗口 ARQ](https://www.geeksforgeeks.org/sliding-window-protocol-set-1/)

**流量控制和误差控制的区别:**

<figure class="table">

| 没有 | 流控制 | 错误控制 |
| --- | --- | --- |
| 1. | 流量控制仅指从发送方到接收方的数据传输。 | 差错控制是指将无差错数据从发送方传输到接收方。 |
| 2. | 对于流量控制，有两种方法:基于反馈的流量控制和基于速率的流量控制。 | 检测数据错误的方法有:[校验和](https://www.geeksforgeeks.org/error-detection-in-computer-networks/)、[循环冗余校验](https://www.geeksforgeeks.org/modulo-2-binary-division/)和[奇偶校验](https://www.geeksforgeeks.org/vertical-redundancy-check-vrc-or-parity- check/)。
纠正数据错误的方法有:[汉明码](https://www.geeksforgeeks.org/hamming-code-in-computer-network/)、二进制卷积码、里德-所罗门码、低密度奇偶校验码。 |
| 3. | 它防止数据丢失，并避免接收缓冲区的过度运行。 | 它用于检测和纠正代码中出现的错误。 |
| 4. | 流量控制技术的例子有:停止和等待协议和滑动窗口协议。 | 错误控制技术的例子有:停止和等待 ARQ 和滑动窗口 ARQ。 |

</figure>