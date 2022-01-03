# 无线通信|第三集

> 原文:[https://www.geeksforgeeks.org/wireless-communication-set-3/](https://www.geeksforgeeks.org/wireless-communication-set-3/)

先决条件–[无线通信|第二集](https://www.geeksforgeeks.org/wireless-communication-set-2/)
前面我们讲了各种[认证](https://www.geeksforgeeks.org/difference-between-authentication-and-authorization/)的方法。现在我们讨论了无线安全的另一个方面，完整性。完整性意味着通过无线网络或互联网发送的消息的正确性。为无线网络定义的原始 802.11 标准只有保护网络上数据发送的 WEP 方法。

**完整性方法的类型:**
有三种完整性方法:时间密钥完整性协议(TKIP)、计数器 CBC-MAC 协议(CCMP)和伽罗瓦计数器模式协议(GCMP)。这些解释如下。

**1。用于无线通信安全认证的临时密钥完整性协议(TKIP)–**
WEP 后来被认为是易受攻击的。TKIP 是在发现 WEP 易受攻击后提出的。它是由 WiFi 联盟在 2002 年设计的，密钥大小为 128 位。它使用 RC4 密码算法加密每一帧。
它在底层 WEP 加密之下增加了以下安全特性。

1.  时间戳
2.  TKIP 序列计数器
3.  发送者的媒体访问控制地址
4.  消息完整性检查
5.  按键混合算法

一段时间以来，TKIP 一直被用作完整性方法，直到发现一些攻击者攻击它。实际上，在 2012 年 802.11 标准修订后，命名为 802.11-2012，不再推荐 TKIP。

**2。对抗 CBC-MAC 协议(CCMP)–**
开发了一种比 TKIP 更安全的完整性方法，称为对抗 CBC-MAC 协议。
它由两个算法组成–

1.  AES 计数器模式加密。
2.  用于消息完整性检查的密码块链接消息认证码。

[高级加密标准(AES)](https://www.geeksforgeeks.org/difference-between-aes-and-des-ciphers/) 是迄今为止最强的加密算法。它被世界各地的安全专家广泛使用，因为它是开放的和公众可访问的。实施 CCMP 协议的唯一困难是，客户端和应用程序都必须有支持硬件。CCMP 用于 WiFi 安全中使用的 WPA2 标准。

**3。伽罗瓦计数器模式协议(GCMP)–**
伽罗瓦计数器模式协议缩写为 GCMP 是最安全的认证加密方式，比 CCMP 更安全高效。
GCMP 由两个算法组成–

*   像 CCMP 一样的 AES 计数器模式加密。
*   伽罗瓦消息认证码，检查消息的完整性。

WiFi 安全中使用的 WPA3 标准中使用了 GCMP。