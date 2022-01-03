# DAS 和 NAS 的区别

> 原文:[https://www . geesforgeks . org/das 和 nas 的区别/](https://www.geeksforgeeks.org/difference-between-das-and-nas/)

**1。直连存储(DAS) :**
永久连接到台式计算机的存储设备。DAS 适用于单个用户(连接到计算机的硬盘)。DAS 非常适合中小型企业，在那里可以以较低的启动成本配置足够的存储量。DAS 存储模块将是一个独立的相邻机柜，包含额外的磁盘驱动器。

直接连接存储组件(DAS)–

```
1. Storage devices
2. Cables
3. Disk Array
4. Protocol
5. Storage protocols: ATA, SCSI, SAS, SASA, FC 
```

**2。网络连接存储(NAS) :**
该存储设备连接在局域网上，用于在连接到局域网的不同用户之间共享数据。用户可以通过网络访问文件级别的信息，而不是在扇区级别访问数据。该网络连接存储系统有自己的文件系统，该文件系统一旦设置为网络连接存储的正确配置，就不依赖于与之连接的计算机的操作系统。这种类型的网络需要一种介质来连接多台计算机。NFS、法新社或 CIFS 等文件共享协议提供对网络中文件的访问。

网络连接存储组件–

```
1. Head unit: CPU, Memory
2. Network Interface Card (NIC)
3. Optimized operating system
4. Protocols
5. Storage protocols: ATA, SCSI, FC  
```

**DAS 和 NAS 的区别:**

<center>

| SR.NO | 这是什么 | 美国国家科学院（National Academy of Sciences） |
| --- | --- | --- |
| 1. | DAS 代表直接存取存储。 | 网络连接存储代表网络连接存储。 |
| 2. | 对于备份和恢复，使用扇区。 | 对于备份和恢复，使用文件。 |
| 3. | 很容易安装。 | 安装适中。 |
| 4. | DAS 并不复杂。 | NAS 比 DAS 复杂。 |
| 5. | 它不太贵。 | 它比 DAS 贵。 |
| 6. | 数据传输采用 IDE/SCSI。 | 数据传输采用 TCP/IP，以太网。 |
| 7. | 它的字节容量是 10^9. | 它的字节容量是从 10^9 到 10^12. |
| 8. | 它不允许在不同的操作系统上共享文件。 | 它允许在不同的操作系统上共享文件。 |

</center>