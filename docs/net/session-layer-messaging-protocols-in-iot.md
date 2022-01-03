# 物联网中的会话层消息协议

> 原文:[https://www . geesforgeks . org/session-layer-messaging-protocol-in-IOT/](https://www.geeksforgeeks.org/session-layer-messaging-protocols-in-iot/)

先决条件–[物联网简介](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)
会话层通过控制发送方和接收方之间的数据来管理网络两个端点之间的连接，其中会话层协议负责物联网生态系统中数据的实际传输。这就是为什么这些会话层协议被称为物联网**消息协议**或有时被称为物联网**数据协议。**大多数物联网应用使用 TCP 和 UDP 进行传输，这些消息协议可以通过 [TCP 或 UDP](https://www.geeksforgeeks.org/differences-between-tcp-and-udp/) 运行。

不同的标准化组织有不同类型的消息传递协议，根据它们的实现方式，它们被使用。以下是物联网生态系统中使用的一些流行的物联网消息协议。

1.  **Message Queue Telemetry Transport (MQTT) :**
    MQTT is most widely adopted M2M(Machine to Machine) messaging protocol which was introduced by IBM in 1999\. It uses a Publisher-Subscriber mechanism to operate means Publishers are lightweight sensors that collect data and connect to a mediation layer i.e to a broker(or dealer) to send their data. Then subscribers are applications that collect required sensory data from broker. This mechanism minimizes payload. It is mainly used when a huge network of low power small devices or where IoT devices may have limited bandwidth and need to be monitored or managed via Internet.

2.  **Advanced Message Queuing Protocol (AMQP) :**
    AMQP is an open standard session layer protocol useful for sending transnational messages that’s why mainly used in financial industry. It runs over TCP (Transmission Control Protocol) or UDP (User Datagram Protocol) which is nearly similar to that of MQTT. But only difference is that Broker(Dealer) contains Exchange and Queues as a result it is focused on not losing messages. The exchange receives messages from publishers and distributes them to respective queues. Different subscribers collect topic wise sensory data from respective topic queues.
3.  **Constrained Application Protocol (CoAP) :**
    CoAP is a session layer protocol that uses RESTful architecture which is a standard interface between HTTP clients and servers. It uses UDP (User Datagram Protocol) protocol for lightweight implementation so it is based on two sublayers i.e messaging and request/response for interaction. This protocol is designed to address IoT systems based on HTTP protocols. So, CoAP utilizes all HTTP methods like GET, PUT, PUSH, DELETE for message transmission, and accessing resources. It is a specialized web transfer protocol which uses constrained nodes/devices on same constrained networks in Internet of Things.
4.  **Secure Message Queue Telemetry Transport (SMQTT) :**
    SMQTT works as an extension to MQTT protocol. It is based on an encryption messaging mechanism that’s why it provides a secure messaging standard. In this protocol, subscriber sends encrypted messages to all nodes and nodes receive encrypted message and use message after decryption. The encryption and decryption activities are carried out by using master key.

    该协议遵循四个主要阶段，即设置、加密、发布、解密。

    1.  在安装程序中，发布者和订阅者都在代理附近注册自己并获取主密钥。
    2.  在加密阶段，代理对发布的消息进行加密。
    3.  在发布阶段，代理向订阅者提供加密数据。
    4.  在解密阶段，即最后一个阶段，用户使用该主密钥对数据/消息进行解密。
5.  **数据分发服务(DDS) :**
    DDS 是另一种发布-订阅协议，但它不同于将它们连接到服务器的 MQTT，但这里 DDS 协议是一种无代理架构，这就是为什么它是一种比 MQTT 更高速、更高性能的协议，因为它不依赖于任何中间系统。它是由对象管理组(OMG)为设备间通信而设计的。该协议有两个基本子层，即以数据为中心的发布-订阅层(DCPS)和数据本地重建层(DLRL)。DCPS 层负责向用户传递消息，DLRL 层负责在应用层简单集成 DDS，但这是可选的。