# 网络地址转换的类型

> 原文:[https://www . geesforgeks . org/type-of-network-address-translation-NAT/](https://www.geeksforgeeks.org/types-of-network-address-translation-nat/)

先决条件–[网络地址转换(NAT)](https://www.geeksforgeeks.org/computer-network-network-address-translation-nat/)
网络地址转换(NAT)是将一个或多个本地 IP 地址转换为一个或多个全局 IP 地址的过程，反之亦然，以便为本地主机提供互联网访问。NAT 通常在路由器或防火墙上运行。

**网络地址转换(NAT)工作–**
通常，边界路由器配置为 NAT，即在本地(内部)网络中有一个接口，在全局(外部)网络中有一个接口的路由器。当数据包在本地(内部)网络之外传输时，NAT 会将该本地(私有)IP 地址转换为全局(公共)IP 地址。当数据包进入本地网络时，全局(公共)IP 地址会转换为本地(私有)IP 地址。

如果网络地址转换用完了地址，即在配置的地址池中没有剩余地址，那么数据包将被丢弃，并向目的地发送一个互联网控制消息协议(ICMP)主机无法到达的数据包。

**NAT 类型–**
NAT 有 3 种类型:

**1。静态网络地址转换–**
在这种情况下，单个私有 IP 地址与单个公共 IP 地址映射，即私有 IP 地址转换为公共 IP 地址。它用于网络托管。

**配置–**

![](img/9f2bfad6b75f850a5641e38458ec1909.png)

这是一个小型拓扑，其中，PC 的 IP 地址为 192.168.1.1/24，路由器 R1 的接口 fa0/0 的 IP 地址为 192.168.1.2/24，12.1.1.1/24 的接口 fa0/1，服务器的 IP 地址为 73.1.1.2/24.

现在，内部局部和内部全局如图所示。通过命令 IP nat 在静态源内部配置静态 NAT。

```
R1(config)# ip nat inside source static 192.168.1.1 12.1.1.1 
```

现在，我们已经将路由器的内部接口配置为内部网络地址转换，将外部接口配置为外部网络地址转换。

```
R1(config)# int fa0/0
R1(config-if)# ip nat inside 
R1(config)# int fa0/1
R1(config-if)# ip nat outside 
```

**2。动态网络地址转换–**
在这种类型的网络地址转换中，多个私有 IP 地址被映射到一个公共 IP 地址池。当我们知道在给定时间点想要访问互联网的固定用户数量时，就会用到它。

**配置–**

![](img/9f2bfad6b75f850a5641e38458ec1909.png)

有一台 IP 地址为 192.168.1.1/24 的电脑，接口 fa0/0 上的 IP 地址为 192.168.1.2/24 的路由器 R1，fa0/1 上的 12.1.1.1/24，以及一台 IP 地址为 73.1.1.2/24.的服务器
现在，首先配置访问列表:

```
R1(config)# access-list 1 permit 192.168.1.0 0.0.0.255 
```

配置将从中选择公共 IP 的 nat 池。

```
R1(config)# ip nat pool pool1 12.1.1.1 12.1.1.3 netmask 255.255.255.0 
```

现在，启用动态 NAT:

```
R1(config)# ip nat inside source list 1 pool pool1
```

最后，我们必须将路由器接口配置为内部或外部。

```
R1(config)# int fa0/0
R1(config-if)# ip nat inside
R1(config)# int fa0/1
R1(config-if)# ip nat outside
```

**3。端口地址转换(PAT)–**
这也称为 NAT 过载。在这种情况下，许多本地(私有)IP 地址可以转换为单个公共 IP 地址。端口号用于区分流量，即哪个流量属于哪个 IP 地址。这是最常用的方法，因为它具有成本效益，因为数以千计的用户只需使用一个真实的全球(公共)IP 地址就可以连接到互联网。

**配置–**

![](img/9f2bfad6b75f850a5641e38458ec1909.png)

采用相同的拓扑，PC1 的 IP 地址为 192.168.1.1/24，路由器 R1 的 IP 地址为 192.168.1.2/24，接口 fa0/0 为 12.1.1.1/24，服务器的 IP 地址为 73.1.1.2/24.
现在，首先配置访问列表:

```
R1(config)# access-list 1 permit 192.168.1.0 0.0.0.255 
```

配置将从中选择公共 IP 的 nat 池。

```
R1(config)# ip nat pool pool1 12.1.1.1 12.1.1.1 netmask 255.255.255.0
```

这里，请注意 nat 池被缩小到只有一个 IP 地址，并且使用的 IP 地址是路由器的外部接口 IP 地址。如果你有额外的知识产权，那么你也可以使用它。
现在，启用动态 NAT 过载(PAT):

```
R1(config)# ip nat inside source list 1 pool pool1 overload
```

或者我们也可以使用

```
R1(config)# ip nat inside source list 1 interface fastEthernet 0/1 overload
```

最后，我们必须将路由器接口配置为内部或外部。

```
R1(config)# int fa0/0
R1(config-if)# ip nat inside
R1(config)# int fa0/1
R1(config-if)# ip nat outside
```

**NAT 如何保护你:-**

-它对外界隐藏网络上任何设备的 IP 地址，给所有设备一个单一的地址。

-它要求设备已经请求了每个传入的信息包。如果恶意数据包不在预期通信列表中，它就会被拒绝。

-一些防火墙可以使用白名单来阻止未经授权的传出流量，因此如果您感染了一个恶意软件，您的防火墙可能会阻止它与您的设备通信。