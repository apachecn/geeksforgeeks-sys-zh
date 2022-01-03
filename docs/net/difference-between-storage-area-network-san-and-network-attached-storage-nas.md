# 存储区域网络(SAN)和网络连接存储(NAS)的区别

> 原文:[https://www . geesforgeks . org/存储区域网络 san 和网络连接存储 nas 之间的区别/](https://www.geeksforgeeks.org/difference-between-storage-area-network-san-and-network-attached-storage-nas/)

**存储区域网络(SAN):**
存储区域网络(SAN)用于在服务器和存储设备之间传输数据的光纤通道和交换机。在存储区域网络中，数据由磁盘块标识。存储区域网络中使用的协议有:SCSI、SATA 等。

存储区域网络的组件:

```
1. Node ports
2. Cables
3. Interconnect device such as: Hubs, switches, directors
4. Storage arrays
5. SAN management Software 
```

**网络连接存储(NAS):**
在网络连接存储(NAS)中，数据由文件名和字节偏移量来标识。在网络连接存储中，文件系统由中央处理器和内存等前端单元管理。在这种备份和恢复中，使用文件代替逐块复制技术。

网络连接存储的组件:

```
1. Head unit: CPU, Memory
2. Network Interface Card (NIC)
3. Optimized operating system
4. Protocols
5. Storage protocols: ATA, SCSI,FC 
```

**存储区域网络(SAN)和网络连接存储(NAS)的区别:**

| S.NO | 存储区域网 | 美国国家科学院（National Academy of Sciences） |
| 1. | 存储区域网络代表存储区域网络。 | 网络连接存储代表网络连接存储。 |
| 2. | 在存储区域网络中，数据由磁盘块标识。 | 在 NAS(网络连接存储)中，数据由文件名和字节偏移量来标识。 |
| 3. | 在存储区域网络中，文件系统由服务器管理。 | 在 NAS(网络连接存储)中，文件系统由前端单元管理。 |
| 4. | 存储区域网络成本更高。 | 网络连接存储比存储区域网络便宜。 |
| 5. | 存储区域网络比网络连接存储更复杂。 | 网络连接存储没有存储区域网络复杂。 |
| 6. | 存储区域网络中使用的协议有:SCSI、SATA 等。 | 网络连接存储中使用的协议有:文件服务器、CIFS 等。 |
| 7. | 对于存储区域网络中的备份和恢复，使用逐块拷贝技术。 | 对于网络连接存储中的备份和恢复，使用文件。 |
| 8. | 存储区域网络在高速交通系统中提供高性能。 | 而 NAS 不适合高速流量的环境。 |
| 9. | 存储区域网络需要更多的时间和精力来组织和控制。 | 网络连接存储易于管理，并为组织和控制提供了一个简单的界面。 |
| 10. | SAN 需要 TCP/IP 网络，并且依赖于局域网。 | 网络连接存储不依赖局域网，使用高速光纤通道网络。 |