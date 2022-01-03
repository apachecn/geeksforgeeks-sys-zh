# 基于上下文的访问控制(CBAC)

> 原文:[https://www . geesforgeks . org/context-based-access-control-cbac/](https://www.geeksforgeeks.org/context-based-access-control-cbac/)

最近，[访问控制列表](https://www.geeksforgeeks.org/computer-network-access-lists-acl/)被用于包过滤和保护。ACL 按照管理员提供的规则顺序工作。规则由各种允许和拒绝条件组成。但是 ACL 的缺点是它只过滤到传输层的流量。

因此，对于低预算防火墙功能，使用具有适当 IOS 版本的思科路由器。我们可以通过两种方法实现基于 IOS 的防火墙:

1.  基于上下文的访问控制(CBAC)功能
2.  基于区域的防火墙

**基于上下文的访问控制(CBAC)–**
ACL 为传输层提供流量过滤和保护，而另一方面，CBAC 为应用层提供相同的功能。借助 CBAC 配置，路由器可以充当防火墙。

**工作–**
CBAC 就像一个反射性的访问列表一样工作，但除此之外，它还维护一个状态表，其中会话保存在内存中。当网络中的设备发起会话时，状态表中会有一个动态条目，出站(外出)流量可以通过路由器(基于 IoS 的防火墙)。借助于这个条目，出站流量的回复可以通过路由器(基于 IoS 的防火墙)，因为它有一个在网络内发起的流量条目。这是通过基于 IoS 的防火墙 CBAC 机制实现的，因为它在访问列表上打开临时漏洞(应用于入站流量)以允许回复数据包。

**特色–**CBAC 的一些特色是:

1.  **检查流量–**CBAC 维护对数据包有效负载进行更深入检查所需的 TCP /UDP 信息。
2.  **过滤流量–**CBAC 过滤来自可信网络的流量，并通过防火墙，只有在状态表中有条目时才允许回复。它能够智能过滤第 7 层的流量。
3.  **检测入侵–**CBAC 检查连接建立的速率，通过该速率可以检测到像 Dos 攻击、TCP syn 攻击等攻击。在此基础上，CBAC 机制可以导致连接重新建立或丢弃恶意数据包。
4.  **生成警报和审核–**运行 CBAC 机制的路由器记录有关已建立的连接、发送的字节数、源和目标 IP 地址的信息。

**配置–**

![](img/b208ea0fb99d2e4b64562c7c03afd33c.png)

共有 3 台路由器，即路由器 1(Fa0/0 上的 ip 地址–10 . 1 . 1 . 1/24)、路由器 2(Fa0/0 上的 ip 地址-10.1.1.2/24 和 fa0/1 上的 10.1.2.1/24)和路由器 3 (ip 地址–10 . 1 . 2 . 2/24)。首先，我们将通过 EIGRP 向所有路由器提供路由，以便路由器能够相互 ping 通。
之后，我们将路由器 3 设为 ssh 服务器，路由器 2(CBAC 将在其上运行)仅在路由器 2 检查流量后才允许流量通过。

首先在路由器 1 上配置 EIGRP:

```
router1(config)#router eigrp 100
router1(config-router)#network 10.1.1.0
router1(config-router)#no auto-summary 
```

现在，在路由器 2 上配置 EIGRP 以到达其他网络:

```
router2(config)#router eigrp 100
router2(config-router)#network 10.1.1.0
router2(config-router)#network 10.1.2.0
router2(config-router)#no auto-summary
```

现在，在路由器 3 上配置 eigrp:

```
router3(config)#router eigrp 100
router3(config-router)#network 10.1.2.0
router3(config-router)#no auto-summary
```

现在，我们将在路由器 3 上配置 ssh:

```
router3(config)#ip domain name GeeksforGeeks.com
router3(config)#username saurabh password cisco
router3(config)#line vty 0 4
router3(config-line)#transport input ssh
router3(config-line)#login local 
router3(config)#crypto key generate rsa label Cisco.com modulus 1024
```

现在，我们将在路由器 2 上制作一个访问列表，通过该列表，我们将拒绝除 EIGRP 之外的所有流量，因为 EIGRP 将维护所有路由器的可达性。

```
router2(config)#ip Access-list extended 100
router2(config-ext-nacl)#permit eigrp any any 
router2(config-ext-nacl)#deny ip any any
```

现在，将其应用于界面:

```
router2(config)#int fa0/1
router2(config-if)#ip access-group 100 in
```

现在，路由器 1 将无法 ssh 路由器 3，因为我们已经应用了访问列表，它将只接受 Eigrp 数据包，而拒绝所有其他数据包。
现在，将路由器 2 上的 CBAC 配置为检查 ssh 流量(仅允许由操作 CBAC 的 IoS 路由器检查的流量。

```
router2(config)#!cbac
router2(config)#ip inspect name Cisco ssh
```

第一个命令(！cbac)将启用 cbac 功能，而第二个命令将检查 ssh 流量。
现在，对界面进行检查:

```
router2(config)#int fa0/1
router2(config-if)#ip inspect cisco out
```

现在，路由器 1 将能够对路由器 3 进行 ssh，因为当 ssh 数据包离开出站(fa0/1)接口时，路由器 2 会首先对其进行检查(如我们所配置的)。
这可以通过以下方式验证:

```
router2#show ip inspect all
```

**注意–**
这里，访问列表应用于入站，CBAC 应用于出站，因为我们只希望该流量来自内部网络发起的网络外部(10.1.1.1)。应用于接口出站(进入 fa0/1)的 CBAC 在应用于接口入站的访问列表上创建临时漏洞，以允许通过 ACL 返回数据包。

**局限性–**cbac 机制的一些局限性包括:

1.  CBAC 不容易理解，也就是说，它需要我们想要执行的协议和操作的详细知识。
2.  CBAC 机制无法检查来自路由器(我们在其上配置了 CBAC)本身的流量。
3.  没有状态表故障转移支持。如果一台路由器出现故障，则另一台冗余路由器可以用作 CBAC 防火墙，但状态表不会重复，因此必须重建状态表，从而重建一些连接。
4.  它不检查加密数据包，如 IPsec。