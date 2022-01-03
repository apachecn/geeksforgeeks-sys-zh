# Wifi 保护接入(WPA)

> 原文:[https://www.geeksforgeeks.org/wifi-protected-access-wpa/](https://www.geeksforgeeks.org/wifi-protected-access-wpa/)

两个安全协议和安全认证程序分别是*保护无线电脑网络安全系统(WPA)* 和*保护无线电脑网络安全系统 II (WPA2)* 。这些是由无线联盟开发的，用于保护无线计算机网络。该联盟定义了这些协议，因为研究人员在以前的系统有线等效隐私(WEP)中发现了严重的弱点。

也被称为 IEEE 802.11i 标准草案的 WPA 于 2003 年问世。Wi-Fi 联盟将其作为一项中间措施，以应对更安全、更复杂的 WPA2 系统的出现，该系统于 2004 年推出，是 IEEE 802.11i(或 IEEE 802.11i-2004)标准的通用简写。

2018 年 1 月，随着针对 WPA2 Wi-Fi 联盟的多项安全改进，宣布发布 *WPA3* 。

1.  **WPA –** 
    The WPA is an intermediate measure to take the place of WEP. WPA could be implemented through firmware upgrades on wireless network interface cards that were designed for WEP in 1999\. However, since more changes were required in the wireless access points (APs) than those needed on the network cards, most pre-2003 APs could not be upgraded to support WPA. 

    WPA 协议几乎实现了所有的 IEEE 802.11i 标准。时间密钥完整性协议(TKIP)被用于 WPA。WEP 使用的是 64 位或 128 位加密密钥，必须在无线接入点和设备上手动输入，一旦输入就永远无法更改。TKIP 采用每包密钥，这意味着它为每个包动态生成一个新的 128 位密钥，从而防止危及 WEP 的攻击类型。

    WPA 包括消息完整性检查，旨在防止攻击者更改或重新发送数据包。这取代了 WEP 标准使用的循环冗余校验(CRC)。CRC 的一个主要缺陷是，它没有为它处理的数据包提供足够强的数据完整性保证。经过良好测试的消息认证码可以解决这些问题，但是它们需要太多的计算才能在旧的网卡上使用。WPA 使用一种称为 TKIP 的消息完整性检查算法来验证数据包的完整性。TKIP 比 CRC 强得多，但 WPA2 使用的算法更强。研究人员发现了 WPA 中的一个缺陷，类似于 WEP 中的旧缺陷和消息完整性代码哈希函数(名为迈克尔)的局限性，该函数用于从短数据包中检索密钥流，以用于重新注入和欺骗。

2.  **WPA2–**
    WPA2 取代 WPA。需要 Wi-Fi 联盟进行测试和认证的 WPA2 实施了 IEEE 802.11i 的强制元素。特别是，它包括对基于 AES(高级加密标准)的加密模式 CCMP(计数器模式 CBC-MAC 协议)的强制支持。认证始于 2004 年 9 月。从 2006 年 3 月 13 日起，所有新设备都必须获得 WPA2 认证，才能使用无线网络商标。