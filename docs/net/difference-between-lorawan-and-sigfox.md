# 罗拉万和西格福克斯的区别

> 原文:[https://www . geesforgeks . org/区别-lora wan-和-sigfox/](https://www.geeksforgeeks.org/difference-between-lorawan-and-sigfox/)

先决条件–[物联网中的数据链路层通信协议](https://www.geeksforgeeks.org/data-link-layer-communication-protocols-in-iot/)

[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)使用不同的网络协议为网络层提供服务。在物联网中，为了建立设备之间的通信，我们需要通信协议。在网络协议中，LPWAN 是应用最广泛的标准通信协议之一。

**低功耗广域网(LPWAN) :**
LPWAN 也叫低功耗广域网。这是一个无线广域网，范围从 2 公里到 1000 公里不等。 **SigFox** 、 **LoRaWAN** 都是 LPWAN 技术的例子。LoRaWAN 和 SigFox 都实现了长距离、低功耗的无线数据集成。然而，LoRaWAN 和 SigFox 是不同的技术。

**1。**
SigFox 使用双向功能，即 DBPSK 在一个方向，GFSK 在另一个方向。其中 DBPSK 代表差分二进制相移键控，GFSK 代表高斯频移键控，SigFox 和他们的合作伙伴在塔上设置接收器，从不同设备的不同节点接收数据传输。

**2。LoRaWAN :**
LoRaWAN 是一种 **MAC 层协议，**是为大规模公共网络设计的。LoRaWAN 是使用 Semtech 的 LoRa 技术构建的。但重要的是，LoRa 和 LoRaWAN 是两回事。LoRa 和 LoraWAN 属于非蜂窝 LPWAN 无线通信网络协议。

**罗拉万和西格福克斯的区别:**

<center>

| **序列号** | **对比** |  | **罗拉湾** |
| 01 | 调节；调整 | 它遵循二进制相移键控调制。 | 劳拉万遵循啁啾扩频调制。 |
| 02 | 带宽 | 在 SigFox 中，带宽是 100 赫兹。 | 对于罗兰，带宽为 250 千赫和 125 千赫。 |
| 03 | 最大数据速率 | 它可以发送高达 100bps 的数据。 | 在 LoRaWAN 的情况下，最大数据速率为 50Kbps。 |
| 04 | 功能 | 信号福克斯有限双向/半双工 | 罗兰是全双向/半双工的 |
| 05 | 每天最大消息数 | 在 SigFox 中，上行链路=140，下行链路=4。 | 在劳拉湾，这个设施是无限的。 |
| 06 | 最大有效负载长度 | 上行=12 字节，
下行=8 字节。 | 最大有效负载长度为 243 字节。 |
| 07 | 范围 | SigFox 的范围是城市 10 公里，农村 40 公里。 | 劳拉湾的范围分别是城市 5 公里，农村 20 公里。 |
| 08 | 界面免疫 | SigFox 网络架构中的接口抗扰度非常高。 | 接口抗扰度与 SigFox 网络架构相同。 |
| 09 | 身份验证和加密 | 它不支持现代加密技术。 | 它支持(AES 128b)作为加密技术。 |
| Ten | 拓扑学 | 它遵循星型拓扑。 | 劳拉万遵循星对星拓扑。 |

</center>