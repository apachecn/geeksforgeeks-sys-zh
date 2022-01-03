# BISYNC 和 HDLC 特性的区别

> 原文:[https://www . geesforgeks . org/bisync 和-hdlc 之间的差异-功能/](https://www.geeksforgeeks.org/difference-between-bisync-and-hdlc-features/)

**BISYNC:**
BISYNC 代表二进制同步通信。它是一种半双工链路协议，取代了代表同步发射-接收的 SRT。

**HDLC:**
HDLC 代表高级数据链路控制。它在现场视察参考模型的数据链路层工作。它支持面向连接和无连接服务。

**HDLC 和 BISYNC 的特点:**

<center>

| 双同步功能 | HDLC 特色 |
| --- | --- |
| 它支持串行传输。 | 它还支持串行传输。 |
| BISYNC 的通信方式是同步的。 | HDLC 的通信方式有同步和异步两种。 |
| 它使用 TWA 定向模式。 | 它使用环球航空和 TWS 定向模式。 |
| 它支持点对点和点对多点配置。 | 它还支持点对点和点对多点配置。 |

</center>

它遵循停止和等待流量控制协议。它遵循滑动窗口流量控制协议。对于内容错误，它使用 CRC 循环冗余校验方法。对于内容错误，它使用循环冗余校验方法。它在成帧中使用 SYN SYN 帧标识符。它在成帧中使用标志帧标识符。帧中的 EBT/ETX 帧分隔符。在框架中标记框架分隔符。成帧中的多字节信息字段。成帧中的多位信息字段。对于框架透明度，它遵循 DLE 填充。For Framing transparency it follows ZERO stuffing.