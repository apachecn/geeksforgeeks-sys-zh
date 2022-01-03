# 自适应安全设备(ASA)功能

> 原文:[https://www . geesforgeks . org/adaptive-security-appliance-asa-features/](https://www.geeksforgeeks.org/adaptive-security-appliance-asa-features/)

防火墙是一种网络安全系统，它根据基于 IP 地址、端口号定义的规则对输入或输出的数据包采取行动。思科称其防火墙为自适应安全设备。

思科 ASA 5500 系列有型号:
思科 ASA 5505、思科 ASA 5510、思科 ASA 5515-X、思科 ASA 5520、思科 ASA 5525-X、思科 ASA 5540、思科 ASA 5550、思科 ASA 5555-X、思科 ASA 5585-X。

**自适应安全设备(ASA)–**
ASA 是一款思科安全设备，可以通过 VPN 功能、防病毒和许多其他功能来执行基本的防火墙功能。ASA 的一些特性包括:

1.  **Packet filtering –** 
    Packet filtering is a simple process of filtering the incoming or outgoing packet on the basis of rules defined on the ACL which has been applied to the device. It consists of various permit or denies conditions. If the traffic matches one of the rules, no other rule is matched and the matched rule is executed. 
2.  **Stateful filtering –** 
    By default, ASA performs stateful tracking of the packet if the packet is generated from a higher security level to a lower security level. 

    默认情况下，如果流量是由安全级别较高的设备为安全级别较低的设备(作为目的地)发起的，则允许使用 TCP 和 UDP 回复流量，并且可以远程登录安全级别较低的其他设备。这是因为状态数据库是在默认情况下启用状态检测的情况下维护的(其中维护了关于源和目标设备信息的条目，如 IP 地址、端口号)。

3.  **Routing support –** 
    ASA can perform static routing, Default routing also dynamic routing protocols like EIGRP, OSPF, and RIP. 
4.  **透明防火墙–**
    ASA 可以两种模式运行:
    *   *路由模式*:在这种模式下，ASA 就像一个第三层设备(路由器跳)，需要在其接口上有两个不同的 IP 地址(意味着两个不同的子网)。
    *   *透明模式*:在这种模式下，ASA 工作在第 2 层，由于接口(内部和外部)都充当网桥，因此只需要一个 IP 地址来管理 ASA 的管理目的。
5.  **AAA support –** 
    ASA supports AAA services either using its local database or using an external server like ACS (Access Control Server). 
6.  **VPN support –** 
    ASA supports policy-based VPNs like point-to-point IPsec VPN(site-to-site VPN and remote-access VPN) and SSL-based VPNs. 
7.  **Supports IPv6 –** 
    ASA (new versions) supports IPv6 routing such as static, dynamic. 
8.  **VPN load Balancing –** 
    It is a Cisco proprietary feature of Cisco ASA. Multiple clients can be shared across multiple ASA units at the same time. 
9.  **Stateful failover –** 
    ASA supports the high availability of pair of Cisco ASA devices. If one of the ASA goes down, the other ASA device will perform the operations without any interruption. When stateful failover is enabled, the active unit continuously passes connection state information to the backup device. After the failover occurs, the same connection information is available on the new active unit. 
10.  **Clustering –** 
    Cisco ASA lets us configure multiple ASA devices as a single logical device. cluster can consist of a maximum of 8 cohesive units. This results in high throughput and at the same time provides redundancy. 
11.  **Advance Malware Protection (AMP) –** 
    Cisco ASA provides support for Next-Generation firewall features which can provide protection advanced malware protection in a single device as the classic firewall features are combined with NGFWs features. 
12.  **模块化策略框架(MPF)–**
    MPF 用于定义不同流量的策略。它在 ASA 中用于利用高级防火墙功能，如 QOS、监管、优先级等。
    在使用 MPF 时，我们定义了用于识别流量类型的类别图、用于识别应采取何种措施(如优先级)的策略图以及用于应用该策略的服务策略。