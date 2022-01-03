# SNMP 完整格式

> 原文:[https://www.geeksforgeeks.org/snmp-full-form/](https://www.geeksforgeeks.org/snmp-full-form/)

[简单网络管理协议(SNMP)](https://www.geeksforgeeks.org/simple-network-management-protocol-snmp/) 主要被管理员用来监控网络设备。实施此协议将减少登录每个设备和验证所有日志的工作量，并通过向管理员通知基于配置的任何可疑日志/活动来确保网络始终可靠，并被广泛接受。

SNMP 是一种应用层协议，使用 [UDP](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) 端口号 161/162，由 RFC1157 中的互联网架构板(IAB)定义，用于交换管理信息。多年来，协议有了重大改进，有三个主要版本，即 SNMPv1、SNMPv2 & SNMPv3。

1.  **SNMPv1–**
    在 RFC 1028 中定义，相对容易使用，因为它提供了数据轮询的基本功能。它的主要限制是安全性和 32 位计数器体系结构。它甚至在局域网中使用了 30 年后的今天。
2.  **snmpv 2–**
    在 RFC 1901，1441 中定义，支持 64 位计数器架构并改进了错误处理，但数据未加密，这使得安全性受到限制。

*   **SNMPv3 –**
    Defined in RFC 3410, adds security to the already existing advantages of SNMPv2\. It being the latest and currently mostly widely used.

    **特征:**

    *   SNMP 用于监控网络
    *   它检测任何网络故障
    *   也可用于配置远程设备。
    *   允许以标准化的方式从网络行业的各个制造商收集各种设备的信息。

    **优势:**

    *   通过从所有设备收集数据，减轻管理员的任务，并允许在需要时进行控制。
    *   当问题出现时，陷阱将有助于隔离问题。
    *   通过各种平台向管理员发送足够的通知，及时通知问题。
    *   从收集的日志中进行分析有助于获得更多的见解(甚至支持可视化解释)并相应地进行规划。
    *   灵活的网络自动发现和模板有助于减少繁琐的配置。
    *   可以监控任何符合行业标准的网络设备。
    *   有开源 SNMP 服务器可用，这使得它更容易和经济高效。
    *   SNMP 是通用的，因为它通常被理解并使用标准化的结构。

    **缺点:**

    *   配置困难、繁琐且耗时。
    *   SNMP 工作在间隔轮询机制上，间隔之间发生的事件可能会被遗漏。例如，在轮询间隔期间关闭和恢复的接口不会通知管理员。
    *   定期轮询大量数据，这需要更强的处理能力。
    *   使用 UDP 进行任何通信，这增加了数据包从网络设备传输到监控工具的必要性。