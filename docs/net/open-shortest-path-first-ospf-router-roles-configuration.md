# 打开最短路径优先(OSPF)路由器角色和配置

> 原文:[https://www . geesforgeks . org/open-最短路径-first-OSPF-router-roles-configuration/](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-router-roles-configuration/)

先决条件–[开放最短路径优先(OSPF)](https://www.geeksforgeeks.org/computer-network-open-shortest-path-first-ospf-protocol-states/)
开放最短路径优先(OSPF)是一种链路状态路由协议，用于使用自己的 SPF 算法找到源路由器和目的路由器之间的最佳路径。

**开放最短路径优先(OSPF)路由器角色–**
一个区域是一组连续的网络和路由器。属于同一区域的路由器共享一个公共拓扑表和区域 I。我想要的区域与路由器的接口相关联，因为路由器可以属于多个区域。路由器在 OSPF 有一些作用:

![](img/6a7f920c26f799aa62e633cf5e7a53e4.png)

1.  **骨干路由器–**0 区称为骨干区，0 区的路由器称为骨干路由器。如果路由器部分位于区域 0 中，那么它也是骨干路由器。
2.  **内部路由器–**内部路由器是指所有接口都在一个区域内的路由器。
3.  **区域边界路由器(ABR)–**将主干区域与另一区域连接起来的路由器称为区域边界路由器。它属于不止一个领域。因此，AbR 维护多个链路状态数据库，描述主干拓扑和其他区域的拓扑。
4.  **区域总结边界路由器(asBR)–**当 OSPF 路由器连接到不同的协议(如 EIGRP 或边界网关协议)或任何其他路由协议时，它被称为 AS。连接两个不同自治系统(其中一个接口运行 OSPF)的路由器称为区域总结边界路由器。这些路由器执行重新分发。ASBRs 同时运行 OSPF 和另一种路由协议，如 RIP 或 BGP。ASBRs 在其整个 AS 中通告交换的外部路由信息。

**注意–**路由器可以同时是骨干路由器和区域边界路由器，即一台路由器一次可以执行多个角色。

**配置–**

![](img/eb68a8edb22aa2e99e583e5ac278b240.png)

有一个小型拓扑，其中连接了 3 台路由器，即 R1、R2 和 R3。R1 连接到网络 10.255.255.80/30(接口 fa0/1)、192.168.10.48/29(接口 fa0/0)和 10.255.255.8/30(接口 gi0/0)
**注意–**在图中，IP 地址是用它们相应的接口来写的，但由于必须通告网络，因此您必须写网络 I’d。R2 连接到网络 192.168.10.64/29(接口 fa0/0)、10.255.255.80/30(接口 fa0/1)。R3 连接到网络 10.255.255.8/30 (int fa0/1)、192.168.10.16/29 (int fa0/0)。

现在，为 R1 配置 OSPF。

```
R1(config)#router ospf 1
R1(config-router)#network 192.168.10.48 0.0.0.7 area 1
R1(config-router)#network 10.255.255.80 0.0.0.3 area 1
R1(config-router)#network 10.255.255.8 0.0.0.3 area 1
```

这里，1 是我要的 OSPF 实例或过程。可以相同，也可以不同(没关系)。这里使用了通配符掩码，使用的区域是 1。
现在，配置 R2

```
R2(config)#router ospf 1
R2(config-router)#network 192.168.10.64 0.0.0.7 area 1
R2(config-router)#network 10.255.255.80 0.0.0.3 area 1
```

同样，对于 R3

```
R3(config)#router ospf 1
R3(config-router)#network 192.168.10.16 0.0.0.7 area 1
R3(config-router)#network 10.255.255.8 0.0.0.3 area 1
```

您可以通过键入命令来检查配置

```
R3#show ip protocols 
```