# 保护无线和移动设备

> 原文:[https://www . geeksforgeeks . org/securing-wireless-and-mobile-devices/](https://www.geeksforgeeks.org/securing-wireless-and-mobile-devices/)

设备加固是减少漏洞和帮助保护网络安全的工具和技术的集合。其中一些方法涉及相互认证、WEP 和 WPA/WPA2。

*   **Mutual Authentication:**
    One of the remarkable vulnerabilities of wireless networks is the utilization of rogue access points. An access point is a device that enables wireless devices to connect to a network. Any device that has a wireless transmitter and hardwired interface to a network can go about as a rouge access point. The rogue access point can impersonate an authorized access point. The outcome is that wireless devices establish communication with the rogue access point rather than the authorized access point.

    骗子可以接收连接请求，复制请求中的数据，并将数据转发给授权的网络接入点。为了防止恶意接入点，使用了相互身份验证。在相互认证中，通信链路中的两个实体相互认证。客户端向接入点进行验证，接入点对客户端进行身份验证。它也称为双向身份验证。

*   **Wired Equivalent Privacy (WEP):**
    Wired Equivalent Privacy (WEP) is one of the first and widely used Wi-Fi security guidelines. WEP became a security standard in September 1999\. It provides authentication and encryption protections. The WEP standards are out of date however numerous devices still support WEP.

    不管对标准和扩展密钥大小的修正，WEP 都经历了各种安全缺陷。网络罪犯可以轻松快速地破解 WEP 密码。

*   **Wi-Fi Protected Access (WPA/WPA2)**
    The most widely recognized WPA configuration is WPA-PSK (Pre-Shared Key). The keys used by WPA are 256-bit. WPA provides message integrity checks which could detect if an attacker had captured and changed information gone between the wireless access point and client. Another key security improvement as Temporal Key Integrity Protocol (TKIP).

    TKIP 标准提供了保护和更改加密密钥的能力。从 WPA 到 WPA2，最值得注意的安全改进之一是强制使用高级加密标准算法。

**有趣的事实:**

*   WPA2 是最快的加密协议。
*   WPA2 密码最长可达 63 个字符。