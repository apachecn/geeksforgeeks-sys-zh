# 计算机网络中的以太网通道

> 原文:[https://www . geesforgeks . org/ether channel-in-computer-network/](https://www.geeksforgeeks.org/etherchannel-in-computer-network/)

以太信道是一种端口链路聚合技术，其中多个物理端口链路被分组到一个逻辑链路中。它用于提供高速链接和冗余。最多可以聚合 8 条链路来形成一条逻辑链路。

**以太网通道的需求–**

![](img/2b4ceef43b07d8213a31c0f44d32c150.png)

这是一种拓扑结构，其中两台交换机分别与一台电脑相连。交换机和电脑之间的链路为 1000 兆字节/秒，交换机之间的链路为 100 兆字节/秒。

现在，假设您想发送超过 100mb/s 的流量，那么我们有拥塞，因为交换机之间的链路只有 100mb/s，数据包将开始丢弃。现在，为了解决这个问题，我们应该在交换机之间建立高速链路。为了实现这一点，我们可以简单地用一条高速链路代替当前的链路，或者我们可以捆绑一条以上相同速度为 100mb/s 的链路。通过形成一个 EtherChannel，您可以将一条以上的链路捆绑成一条逻辑链路。

但是，当您用多条链路连接交换机时，STP(生成树协议)将阻塞冗余最少的链路。由于我们制作了一个以太信道，所有的链路(被分组为一个逻辑链路 k)将被视为单个逻辑链路，因此没有链路将被阻塞，并且它将在我们的网络中为我们提供高速链路和冗余。

**标准–**要形成以太网通道，所有端口都应具备:

1.  相同的双工
2.  同样的速度
3.  相同的 VLAN 配置(即本地 VLAN 和允许的 VLAN 应该相同)
4.  交换机端口模式应该相同(接入或中继模式)

**以太网通道协议–**要形成以太网通道，有两个协议，端口聚合协议(PAgP)和链路聚合控制协议(LACP)。

**1。端口聚合协议(PAgp)–**
端口聚合协议是一种思科专有协议，用于形成以太网通道。有不同的模式可以配置您的界面。这些是:

1.  **开:**在这种模式下，接口将是以太网通道的一部分，但不会发生协商。
2.  **可取:**在此模式下，接口会不断尝试将另一侧接口转换为以太网通道。
3.  **Auto:** 在此模式下，当且仅当对方接口请求时，接口将成为 EtherChannel 的一部分。
4.  **关闭:**接口上没有配置以太网通道。

**配置–**

![](img/bbf432a2f07aa508694eb232a31e26fa.png)

有一个小型拓扑，其中两台交换机 S1 和 S2 相互连接，我们必须将这两条链路捆绑成一条逻辑链路。

```
S1(config)# interface fa0/1
S1(config-if)# channel-group 1 mode desirable 
S1(config)# interface fa0/2
S1(config-if)# channel-group 1 mode desirable 

S1(config)# interface port-channel 1
S1(config-if)# switchport trunk encapsulation dot1q
S1(config-if)# switchport mode trunk
```

这里，用户使用了理想模式和交换机端口模式中继。两个交换机上的模式应该相同，因此用户也可以在其他交换机上进行配置。

现在，在交换机 S2 上配置:

```
S2(config)# interface fa0/1
S2(config-if)# channel-group 1 mode desirable 
S2(config)# interface fa0/2
S2(config-if)# channel-group 1 mode desirable 
S2(config)# interface port-channel 1
S2(config-if)# switchport trunk encapsulation dot1q
S2(config-if)# switchport mode trunk
```

**2。链路聚合控制协议(LACP)–**
链路聚合控制协议是一种 IEEE 协议，最初定义于 802.3ad，用于形成以太信道。该协议与思科 PAgP 几乎相似。有不同的模式可以配置您的界面。这些是:

1.  **开:**在这种模式下，接口将是以太网通道的一部分，但不会发生协商
2.  **激活:**在此模式下，接口将持续尝试将另一侧接口转换为以太网通道。
3.  **被动:**在此模式下，当且仅当对方接口请求时，接口将成为以太信道的一部分。
4.  **关闭:**接口上没有配置以太网通道。

**配置–**

![](img/bbf432a2f07aa508694eb232a31e26fa.png)

采用相同的拓扑结构，现在您将在两台交换机上配置 LACP。首先，为 S1 配置:

```
S1(config)# interface fa0/1
S1(config-if)# channel-group mode active 
S1(config)# interface fa0/2
S1(config-if)# channel-group mode active

S1(config)# interface port-channel 1
S1(config-if)# switchport trunk encapsulation dot1q
S1(config-if)# switchport mode trunk
```

现在，为 S2 配置:

```
S2(config)# interface fa0/1
S2(config-if)# channel-group mode active
S2(config)# interface fa0/2
S2(config-if)# channel-group mode active 

S2(config)# interface port-channel 1
S2(config-if)# switchport trunk encapsulation dot1q
S2(config-if)# switchport mode trunk
```