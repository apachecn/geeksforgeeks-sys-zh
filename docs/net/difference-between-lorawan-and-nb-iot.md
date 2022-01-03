# 劳拉湾和 NB-IoT 的区别

> 原文:[https://www . geeksforgeeks . org/区别-lora wan-和-nb-iot/](https://www.geeksforgeeks.org/difference-between-lorawan-and-nb-iot/)

先决条件–[物联网中的数据链路层协议](https://www.geeksforgeeks.org/data-link-layer-communication-protocols-in-iot/)

**1。劳拉万:**
劳拉万是 MAC 层协议下的，是为大规模公共区域网络而做的。LoRaWAN 是使用 Semtech 的 LoRa 技术创建的。LoRa 和 LoraWAN 属于非蜂窝无线通信网络协议。它遵循啁啾扩频调制(CSS 调制)。

**2。NB-IoT :**
NB-IoT 又称窄带 IoT，是公认的物联网无线通信。NB-IoT 属于 LPWAN(低功耗广域网)类别，能够连接需要少量数据、低带宽和长电池寿命的设备。

NB-IoT 是一种用于物联网设备和应用的窄带无线电技术，分别需要低成本的长距离无线连接和长电池寿命的低功耗。

**劳拉万和 NB-IoT 的区别:**

<center>

| 比较 | 洛拉万 | nb-物联网 |
| 调节；调整 | LORAWAN 使用线性调频扩频调制。 | NB-IoT 采用正交相移键控调制。 |
| 频率 | 它在欧洲使用 868 兆赫兹，在北美使用 915 兆赫兹，在亚洲使用 433 兆赫兹(未经许可的 ISM 频段)。 | 它使用许可的长期演进频段。 |
| 带宽 | 劳拉万有 250 千赫和 125 千赫的带宽。 | NB-IoT 的带宽为 200KHz。 |
| 最大消息数/天 | 它每天可以发送的最大消息数是无限的。 | 在这项技术中，最大消息/天也是无限的。 |
| 最大数据速率 | 在 LoRaWAN 的情况下，最大数据速率为 50Kbps。 | 在 NB-IoT 的情况下，最大数据速率为 200Kbps。 |
| 最大有效负载长度 | 在 LORAWAN 中，最大有效载荷长度为 243 字节。 | 在 NB-IoT 中，最大有效负载长度为 1600 字节。 |
| 范围 | 劳拉湾的范围是城市 5 公里，农村 20 公里。 | NB-IoT 的范围是城市 1 公里，农村 10 公里。 |
| 抗干扰性 | 在劳拉万的情况下，抗干扰性非常高。 | NB-Iot 情况下的抗干扰性低。 |
| 身份验证和加密 | 它支持 AES 128b 作为加密技术。 | 它支持 LTE 加密技术。 |
| 自适应数据速率 | 劳拉万支持自适应数据速率。 | 它不支持自适应数据速率。 |

</center>