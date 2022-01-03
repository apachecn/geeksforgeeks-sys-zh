# 存储区域网络

> 原文:[https://www.geeksforgeeks.org/storage-area-networks/](https://www.geeksforgeeks.org/storage-area-networks/)

随着电子商务的快速增长，基本上集成了整个组织的应用程序数据的企业资源规划系统，以及保存历史聚合信息的数据仓库，对存储的需求必须大幅上升。对于当今的互联网驱动型组织来说，有必要从面向静态固定数据中心的运营转向更加灵活和动态的基础架构，以满足其信息处理需求。RAID 系统的许多用户无法有效利用容量，因为它必须附加到一个名为**存储区域网络**的概念上。

在**存储区域网络**中，在线存储外围设备被配置为高速网络上的节点，并且可以以非常灵活的方式从服务器连接和断开连接。许多公司作为存储区域网络提供商出现，并提供自己的专有拓扑。它们基本上允许将存储系统放置在离服务器较远的位置，并提供不同的性能和连接选项。

现有的存储管理应用程序可以使用封装传统 SCSI 协议的光纤通道网络移植到存储区域网络配置中。因此，连接到存储区域网络的设备显示为 SCSI 设备。存储区域网络的当前体系结构选择包括以下内容:

1.  Point-to-point connection between storage system and server through Fibre Channel.
2.  Use Fibre Channel switches to connect multiple RAID systems, tape libraries, etc. to the server.
3.  Use Fibre Channel hubs and switches to connect servers and storage systems with different configurations.

**声称的主要优势如下:**

1.  With the help of Fibre Channel hubs and switches, many-to-many connections between servers and storage devices can be flexibly realized.
2.  With proper fiber optic cable, the distance between server and storage system can reach 10 kilometers.
3.  Better isolation capability, allowing new servers and peripherals to be added without interruption.

存储区域网络的使用正在迅速增加，但它仍然面临许多问题，例如结合来自多个供应商的存储选项，以及处理不断发展的存储管理软件和硬件标准。大多数大公司都在评估存储区域网络作为数据库存储的可行选择。