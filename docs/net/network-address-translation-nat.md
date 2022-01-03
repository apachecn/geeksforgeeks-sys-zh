# 网络地址转换(NAT)

> 原文:[https://www . geesforgeks . org/network-address-translation-NAT/](https://www.geeksforgeeks.org/network-address-translation-nat/)

要访问互联网，需要一个公共 IP 地址，但我们可以在专用网络中使用私有 IP 地址。NAT 的思想是允许多个设备通过一个公共地址访问互联网。为此，需要将私有 IP 地址转换为公共 IP 地址。**网络地址转换(NAT)** 是一个过程，其中一个或多个本地 IP 地址被转换成一个或多个全局 IP 地址，反之亦然，以便向本地主机提供互联网访问。此外，它还转换端口号，即在将被路由到目的地的数据包中用另一个端口号屏蔽主机的端口号。然后，它会在 NAT 表中输入相应的 IP 地址和端口号。NAT 通常在路由器或防火墙上运行。

**网络地址转换(NAT)工作–**
通常，边界路由器配置为 NAT，即在本地(内部)网络中有一个接口，在全局(外部)网络中有一个接口的路由器。当数据包在本地(内部)网络之外传输时，NAT 会将该本地(私有)IP 地址转换为全局(公共)IP 地址。当数据包进入本地网络时，全局(公共)IP 地址会转换为本地(私有)IP 地址。

如果网络地址转换用完了地址，即在配置的地址池中没有剩余地址，那么数据包将被丢弃，并向目的地发送一个互联网控制消息协议(ICMP)主机无法到达的数据包。

**为什么要屏蔽端口号？**
假设在一个网络中，两台主机 A 和 B 相连。现在，它们都同时在主机端请求相同的目的地、相同的端口号，比如 1000。如果网络地址转换只转换 IP 地址，那么当它们的数据包到达网络地址转换时，它们的两个 IP 地址都将被网络的公共 IP 地址屏蔽并发送到目的地。目的地将向路由器的公共 IP 地址发送回复。因此，在收到回复时，NAT 不清楚哪个回复属于哪个主机(因为 A 和 B 的源端口号相同)。因此，为了避免这样的问题，网络地址转换也会屏蔽源端口号，并在网络地址转换表中创建一个条目。

**NAT 内部和外部地址–**
内部是指必须翻译的地址。外部是指不受组织控制的地址。这些是将进行地址转换的网络地址。

![](img/28563ce5df1fd976bdb0e0bef4fbdbac.png)

*   **内部本地地址–**分配给内部(本地)网络上的主机的 IP 地址。该地址可能不是服务提供商分配的 IP 地址，即这些是私有 IP 地址。这是从内部网络看到的内部主机。

*   **内部全局地址–**代表一个或多个内部本地 IP 地址对外的 IP 地址。从外部网络看，这是内部主机。

*   **外部本地地址–**这是翻译后本地网络中目的主机的实际 IP 地址。

*   **外部全局地址–**这是从外部网络看到的外部主机。它是转换前外部目的主机的 IP 地址。

**网络地址转换(NAT)类型–**
配置 NAT 有 3 种方式:

1.  **Static NAT –** In this, a single unregistered (Private) IP address is mapped with a legally registered (Public) IP address i.e one-to-one mapping between local and global addresses. This is generally used for Web hosting. These are not used in organizations as there are many devices that will need Internet access and to provide Internet access, a public IP address is needed. 

    假设，如果有 3000 台设备需要接入互联网，组织必须购买 3000 个公共地址，这将非常昂贵。

2.  **Dynamic NAT –** In this type of NAT, an unregistered IP address is translated into a registered (Public) IP address from a pool of public IP addresses. If the IP address of the pool is not free, then the packet will be dropped as only a fixed number of private IP addresses can be translated to public addresses. 

    假设，如果有一个由 2 个公共 IP 地址组成的池，那么在给定时间只能转换 2 个私有 IP 地址。如果第三个私有 IP 地址想要访问互联网，那么数据包将被丢弃，因此许多私有 IP 地址被映射到公共 IP 地址池。当想要访问互联网的用户数量固定时，使用 NAT。这也是非常昂贵的，因为组织必须购买许多全球 IP 地址来组成一个池。

3.  **端口地址转换(PAT)–**这也称为 NAT 过载。在这种情况下，许多本地(私有)IP 地址可以转换为一个注册的 IP 地址。端口号用于区分流量，即哪个流量属于哪个 IP 地址。这是最常用的方法，因为它具有成本效益，因为数以千计的用户只需使用一个真实的全球(公共)IP 地址就可以连接到互联网。

**NAT 的优势–**

*   网络地址转换保存合法注册的 IP 地址。

*   它提供了隐私，因为设备的 IP 地址，发送和接收的流量，将被隐藏。

*   当网络发展时，消除地址重新编号。

**NAT 的劣势–**

*   转换会导致切换路径延迟。

*   启用网络地址转换后，某些应用程序将无法运行。

*   使 IPsec 等隧道协议变得复杂。

*   此外，路由器作为网络层设备，不应该篡改端口号(传输层)，但由于 NAT，它必须这样做。