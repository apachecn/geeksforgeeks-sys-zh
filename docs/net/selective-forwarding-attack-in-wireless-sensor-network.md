# 无线传感器网络中的选择性转发攻击

> 原文:[https://www . geesforgeks . org/选择性转发-无线传感器网络攻击/](https://www.geeksforgeeks.org/selective-forwarding-attack-in-wireless-sensor-network/)

在这种类型的[网络攻击](https://www.geeksforgeeks.org/basic-network-attacks-in-computer-network/)中，恶意节点拒绝了促进某些信息包的请求，并确保它们不再被传递。对手可能会有选择地或随机地丢弃数据包。攻击者试图破坏网络的数据包丢失率。

攻击者攻击网络的两种方式是:

1.  **内部攻击:**
    授权的传感器节点的认证可能被破坏，或者对手可能从节点窃取一些密钥或信息，攻击整个网络。检测这样的攻击变得很困难。
2.  **局外人攻击:**
    通过干扰合法节点之间的路由路径。

**有各种类型的选择性转发攻击:**

*   恶意节点禁止信息从授权节点流向基站。从而导致[拒绝服务攻击](https://www.geeksforgeeks.org/denial-of-service-ddos-attack/)，通过攻击整个网络，限制信息从每个节点流向汇聚节点，可以转化为黑洞攻击。
*   未经授权的节点忽略转发信息并随机丢弃它们。相反，它们变得贪婪，并向其他节点发送自己的信息包。这种类型的攻击被称为**忽视和贪婪**。
*   这种攻击的另一种形式是，未经授权的节点延迟流经它们的消息，从而误导节点之间的路由数据。
*   最后一种类型是**盲信攻击**。当数据包从合法节点转发到恶意节点时，它保证合法节点将信息转发到下一个节点，并最终在不被注意的情况下丢弃数据包。它可以攻击各种多跳路由协议，如地理路由、TinyOS 信标等。

**检测和预防方案**根据方案或根据方案的防御进行分类:

**一、**根据方案性质分为 2 个子部分:

*   **集中式和分布式:**
    在集中式方案中，传感器节点头或宿负责检测和防止这种攻击，而在分布式方案中，基站和簇头都负责防止这种攻击。

**二。**在方案防御的基础上，分为以下两部分:

*   **检测和预防:**
    预防型方案不能检测到攻击或故障节点，而是忽略故障节点并将其切断网络。而检测类型方案足以检测攻击或故障节点或者甚至两者。

**对抗此类攻击的各种方案:**

*   A security scheme that detects attack and raises alarms by using multi hop acknowledgements from various sensor nodes in the network. In this, both source nodes and base station can detect the attack and make decisions accordingly even if one of them is compromised.

    这遵循分布式方案方法，并且可以检测是否有任何恶意节点试图丢弃数据包，而不是将其转发给下一个节点。它声称检测这些选择性转发攻击的准确率为 95%。

*   An intrusion detection system (IDS) can detect any possible loophole that can be exploited by the attacker and warns the network about the malicious nodes that might be involved. An intrusion detection system is designed based on specification-based detection.

    这种技术使用一种监视方法，其中相邻节点可以跟踪节点的活动，并查看它是否将实际数据包转发给其他节点。如果丢弃了实际数据包，计数器将递增，并在该值达到某个限制时发出警报。如果许多监视节点发出警报，基站就会得到通知，受损节点就会被移除。

*   A distributed prevention scheme that uses multi-hop acknowledgement to fight selective forwarding attacks.in this scheme, it is assumed that all the sensor nodes are aware of their location and the number of faulty nodes and energy level of network is either known or estimated.

    考虑到能量约束和存在的故障节点，所有的数据传送路径都是通过不确定逻辑推导出来的。如果多路径路由协议不能提供真实的信息，那么传播限制方法就开始使用。

*   Another scheme which uses hexagonal mesh topology. Routing algorithm is applied to find the best path for packet transmission. The nodes near the routing path examines the information transmission of its neighbor nodes, determine the location of the attacker and send these dropped packets again where it was supposed to reach.

    这暴露了选择性转发攻击，该攻击反过来警告邻近节点攻击者的位置，并忽略攻击者节点转发进一步的消息。这种方法确保了真实的数据传递，并且消耗更少的能量和存储。