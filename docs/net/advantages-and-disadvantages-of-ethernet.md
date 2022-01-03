# 以太网的优缺点

> 原文:[https://www . geeksforgeeks . org/以太网的优缺点/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-ethernet/)

**以太网**是[局域网(LAN)](https://www.geeksforgeeks.org/local-area-network-lan-technologies/) 技术。该系统由在局域网连接上连接多个系统的规则组成。除了局域网，它还用于城域网和广域网。一种将多个计算机系统连接起来形成局域网的系统，有规则控制数据流，避免两个或多个系统在传输过程中出现任何错误。**罗伯特·梅特卡夫**发明以太网技术。它被标准化为 IEEE 802.3

以太网在 [TCP/IP 模型](https://www.geeksforgeeks.org/tcp-ip-model/)架构的链路层运行。它提供无连接通信，在通过网络传输任何数据之前，系统会检查访问介质是否可以自由传输数据。它使用载波侦听多路访问/冲突检测(CSMA/光盘)来确定空闲介质。此外，它建立在星型拓扑结构上。

**以太网使用两种电缆:**

*   [Twisted pair](https://www.geeksforgeeks.org/what-is-stpshielded-twisted-pair/) .
*   [Optical fiber](https://www.geeksforgeeks.org/fiber-optics-and-types/) .

根据数据传输速度，它基本上分为三种类型的以太网。

*   Basic Ethernet is the slowest of all Ethernet networks, providing a speed of (about 10Mbps, 2500m).
*   Fast Ethernet (about 100Mbps, 250 meters), between basic network and Gigabit network.
*   Gigabit Ethernet (about 1Gbps, 250 meters).

**以太网的优势:**

*   Gigabit Ethernet provides the fastest speed of 1Gbps. The speed range is more than 10 times that of fast Ethernet.
*   We don't need too much cost to set up Ethernet. Relatively cheap. The total cost of induction is less.
*   In Ethernet, all nodes have equal privileges. It does not follow the client-server architecture.
*   No switches or hubs are required.
*   Simple maintenance.
*   The cable used to connect the Ethernet system is very noisy.
*   Because of the strong noise, the standard of information transmission will not be lowered. The data transmission quality is good.
*   The latest versions such as Gigabit Ethernet and Wireless Ethernet (IEEE 802.11ac/11ad) are adopted, and the data transmission speed is 1-100Gbps.

**以太网的缺点:**

*   It provides uncertain services.
*   It is not suitable for real-time applications because it requires deterministic services.
*   Because the priority package cannot be set, it is not suitable for client-server architecture.
*   In an interactive application, the data is extremely small, and it is hoped that the data can be transmitted quickly. In Ethernet, the minimum frame size is limited to 46B. Therefore, it is not an honest choice for interactive applications.
*   If you use it in an interactive application, you must input dummy data to form the mandatory frame size 46B.
*   Not suitable for traffic-intensive applications. If the traffic rate on Ethernet increases, the efficiency of Ethernet will decrease.
*   It provides connectionless communication through the network.
*   The receiver cannot send any knowledge after receiving the data packet.
*   If there is any problem with Ethernet, it is difficult to troubleshoot the cables or nodes in the network that cause the actual problem.
*   100 base-T4 version does not support full-duplex data communication mode.