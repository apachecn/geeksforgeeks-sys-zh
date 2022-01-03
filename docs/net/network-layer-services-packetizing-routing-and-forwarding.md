# 网络层服务-打包、路由和转发

> 原文:[https://www . geesforgeks . org/网络层-服务-打包-路由和转发/](https://www.geeksforgeeks.org/network-layer-services-packetizing-routing-and-forwarding/)

**网络层**是计算机网络 [OSI 模型](https://www.geeksforgeeks.org/layers-of-osi-model/)中的第三层。它的主要功能是将网络数据包从源传输到目的地。它涉及源主机和目标主机。在源端，它接受来自传输层的数据包，将其封装在数据报中，然后将数据包传送到数据链路层，以便进一步发送到接收器。在目的地，数据报被解封，数据包被提取并传送到相应的传输层。

**特征:**

1.  网络层的主要职责是将数据包从源端传送到目的端，而不改变或使用它。
2.  如果数据包太大而无法传递，它们就会被分段，即分解成更小的数据包。
3.  它决定了数据包在网络中可用的多个根中从源传输到目的地的根(也称为路由)。
4.  源地址和目的地址被添加到网络层内部的数据包中。

网络层协议提供的**服务**如下:

1.  [**Packetizing**](https://www.geeksforgeeks.org/fragmentation-network-layer/) **–** 
    The process of encapsulating the data received from upper layers of the network(also called as payload) in a network layer packet at the source and decapsulating the payload from the network layer packet at the destination is known as packetizing. 

    源主机将包含源地址和目的地址以及网络层协议所需的一些其他相关信息的报头添加到从上层协议接收的有效负载中，并将数据包传送到数据链路层。

    目的主机从其数据链路层接收网络层数据包，对数据包进行解封装，并将有效负载传送到相应的上层协议。路径中的路由器不允许更改源地址或目的地址。除非需要分段，否则不允许路径中的路由器对收到的数据包进行解封装。

2.  [**Routing**](https://www.geeksforgeeks.org/types-of-routing/) **and Forwarding –** 
    These are two other services offered by the network layer. In a network, there are a number of routes available from the source to the destination. The network layer specifies has some strategies which find out the best possible route. This process is referred to as routing. There are a number of routing protocols which are used in this process and they should be run to help the routers coordinate with each other and help in establishing communication throughout the network. 

    转发被简单地定义为当一个数据包到达它的一个接口时，每个路由器所采取的动作。当路由器从其附属网络之一接收到数据包时，它需要将数据包转发到另一个附属网络([单播路由](https://www.geeksforgeeks.org/unicast-routing-link-state-routing/))或一些附属网络(在组播路由的情况下)。

预计来自网络层的其他一些**服务有:**

1.  [**【差错控制】**](https://www.geeksforgeeks.org/error-control-in-tcp/)**–**
    虽然可以在网络层实现，但通常不首选，因为一个网络层的数据包可能会在每台路由器上碎片化，这使得网络层的差错校验效率低下。

2.  [**Flow Control**](https://www.geeksforgeeks.org/difference-between-flow-control-and-congestion-control/) **–** 
    It regulates the amount of data a source can send without overloading the receiver. If the source produces a data at a very faster rate than the receiver can consume it, the receiver will be overloaded with data. To control the flow of data, the receiver should send a feedback to the sender to inform the latter that it is overloaded with data. 

    网络层的设计缺乏流量控制。它不直接提供任何流量控制。数据报由发送方在准备好的时候发送，而不考虑接收方的准备情况。

3.  [**【拥塞控制】**](https://www.geeksforgeeks.org/congestion-control-in-computer-networks/)**–**
    当源发送的数据报数量超出网络或路由器的容量时，就会发生拥塞。这是网络层协议的另一个问题。如果拥塞持续，有时可能会出现系统崩溃且没有数据报被传送的情况。虽然拥塞控制是在网络层间接实现的，但在网络层仍然缺乏拥塞控制。

**网络层服务的优势:**

*   网络层的分组化服务为数据包的传输提供了便利。
*   分组化还消除了数据通信系统中的单点故障。
*   网络层的路由器通过创建冲突域和广播域来减少网络流量。
*   在转发的帮助下，数据包在网络中从一个地方传输到另一个地方。

**网络层服务的缺点:**

*   网络层的设计缺乏流量控制。
*   由于网络中存在太多超出网络或路由器容量的数据报，有时会发生拥塞。因此，一些路由器可能会丢弃一些数据报，一些重要的信息可能会丢失。
*   虽然在网络层存在间接的错误控制，但是缺乏适当的错误控制机制，因为由于碎片数据分组的存在，错误控制变得难以实现。