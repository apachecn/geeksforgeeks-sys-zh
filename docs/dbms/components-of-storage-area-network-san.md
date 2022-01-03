# 存储区域网络组件

> 原文:[https://www . geesforgeks . org/存储区域网络组件-san/](https://www.geeksforgeeks.org/components-of-storage-area-network-san/)

[存储区域网络](https://www.geeksforgeeks.org/storage-area-networks/)的组件包括 3 个基本组件:

```
(a). Server 
(b). Network Infrastructure
(c). Storage
```

上述元素被分为以下元素，

```
(1). Node port
(2). Cables
(3). Interconnection Devices
(4). Storage Array, and
(5). SAN Management Software 
```

这些解释如下。

**1。节点端口:**
在光纤通道中，

*   主持
*   储存；储备
*   磁带库被称为**节点**

节点由用于在其他节点之间传输的端口组成。端口在**全双工**数据传输模式下运行，具有发送(Tx)和接收(Rx)链路。

**2。电缆:**
SAN 实现光纤布线。铜缆用于短距离连接，光缆用于长距离连接。
光缆有 2 种:多模光纤和单模光纤如下。

1.  **Multi-mode fiber:**
    Also called MMF, as it carries multiple rays of light projected at different angles simultaneously onto the core of the cable. In MMF transmission, light beam travelling inside the cable tend to disperse and collide. This collision, weakens the signal strength after it travels certain distance, and it is called **modal dispersion**.

    MMF 电缆用于 500 米的距离，因为模式色散会导致信号衰减。

2.  **单模光纤:**
    也叫 SMF，因为它携带一束光通过光纤的纤芯。电缆中的小芯线减少了模式色散。由于衰减较小，SMF 电缆可用于长达 10 公里的距离。SMF 比 MMF 贵。

除了这些电缆，标准连接器(SC)和朗讯连接器(LC)是常用的光纤电缆，数据传输速度分别高达 1 Gbps 和 4 Gbps。小型可插拔(SFP)是一种用于光通信的光收发器，传输速度高达 10 Gbps。

**3。**互连设备:
SAN 中常用的互连设备有:

1.  中心
2.  开关和
3.  导演

**集线器**是光纤电缆实现中使用的通信设备。它们以环形或星形拓扑连接节点。
**交换机**比集线器更智能。它们直接将数据从一个端口路由到另一个端口。它们价格便宜，性能优于集线器。
**控制器**比交换机大，用于数据中心实施。控制器比交换机具有更高的容错能力和更高的端口数量。

**4。存储阵列:**

磁盘阵列也称为存储阵列，是一种用于基于数据块的存储、基于文件的存储或对象存储的数据存储系统。该术语用于描述包含旋转硬盘驱动器或固态驱动器的专用存储硬件。

存储区域网络的基本目的是为主机提供对存储资源的访问。存储区域网络存储实施提供:

*   高可用性和冗余性，
*   提高性能，
*   业务连续性和
*   多主机连接。

**5。存储区域网络管理软件:**
该软件管理主机、互连设备和存储阵列之间的接口。它包括存储设备、交换机的映射和存储区域网络的逻辑分区等关键管理功能，称为**分区**。它还管理存储区域网络的重要组件，如存储设备和互连设备。