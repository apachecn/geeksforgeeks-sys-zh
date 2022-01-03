# DAS 和 SAN 的区别

> 原文:[https://www . geesforgeks . org/das 和 san 的区别/](https://www.geeksforgeeks.org/difference-between-das-and-san/)

**1。直连存储(DAS) :**
永久连接到台式计算机的存储设备。DAS 适用于单个用户(连接到计算机的硬盘)。它非常适合中小型企业，在那里可以以较低的启动成本配置足够的存储量。DAS 存储模块将是一个独立的相邻机柜，包含额外的磁盘驱动器。

直接连接存储组件(DAS)–

```
1. Storage devices
2. Cables
3. Disk Array
4. Protocol
5. Storage protocols: ATA, SCSI, SAS, SASA, FC 
```

**2。存储区域网络(SAN) :**
SAN 通过网络在数据块级别发挥作用。可以使用 ISCSI 或光纤通道访问的存储。适合关键业务应用和需要高性能的应用。基于存储区域网络的存储解决方案的主要优势是能够将存储阵列共享给多台服务器。这允许您根据需要配置存储容量，通常由专门的存储区域网络管理员进行。更高级别的性能吞吐量是 SAN 环境中的典型特征，并且数据通过冗余磁盘控制器和驱动器高度可用。

存储区域网络的组件-

```
1. Node ports
2. Cables
3. Interconnect device such as: Hubs, switches, directors
4. Storage arrays
5. SAN management Software 
```

**DAS 和 SAN 的区别:**

<center>

| SR.NO | 这是什么 | 存储区域网 |
| --- | --- | --- |
| 1. | DAS 代表直接存取存储。 | 存储区域网络代表存储区域网络。 |
| 2. | 对于备份和恢复，使用扇区。 | 对于备份和恢复，使用逐块拷贝技术。 |
| 3. | 很容易安装。 | 很难安装。 |
| 4. | 这并不复杂。 | 这很复杂。 |
| 5. | 它不太贵 | 它更贵。 |
| 6. | 数据传输采用 IDE/SCSI。 | 数据传输采用光纤通道。 |
| 7. | 它的字节容量是 10^9. | 它的字节容量大于 10^12. |
| 8. | 它不允许在不同的操作系统上共享文件。 | 它允许在不同的操作系统上共享文件。 |

</center>