# 保护路由协议

> 原文:[https://www.geeksforgeeks.org/securing-routing-protocols/](https://www.geeksforgeeks.org/securing-routing-protocols/)

先决条件–[路由信息协议(RIP)](https://www.geeksforgeeks.org/computer-network-routing-information-protocol-rip/) 、 [EIGRP 基础知识](https://www.geeksforgeeks.org/computer-network-eigrp-fundamentals/)、 [OSPF 协议基础知识](https://www.geeksforgeeks.org/computer-network-open-shortest-path-first-ospf-protocol-fundamentals/)
路由是第 3 层设备(路由器或第 3 层交换机)在源网络和目的网络之间找到最佳路径的过程。动态路由协议用于减少管理员开销，即管理员必须配置更少，但默认情况下，所有路由信息对所有相关方都是可见的，因为它没有加密，因此容易受到攻击。

我们可以通过创建密钥链并将其应用于通告路由的接口，对路由协议(如 RIP、EIGRP 和 OSPF)进行身份验证，从而保护路由协议的安全。在这里，我们将不讨论协议，而是将身份验证放在 RIP、EIGRP 和 OSPF 上。

**1。路由信息协议(RIP)–**
RIP 是一种距离矢量路由协议，使用端口号 520，管理距离为 120。它是一个应用层协议，有 3 个版本，其中只有一个版本支持身份验证。

**配置–**

![](img/abbfb4cc9801cb7dcdc57beafe46385b.png)

有 3 台路由器的名称分别为路由器 1(以太网 0/0 上的 IP 地址-192.168.1.1)、路由器 2(以太网 0/0 上的 IP 地址-192.168.1.2 和以太网 0/1 上的 192.168.2.1)、路由器 3(以太网 0/0 上的 IP 地址-192.168.2.2)。路由器 1 将无法 ping 通路由器 3，因为它没有通往 192.168.2.0 网络的路由。为此，我们将在所有路由器上执行 RIP 路由，然后对它们进行身份验证。

首先为 RIP 配置路由器 1:

```
router1(config)#router rip
router1(config-router)#network 192.168.1.0
router1(config-router)#no auto-summary
router1(config-router)#version 2
```

现在，为路由器 2 配置 RIP:

```
router2(config)#router rip
router2(config-router)#network 192.168.1.0
router2(config-router)#network 192.168.2.0
router2(config-router)#no auto-summary
router2(config-router)#version 2
```

现在，为路由器 3 配置 RIP:

```
router3(config)#router rip
router3(config-router)#network 192.168.2.0
router3(config-router)#no auto-summary 
router3(config-router)#version 2
```

这里，我们启用了 RIP 版本 2，因为它支持身份验证。现在，为了能够从路由器 1(192 . 168 . 1 . 1)Ping 通路由器 3 (192.168.2.2)，请逐一对所有路由器进行身份验证。首先制作一个钥匙链，应用到界面:

```
router1(config)#key chain cisco
router1(config-keychain)#key 1
router1(config-keychain-key)#key-string cisco1
router1(config-keychain-key)#exit
router1(config-keychain)#exit
router1(config)#int ethernet0/0
router1(config-if)#ip rip authentication mode md5
router1(config-if)#ip rip authentication key-chain cisco
```

在这里，我们已经创建了一个名为 cisco 的密钥链，它具有密钥 d 1 和密钥串 cisco1，并将其应用于接口 ethernet0/0(我们已经在此通告了 RIP)。
现在在路由器 2 上创建相同的钥匙链:

```
router2(config)#key chain cisco
router2(config-keychain)#key 1
router2(config-keychain-key)#key-string cisco1
router2(config-keychain-key)#exit
router2(config-keychain)#exit
router2(config)#int ethernet0/0
router2(config-if)#ip rip authentication mode md5
router2(config-if)#ip rip authentication key-chain cisco
```

**注意–**在两台路由器上，密钥链的配置、它的 id 和密钥串应该是相同的。

**2。增强型内部网关路由协议–**
EIGRP 是一种高级距离路由协议，使用协议号 88，管理距离 90。它是一个网络层协议，支持明文和 md5 认证。

**配置–**

![](img/abbfb4cc9801cb7dcdc57beafe46385b.png)

采用相同的拓扑结构，有 3 台路由器分别命名为路由器 1(以太网 0/0 上的 ip 地址-192.168.1.1)、路由器 2(以太网 0/0 上的 ip 地址-192.168.1.2 和以太网 0/1 上的 192.168.2.1)、路由器 3(以太网 0/0 上的 IP 地址-192.168.2.2)。此外，路由器 1 将无法 ping 通路由器 3，因为它没有通往 192.168.2.0 网络的路由。为此，我们将在所有路由器上执行 EIGRP 路由，然后对它们进行身份验证。

在路由器 1 上配置 EIGRP:

```
router1(config)#router eigrp 100
router1(config-router)#network 192.168.1.0
router1(config-router)#no auto-summary
```

这里使用的是 100 号自治系统。
在路由器 2 上配置 EIGRP:

```
router2(config)#router EIGRP 100
router2(config-router)#network 192.168.1.0
router2(config-router)#network 192.168.2.0
router2(config-router)#no auto-summary
```

在路由器 3 上配置 EIGRP:

```
router3(config)#router eigrp 100
router3(config-router)#network 192.168.2.0
router3(config-router)#no auto-summary
```

现在，使用 eigrp 对路由器进行身份验证。

```
router1(config)#key chain cisco
router1(config-keychain)#key 1
router1(config-keychain-key)#key-string cisco1
router1(config-keychain-key)#exit
router1(config-keychain)#exit
router1(config)#int ethernet0/0
router1(config-if)#ip authentication mode eigrp 100 md5
router1(config-if)#ip authentication key-chain eigrp 100 cisco
```

在路由器 2 上配置相同内容:

```
router2(config)#key chain cisco
router2(config-keychain)#key 1
router2(config-keychain-key)#key-string cisco1
router2(config-keychain-key)#exit
router2(config-keychain)#exit
router2(config)#int ethernet0/0
router2(config-if)#ip authentication mode eigrp 100 md5
router2(config-if)#ip authentication key-chain eigrp 100 cisco
```

**注意–**在两台路由器上，密钥链的配置、其标识和密钥串应该相同。

**3。开放最短路径优先(OSPF)–**
OSPF 是一种链路状态路由协议，使用协议号 89 和管理距离 110。它是一个网络层协议，支持明文和 md5 认证。

**配置–**

![](img/abbfb4cc9801cb7dcdc57beafe46385b.png)

采用相同的拓扑结构，有 3 台路由器分别命名为 router1(以太网 0/0 上的 ip 地址-192.168.1.1)、router2(以太网 0/0 上的 ip 地址-192.168.1.2 和以太网 0/1 上的 192.168.2.1)、router3(以太网 0/0 上的 ip 地址-192.168.2.2)。为此，我们将在所有路由器上执行 OSPF 路由，然后对它们进行身份验证。
在路由器 1 上配置 OSPF:

```
router1(config)#router ospf 1
router1(config-router)#network 192.168.1.0 0.0.0.255 area 0
```

在路由器 2 上配置 OSPF:

```
router2(config)#router ospf 1
router2(config-router)#network 192.168.1.0 0.0.0.255 area 0
router2(config-router)#network 192.168.2.0 0.0.0.255 area 0
```

在路由器 3 上配置 ospf:

```
router3(config)#router OSPF 1
router2(config-router)#network 192.168.2.0 0.0.0.255 area 0
```

在路由器 1 上配置身份验证:

```
router1(config)#key chain cisco
router1(config-keychain)#key 1
router1(config-keychain-key)#key-string cisco1
router1(config-keychain-key)#exit
router1(config-keychain)#exit
router1(config)#int ethernet0/0
router1(config-if)#ip ospf Authentication message-digest
router1(config-if)#ip ospf authentication-key cisco1
```

在路由器 2 上配置身份验证:

```
router2(config)#key chain cisco
router2(config-keychain)#key 1
router2(config-keychain-key)#key-string cisco1
router2(config-keychain-key)#exit
router2(config-keychain)#exit
router2(config)#int ethernet0/0
router2(config-if)#ip ospf authentication message-digest
router2(config-if)#ip ospf authentication-key cisco1
```

**注–**

*   在两台路由器上，密钥链的配置、id 和密钥串应该相同。
*   Md5 容易受到暴力攻击，因此建议使用包含数字或特殊字符的密码，密码应该很长。