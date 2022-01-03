# 虚拟局域网的类型(VLAN)

> 原文:[https://www.geeksforgeeks.org/types-of-virtual-lan-vlan/](https://www.geeksforgeeks.org/types-of-virtual-lan-vlan/)

[在](https://www.geeksforgeeks.org/virtual-lan-vlan/)[二层交换机](https://www.geeksforgeeks.org/switch-functions-at-layer-2/)上创建虚拟局域网(VLAN) ，减小广播域大小。它是通过将大型广播域分成较小的广播域来提高网络性能的技术之一。

根据其承载的网络类型，有 5 种主要类型的虚拟局域网:

1.  **默认 VLAN–**
    当交换机最初启动时，所有交换机端口都成为默认 VLAN 的成员(通常所有交换机都有名为 **VLAN 1** 的默认 VLAN)，这使得它们都是同一个广播域的一部分。使用默认 VLAN 允许连接到任何交换机端口的任何网络设备与其他交换机端口上的其他设备连接。默认 VLAN 的一个独特之处是它不能被重命名或删除。
2.  **数据 VLAN–**
    数据 VLAN 用于将整个网络分为 2 组。一组用户和另一组设备。这个 VLAN 也被称为用户 VLAN，数据 VLAN 只用于用户生成的数据。这个 VLAN 只携带数据。它不用于承载管理流量或语音。
3.  **VLAN 之声–**
    VLAN 之声配置为承载语音流量。语音虚拟局域网通常比其他类型的网络流量具有更高的传输优先级。为了确保网络电话(VoIP)的质量(整个网络的延迟小于 150 毫秒)，我们必须有单独的语音 VLAN，因为这将为其他应用程序保留带宽。
4.  **管理 VLAN–**
    管理 VLAN 被配置为访问交换机的管理功能(如系统日志记录、监控等流量)。默认情况下，VLAN 1 号是 VLAN 管理层(VLAN 1 号对 VLAN 管理层来说是个糟糕的选择)。如果管理员没有将唯一的 VLAN 配置为管理 VLAN，则 VLAN 的任何交换机都可以定义为管理 VLAN。这种 VLAN 确保了即使在用户流量很大时，管理带宽也是可用的。
5.  **本地 VLAN–**
    这个 VLAN 识别来自中继链路两端的流量。本地 VLAN 仅分配给 802.1Q 中继端口。802.1Q 中继端口将未标记的流量(不来自任何 VLAN 的流量)放在本地 VLAN。最好将本地 VLAN 配置为未使用的 VLAN。