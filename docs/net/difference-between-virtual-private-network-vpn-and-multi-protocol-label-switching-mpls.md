# 虚拟专用网络(VPN)和多协议标签交换(MPLS)的区别

> 原文:[https://www . geeksforgeeks . org/区别-虚拟专用网-VPN-和-多协议-标签交换-mpls/](https://www.geeksforgeeks.org/difference-between-virtual-private-network-vpn-and-multi-protocol-label-switching-mpls/)

**[虚拟专用网络(VPN)](https://www.geeksforgeeks.org/virtual-private-network-vpn-introduction/) :**
VPN 是针对虚拟专用网络的，是一种虽是专用网络但却是虚拟的网络类型。通过应用虚拟专用网络，我们可以将公共网络用作专用网络，因为虚拟专用网络是处理加密、完整性保护和认证或认证的工具。它模拟公共网络上的专用网络。这允许用户远程访问专用网络。与多协议标签交换不同，在虚拟专用网中，路由划分和流量由客户处理。在虚拟专用网中，需要所有现场视察层才能使虚拟专用网正常运行。

**多协议标签交换(MPLS):**
MPLS 是用于多协议标签交换的，是一个至关重要的数据承载系统。它的功能很像分组交换网络和电路交换网络，它在分组交换网络中模拟电路交换网络的一些特征。在多协议标签交换系统中，标签交换方法被用来给每个数据包分配一个号码或标签。每个数据包上的标签或编号在数据包转发过程中起着重要的作用。MPLS 在 [OSI(开放系统互连)模型](https://www.geeksforgeeks.org/layers-of-osi-model/)的第 2 层和第 3 层运行。多协议标签交换是一种更高可靠性的技术，因为它保证了服务质量。

虚拟专用网络和多协议标签交换的区别:

| S.NO | （同 Minneapolis）明尼阿波利斯（美国城市） | 虚拟专用网络 |
| --- | --- | --- |
| 1. | MPLS 支持多点技术。 | 而虚拟专用网也支持多点技术和点对点技术。 |
| 2. | 与 VPN 相比，MPLS 技术的成本更高。 | 而虚拟专用网的成本相对较低。 |
| 3. | MPLS 不操作加密。 | 而 VPN 利用加密。 |
| 4. | MPLS 在 OSI 第 2 层和第 3 层上运行。 | 而在这里，所有现场视察层都是使虚拟专用网发挥作用所必需的。 |
| 5. | 多协议标签交换(MPLS)是一种高可靠性的技术，因为它保证了服务质量。 | 而虚拟专用网也是延迟敏感流量的可靠技术。 |
| 6. | 在 MPLS 中，路由划分和流量由服务提供商处理。 | 在虚拟专用网中，客户处理路由划分和流量。 |
| 7. | 在 MPLS 中，基于云的服务是有限的。 | 而在虚拟专用网中，基于云的服务范围很广。 |
| 8. | 在 MPLS 中，每个被阻塞的站点都可以被解除阻塞。 | 而在 VPN 中，并不是每一个被封锁的站点都可以被解除封锁。 |