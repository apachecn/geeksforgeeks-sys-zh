# 多拉是如何工作的？

> 原文:[https://www.geeksforgeeks.org/how-dora-works/](https://www.geeksforgeeks.org/how-dora-works/)

**动态主机配置协议(DHCP)** 使用了 DORA。动态主机配置协议是[应用层](https://www.geeksforgeeks.org/application-layer-in-osi-model/)的协议。它用于提供子网掩码、路由器地址、域名系统地址和供应商类别标识符。事实上，DHCP 为想要连接到网络的主机提供了一个自动的 IP 地址。

DORA 是 [DHCP](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) 使用的进程。DORA 有助于为主机或客户端机器提供一个 IP 地址。DORA 是服务器和客户端之间遵循一些步骤的过程。它从集中式服务器获取 IP 地址。它由四个阶段组成:

*   **Found**
*   **Provide**
*   **Request**
*   **Confirm**

现在让我们看看当 DHCP 客户端向 DHCP 服务器请求一个 IP 地址时会发生什么。让我们看看在这个过程中他们之间交换了什么消息。

**注意** : *在网络层，DHCP 消息总是被广播的。在数据链路层，也广播 DHCP 消息。*

## 步骤 1: DHCP 发现消息

这是 DORA 过程中的第一条消息，有助于找到网络的 DHCP 服务器。DHCP 客户端将通过发送 DHCP 发现消息来找到服务器。广播消息被发送到网络。由于 DHCP 客户端不知道服务器的 IP 地址，因此消息广播的目的 IP 是 255.255.255.255。并且源 IP 将是 0.0.0.0，因为客户端没有任何 IP 地址。这里，数据链路层和网络层中的 DHCP 发现消息总是被广播。

```
Source IP address: 0.0.0.0  
Destination IP address: 255.255.255.255
Source MAC address: MAC address of DHCP clients
Destination MAC address: FF:FF:FF:FF:FF:FF
```

## 步骤 2: DHCP 提供消息

DHCP 服务器接收发现消息，并用 DHCP 提供请求重放 DHCP 客户端。服务器发送带有填充信息的 DHCP 提供消息。它包含主机可以使用的 IP 地址和持续时间的信息。这里的目的 IP 地址将是 255.255.255.255，因为 DHCP 客户端仍然没有它的 IP 地址。但是这个 DHCP 提供消息在网络层广播，在数据链路层单播。

```
Source IP address: IP Address of DHCP Server
Destination IP address: 255.255.255.255
Source MAC address: MAC address of DHCP Server
Destination MAC address: MAC address of DHCP clients
```

## 第三步:DHCP 请求消息

当 DHCP 客户端从服务器接收到 DHCP 提供消息时，它会向服务器发送请求消息。此消息告诉服务器它接受服务器给出的 IP 地址。这里的目的地地址将是 255.255.255.255 意味着它再次被广播。其原因是网络中可能有许多 DHCP 服务器，因此客户端可能会收到多个 offer 消息，它会接受首先到达他的请求，并发送广播消息以消除其他 DHCP 服务器。这里的源 IP 地址将是 0.0.0.0，因为 DHCP 服务器尚未为客户端分配 IP 地址。DHCP 请求消息也是广播消息。

```
Source IP address: 0.0.0.0
Destination IP address: 255.255.255.255
Source MAC address: MAC address of DHCP clients
Destination MAC address: MAC address of DHCP server
```

## 步骤 4: DHCP 确认消息

这是 DORA 过程中的最后一步或最后一条消息。当 DHCP 服务器从 DHCP 客户端收到请求消息时，它会向客户端发送确认消息。此消息将包含服务器分配给客户端的 IP 地址和子网掩码。源 IP 地址将是服务器的 IP 地址。这将再次广播消息，因为目的 IP 地址是 255.255.255.255。但是在数据链路层的情况下是单播。

```
Source IP address: IP Address of DHCP Server
Destination IP address: 255.255.255.255
Source MAC address: MAC address of DHCP server
Destination MAC address: MAC address of DHCP clients
```

所以，这是多拉进程，当这个进程结束时，DHCP 客户端将获得它的 IP 地址。这里需要记住的是

*   **DHCP discovery message** -broadcast
*   **DHCP offer message** -network layer broadcast and data link layer unicast
*   **DHCP request message** -Network layer broadcast and data link layer unicast
*   **DHCP acknowledge message** -Network layer broadcast and data link layer unicast