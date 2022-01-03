# IP 地址的结构和类型

> 原文:[https://www . geesforgeks . org/IP 地址的结构和类型/](https://www.geeksforgeeks.org/structure-and-types-of-ip-address/)

一个 [IP 地址](https://www.geeksforgeeks.org/difference-between-private-and-public-ip-addresses/)代表一个互联网协议地址。通过网络识别设备的唯一地址。它几乎就像是一套管理通过互联网或本地网络发送的数据结构的规则。IP 地址有助于互联网区分不同的路由器、计算机和网站。它作为特定网络中的特定机器标识符，有助于改善源和目标之间的视觉通信。

**IP 地址结构:**
IP 地址显示为一组四位数——默认地址可能是 192.158.1.38。集合中的每个数字的范围可以从 0 到 255。因此，总的 IP 地址范围从 0.0.0.0 到 255.255.255.255。

```
IP address is basically divided into two parts: X1\. X2\. X3\. X4
1\. [X1\. X2\. X3] is the Network ID
2\. [X4] is the Host ID
```

1.  [**网络 ID**](https://www.geeksforgeeks.org/finding-network-id-of-a-subnet-using-subnet-mask/)**–**
    是左侧 IP 地址中标识设备所在具体网络的部分。在普通家庭网络中，设备的 IP 地址为 192.168.1.32，地址的 192.168.1 部分将是网络标识。按照惯例，最后一部分填写不为零，所以我们可以说设备的网络 ID 是 192.168.1.0。
2.  [**【主机 ID】**](https://www.geeksforgeeks.org/ip-addressing-gq/)**–**
    主机 ID 是网络 ID 没有取的 IP 地址的一部分。识别网络中的特定设备(在 TCP / IP 世界中，我们称设备为“主机”)。继续我们的 IP 地址 192.168.1.32 的例子，主机标识将是 32-192 . 168 . 1 . 0 网络上唯一的主机标识。

**IP 地址类型:**
有 4 种类型的 IP 地址——公共、私有、固定和动态。其中，公有地址和私有地址都是从它们的本地网络位置派生出来的，应该在网络内部使用，而公有 IP 是离线使用的。

1.  [**公共 IP 地址**](https://www.geeksforgeeks.org/difference-between-private-and-public-ip-addresses/)**–**
    公共 IP 地址是互联网协议地址，由各种服务器/设备加密。这时，您将这些设备与互联网连接起来。这是我们在主页上显示的同一个 IP 地址。那么为什么是第二页呢？嗯，不是所有的人都讲知识产权语言。我们希望让每个人都能尽可能容易地获得他们需要的信息。有些人甚至称之为他们的外部 IP 地址。公共互联网协议地址是通过互联网访问的互联网协议地址。与用于将邮件投递到您家中的邮政地址一样，公共互联网协议地址是分配给计算机设备的不同国际互联网协议地址。网络服务器、电子邮件服务器和任何可以直接访问互联网的服务器设备都是那些将输入公共互联网协议地址的设备。互联网地址协议在全球范围内都是独一无二的，并且只随唯一的设备提供。
2.  [**私有 IP 地址**](https://www.geeksforgeeks.org/what-is-apipa-automatic-private-ip-addressing/)**–**
    连接到您的互联网网络的所有设备都有私有 IP 地址。这包括电脑、智能手机和平板电脑，但也包括任何支持蓝牙的设备，如扬声器、打印机或智能电视。随着物联网的不断发展，你家里拥有的私有 IP 地址数量很可能会增加。你的路由器需要一种方法来分别识别这些东西，大多数东西都需要一种方法来相互了解。因此，您的路由器会生成私有 IP 地址，这些地址是分隔网络的每个设备的唯一标识符。
3.  [**静态 IP 地址**](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-static-ip/)**–**
    静态 IP 地址是无效的 IP 地址。反之，动态 IP 地址将由[动态主机配置协议(DHCP)服务器](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/)提供，可以更改。静态 IP 地址不会更改，但可以作为正常网络管理的一部分进行更改。
    静态 IP 地址不兼容，给定一次，多年不变。这种类型的 IP 也有助于您获得有关设备的更多信息。
4.  [**动态 IP 地址**](https://www.geeksforgeeks.org/difference-between-static-and-dynamic-ip-address/)**–**
    表示不断变化。动态 IP 地址会不时变化，并且不总是相同的。如果你有一个直播电缆或 DSL 服务，你可能有一个强大的 IP 地址。互联网服务提供商(向客户提供动态 IP 地址，因为它们太贵了。您的 IP 地址不是一个永久的 IP 地址，而是从地址池中取出并分配给您。几天、几周，有时甚至几个月后，这个号码被放回湖中，并被赋予一个新的号码。大多数互联网服务提供商不会向居住在那里的客户提供静态 IP 地址，当他们提供静态 IP 地址时，通常会更贵。动态 IP 地址很烦人，但是有了合适的软件，你可以轻松免费地导航。

**网站 IP 地址类型:**
网站 IP 地址有两种类型——专用 IP 地址和共享 IP 地址。让我们讨论一下这两个问题。

1.  [**专用 IP 地址**](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-dedicated-ip-addresses/)**–**
    专用 IP 地址是每个网站独有的地址。该地址没有被任何其他域使用。专用的 IP 地址在许多方面都是有益的。当流量负载较高时，它提供更高的速度，并带来更高的安全性。但是与共享 IP 相比，专用 IP 成本较高。
2.  [**共享 IP 地址**](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)**–**
    共享 IP 地址不是唯一的。它在多个域之间共享。对于大多数用户来说，共享的 IP 地址就足够了，因为常见的配置不需要专用的 IP。

**基于运营特征的 IP 地址分类:**
根据运营特征，IP 地址分类如下:

1.  [**广播寻址**](https://www.geeksforgeeks.org/difference-between-unicast-broadcast-and-multicast-in-computer-network/)**–**
    术语“广播”是指通过网络传输音频或视频。广播数据包会同时发送给本地网络的所有用户。他们不必被明确地命名为接收者。网络用户可以打开数据包，然后解释信息、执行指令或丢弃信息。此服务在 IPv4 中可用。广播常用的 IP 地址是 255.255.255.255
2.  [**【单播寻址】**](https://www.geeksforgeeks.org/internet-protocol-version-6-ipv6/)**–**
    该地址标识网络上的唯一节点。单播只不过是从网络中的一点到另一点的一对一数据传输。这是最常见的 IP 寻址形式。这种方法可以用于发送和接收数据。它有 IPv4 和 IPv6 版本。
3.  [**组播 IP 地址**](https://www.geeksforgeeks.org/difference-between-unicast-and-multicast/)**–**
    这些 IP 地址主要帮助建立一对多的通信。多播 IP 路由协议用于向多个接收者分发数据。D 类地址(224.0.0.0 到 239.255.255.255)定义了多播组。
4.  [**【选播寻址】**](https://www.geeksforgeeks.org/introduction-of-anycast-routing/)**–**
    在选播寻址数据时，数据包不会传输到网络上的所有接收器。当数据包被分配到任播地址时，它会被传送到具有该任播地址的最近接口。