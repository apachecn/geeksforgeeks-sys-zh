# 什么是分布式拒绝服务？

> 原文:[https://www . geesforgeks . org/what-is-DDOS distributed-拒绝服务/](https://www.geeksforgeeks.org/what-is-ddosdistributed-denial-of-service/)

**分布式拒绝服务(DDoS)** 是一种 DoS 攻击类型，其中多个被木马感染的系统瞄准特定系统，从而导致 DOS 攻击。分布式拒绝服务攻击使用多个服务器和互联网连接来淹没目标资源。DDoS 攻击是网络平台上最强大的武器之一。当你知道一个网站被关闭时，它通常意味着它已经成为 DDoS 攻击的受害者。这意味着黑客攻击了你的网站或个人电脑，强加了这些沉重的流量。因此，网站或电脑因超载而崩溃。

**DDoS 攻击的例子:**
2000 年，使用网名“Mafiaboy”的 15 岁男孩 Michael Calce 策划了第一次 DDoS 攻击。他侵入了不同大学的计算机网络。他用他们的服务器来操作

导致易贝和雅虎等多家网站瘫痪的 DDoS 攻击。

2016 年，Dyn 遭遇了大规模的 DDoS 攻击，导致网飞、PayPal、亚马逊和 GitHub 等主要网站和服务瘫痪。

**DDoS 攻击的类型:**
下面提到了各种类型的 DDoS 攻击:

1.  **体积攻击:**
    体积攻击是最常见的 DDoS 攻击形式。他们使用僵尸网络使网络或服务器过载，流量很大，但超出了网络处理流量的能力。这种攻击让目标承受了大量垃圾数据。这将导致网络带宽的损失，并可能导致完全拒绝服务。
2.  **Protocol Attacks:**
    TCP Connection Attacks exploit a vulnerability in the TCP connection sequence which is commonly referred to as the three-way handshake connection with the host and the server.

    工作说明如下。目标服务器收到以握手开始的请求。在这次攻击中，握手永远不会完成。这使得连接的端口繁忙，无法处理任何进一步的请求。与此同时，网络罪犯继续发送多个请求，淹没所有工作端口并关闭服务器。

3.  **Application Attacks:**
    Application layer attacks (Layer 7 attacks) target applications of the victim of in a slower fashion. Thus, they may initially appear as legitimate requests from users and the victim becomes unable to respond. These attacks targets the layer where a server generates web pages and responds to http requests.

    应用程序级攻击与针对应用程序的其他类型的 DDoS 攻击结合在一起，并伴随着网络和带宽。这些攻击具有威胁性，因为公司更难察觉。

4.  **碎片攻击:**
    网络犯罪分子利用数据报碎片化过程中的脆弱性，将 IP 数据报分成更小的数据包，通过网络传输，然后重新组装。在这种攻击中，伪造的数据包无法重组。

**DDoS 攻击是如何工作的:**
DDoS 攻击的逻辑非常简单，尽管攻击之间可以高度区分。网络连接由操作系统模型的不同层组成。各种类型的 DDoS 攻击集中在特定的层。

下面举例说明:

*   **第 3 层:网络层–**攻击被称为蓝精灵攻击、ICMP 泛洪和 IP/ICMP 碎片。
*   **第 4 层:传输层–**攻击包括 SYN 泛洪、UDP 泛洪和 TCP 连接耗尽。
*   **第 7 层:应用层–**HTTP 加密攻击。

**如何保护自己免受 DDoS 攻击:**

1.  **快速行动:**
    越早识别出 DDoS 攻击，抵抗伤害的速度就越快。公司应该提供 DDoS 服务或某种技术，以便尽快实现和处理繁重的流量。
2.  **配置防火墙和路由器:**
    防火墙和路由器的配置方式应该是拒绝虚假流量，你应该让你的路由器和防火墙更新最新的安全补丁。
3.  **考虑人工智能:**
    虽然目前高级防火墙和入侵检测系统的防御非常普遍，但人工智能正被用于开发新系统。
4.  **保护你的物联网设备:**
    为了防止你的设备成为僵尸网络的一部分，确保你的计算机有可信的安全软件是明智的。用最新的安全补丁更新它是很重要的。