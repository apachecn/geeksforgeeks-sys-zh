# 【FAT32 和 NTFS 的区别

> 原文:[https://www . geesforgeks . org/difference-fat 32 和-ntfs/](https://www.geeksforgeeks.org/difference-between-fat32-and-ntfs/)

文件系统提供了组织驱动器的方式。其主要操作是指定数据在驱动器上的存储方式以及附加到文件的信息类型，如文件名、权限和其他属性。Windows 支持三种不同的文件系统，即 [FAT32、exFAT 和 NTFS](https://www.geeksforgeeks.org/difference-fat32-exfat-ntfs-file-system/) 。这些文件系统的转换如下:

*   8 位 FAT(原始 8 位 FAT)
*   FAT12 (8 位文件分配表)
*   FAT16(初始 16 位文件分配表(含 16 位扇区条目))
*   FAT16B(最终 16 位文件分配表(含 32 位扇区条目))
*   FAT32(文件分配表-32)
*   可扩展文件分配表
*   新技术文件系统

FAT32 和 NTFS 是操作系统中使用的文件系统类型。

**1。FAT32 :**
FAT32 代表文件分配表。FAT32 是以前文件系统的扩展，在以前的文件系统中，数据以 32 位的块存储。FAT32 是 FAT16 的升级版本，旨在克服 FAT16 的限制，并增加对更大媒体的支持。在 Windows XP 之前，FAT32 一直用于 Windows 95 等旧版本的操作系统。

**FAT32 的优势–**

*   FAT32 在 200 MB 的分区下高效工作。
*   FAT32 提供了与不同操作系统的兼容性。
*   FAT32 经常被用作多引导系统上的主分区。

**FAT32 的缺点–**

*   FAT32 中大小超过 200 MB 的分区会降低性能。
*   由于缺乏加密，FAT32 是不安全的。
*   FAT32 容易碎裂。

**2。**
NTFS 代表新技术文件系统。它于 1993 年首次推出，用于较新版本的操作系统，如 Windows NT 和 2000 以及更高版本的 Windows。NTFS 是一个更健壮、更高性能的日志文件系统，具有多用户访问控制、ACL 和许多其他功能，使其适合与具有保护功能的操作系统一起工作。NTFS 包括数据恢复、多数据流、容错、安全性、扩展文件大小和文件系统、UNICODE 名称等特性。由于其数据结构开销，exFAT 用于 NTFS 不可行的地方，但是需要比标准 FAT32 文件系统更大的文件大小限制。

**NTFS 的优势–**

*   NTFS 是高度安全的，因为它通过实施加密文件系统(EFS)来防止对文件内容的未授权访问。
*   即使在大小超过 400 兆的分区中，NTFS 也表现良好。
*   NTFS 不太容易出现碎片。

**NTFS 的缺点–**

*   不广泛支持 NTFS。
*   在 400 兆的分区下，NTFS 文件系统的性能会下降。

**FAT32 和 NTFS 的区别:**

<center>

| 特征 | FAT32 | Windows NT 文件系统(NT File System) |
| 结构 | 简单的 | 复杂的 |
| 文件名中支持的最大字符数 | Eighty-three | Two hundred and fifty-five |
| 最大文件大小 | 4GB | 16TB |
| 加密 | 未加密 | 使用加密文件系统加密(EFS) |
| 安全 | 仅网络类型 | 本地和网络类型 |
| 容错 | 没有容错规定 | 存在自动故障排除 |
| 与操作系统的兼容性 | Windows 95/98/2000/2003/XP | Windows NT/2K/XP/Vista/7/8/10，macOS X，Linux |
| 压缩 | 不允许压缩 | 支持文件压缩 |
| 访问速度 | 低的 | 相对高于其他文件系统 |
| 用户级磁盘空间 | 不在场 | 礼物 |
| 转换 | 允许 | 不允许 |

</center>