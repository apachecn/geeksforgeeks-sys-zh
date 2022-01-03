# 交互连接建立(ICE)

> 原文:[https://www . geesforgeks . org/interactive-connectivity-establishment-ice/](https://www.geeksforgeeks.org/interactive-connectivity-establishment-ice/)

先决条件–[网络地址转换(NAT)](https://www.geeksforgeeks.org/network-address-translation-nat/)

**什么是 ICE？**
交互式连接建立(ICE)用于互联网上的两个节点必须尽可能直接通信的问题，但是 NAT 和防火墙的存在使得节点之间难以相互通信。这是一种网络技术，它利用 STUN(用于网络地址转换的会话遍历实用程序)和 TURN(使用围绕网络地址转换的中继进行遍历)在两个节点之间建立尽可能直接的连接。

**它是如何工作的？**
要了解 ICE 是如何工作的，我们需要了解 STUN 协议及其扩展 TURN 协议的工作原理。

*   **STUN(用于 NAT 的会话遍历实用程序):**
    对于 NAT 下具有本地地址的端点，本地网络之外的其他端点无法到达该端点，因此无法建立连接。当这种情况发生时，端点可以从 STUN 服务器请求它的公共 IP 地址。这个公共可达的 IP 可以被其他端点用来建立连接。但是当端点处于对称 NAT 下时，这种情况会失败，这在大多数实际情况下都会发生。这就是 TURN 服务器出现的地方。

*   **TURN (Traversal Using Relays Around NATs):**
    TURN server as the name suggests is used as a relay server or an intermediate server to exchange data. When any endpoint under Symmetric NAT can contact a TURN server which is on the public internet to establish a connection the endpoint is then called a TURN client. The disadvantage of using a TURN server is that it is required throughout the whole time span of the session unlike STUN server which no longer needed after the connection is established. Therefore in ICE technique STUN is used as default.

    ICE 是使用 STUN 和 TURN 协议建立连接的技术。在开始时，端点不知道自己的网络拓扑，无论它们是在单个网络地址转换下还是在多级网络地址转换下，以及网络地址转换的类型，ICE 让端点使用 STUN 服务器发现这一点，通过它他们可以找到建立直接连接的路径。如果是，则建立连接，否则使用 TURN 服务器作为中继，在端点之间交换信息。

    ICE 要求默认情况下应使用 STUN，因为 TURN 通信需要连续使用 TURN 服务器，连接不是对等的，需要使用更多的服务器资源。ICE 是由互联网工程任务组开发的 [RFC 8445](https://tools.ietf.org/html/rfc8445) 。

    该协议用于以下情况:

    *   会话发起协议
    *   互联网协议语音
    *   P2P 通信
    *   webrtc
    *   电信会议