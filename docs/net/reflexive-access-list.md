# 自反访问列表

> 原文:[https://www.geeksforgeeks.org/reflexive-access-list/](https://www.geeksforgeeks.org/reflexive-access-list/)

默认情况下，[访问列表](https://www.geeksforgeeks.org/computer-network-access-lists-acl/)不会跟踪会话。访问列表由从上到下扫描的各种允许和拒绝规则组成。如果任何一个条件匹配，那么它被执行，并且没有其他条件匹配。

对于非常小的办公室来说，自反访问列表充当有状态防火墙，因为它只允许网络内发起的流量，而拒绝来自网络外的其他数据包。

**自反访问列表–**
自反访问列表是一个访问列表，只允许回复网络内发起的会话(来自外部网络)的数据包。

**工作–**
当会话在网络内发起并通过路由器(操作自反访问列表)到达网络外时，自反访问列表被触发。因此，它会为网络内发起的流量创建一个临时条目，并且只允许来自外部网络的属于会话一部分的流量(网络内生成的流量)。会话结束时，此临时条目将被删除。

**临时入境的特点–**

1.  该条目指定了与原始出站数据包(发往网络外部的数据包)相同的源地址和目的地址，只是它们在来自网络外部时被交换。
2.  这些条目应该具有与原始出站数据包相同的源端口号和目的端口号，除非它们在来自网络外部时被交换。
3.  条目应该具有与原始出站数据包相同的协议。

**自反访问列表的特征–**

1.  自反访问列表应该嵌套在命名的扩展访问列表中。
2.  它不能直接应用于接口。
3.  会话开始时会生成一个临时条目，会话结束时会自动销毁。
4.  它在访问列表的末尾没有隐式拒绝。
5.  就像正常的访问列表一样，如果其中一个条件匹配，那么就不会再计算条目。
6.  自反访问列表不能用编号的访问列表定义
7.  自反访问列表不能用命名或编号的标准访问列表来定义。

**配置–**

![](img/529249ce5b7aca3ed7be7f366950d400.png)

fa0/0 和 11 上有两台路由器，即路由器 1 (IP 地址–10 . 1 . 1 . 1/24)。fa0/1 上的 1.1.1/24)、路由器 2(Fa0/0 上的 IP 地址-11.1.1.2/24 和 fa0/1 上的 12.1.1.1/24)以及 PC1 (IP 地址-10.1.1.2/24)和 PC2 (IP 地址-12.1.1.2/24)。首先，我们将通过 EIGRP 向所有路由器提供路由，以便个人电脑能够相互 ping 通。

在路由器 1 上配置 Eigrp:

```
router1(config)#router Eigrp 100
router1(config-router)#network 10.1.1.0
router1(config-router)#network 11.1.1.0
router1(config-router)#No auto-summary
```

在路由器 2 上配置 Eigrp:

```
router2(config)#router Eigrp 100
router2(config-router)#network 11.1.1.0
router2(config-router)#network 12.1.1.0
router2(config-router)#No auto-summary
```

现在，我们将允许来自网络内部(10.1.1.0 网络)的 IP、TCP 和 UDP 流量，并评估来自网络外部(12.1.1.0 和 11.1.1.0 网络)的流量。创建一个名为“自反”的访问列表，供内部流量流出。

```
router1(config)#ip Access-list extended reflexive 
router1(config-ext-na)#permit ip any any reflect ip_database
router1(config-ext-nacl)#permit tcp any any reflect tcp_database
router1(config-ext-nacl)#permit udp any any reflect udp_database
```

在这里，我们允许 IP、TCP 和 UDP 流量，并将其命名为 ip_database、tcp_database 和 udp_database。

**注意–**
这里，Reflexive 是访问列表的名称，而不是关键字。现在，将此访问列表应用于路由器 1 的接口 fa0/1 的出站，以便允许流量流出路由器。

```
router1(config)#int fa0/1
router1(config-if)#ip access-group reflexive out
```

现在，对入站流量(即进入网络的流量)应用访问列表。如果流量是由内部(10.1.1.0)网络发起的，我们应该只允许该流量进入内部。

```
router1(config)#ip access-list extended reflexive_in
router1(config-ext-nacl)#permit Eigrp any any
router1(config-ext-nacl)#evaluate tcp_database
router1(config-ext-nacl)#evaluate udp_database
router1(config-ext-nacl)#evaluate ip_database 
```

在这里，我们允许 Eigrp 流量，因此路由器之间应该存在可达性，否则以太网内部将不会有流量返回。
我们已经评估了 udp _ databse、ip_database 和 tcp_database，以便允许在网络内部发起的流量(tcp、udp 或 ip)。现在，将此应用于内部方向的接口 fa0/1，因为应该评估进入内部的流量。

```
router1(config)#int fa0/1
router1(config-if)#ip access-group reflexive_in in
```

这里，自反 _in 是访问列表的名称。

**优势–**自反访问列表的优势有:

*   易于实施。
*   对来自外部网络的流量提供更好的控制。
*   提供针对某些 Dos 攻击和欺骗的安全性。

**劣势–**

*   有些应用程序使用动态端口，因此可能会出现故障。对于自反访问列表，源端口和目标端口应该是静态的。