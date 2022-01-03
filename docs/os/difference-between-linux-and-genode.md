# 【Linux 和 Genode 的区别

> 原文:[https://www . geeksforgeeks . org/Linux 和 genode 的区别/](https://www.geeksforgeeks.org/difference-between-linux-and-genode/)

**1。 [Linux](https://www.geeksforgeeks.org/introduction-to-linux-operating-system/) :**
Linux 是由 Linus Torvalds 开发的一组开源类 Unix 操作系统。它是 Linux 发行版的打包版本。一些最常用的 Linux 发行版是 Debian、Fedora 和 Ubuntu。基本上是用 C 语言和汇编语言写的。Linux 使用的内核是 Monolithic 内核。Linux 发行版的目标系统是云计算、嵌入式系统、移动设备、个人电脑、服务器、大型机和超级计算机。Linux 的第一个版本于 1991 年推出。用于个人计算机的最新版本的 Linux 是 5.6(内核)。

**2。Genode :**
Genode 是由 Genode Labs 提供的免费开源操作系统。它由一个微内核抽象层和一组用户空间组件组成。它可以用作个人计算机操作系统的基础，也可以用作客户操作系统的虚拟机监视器。它主要是为台式机、嵌入式系统和服务器设计的。Genode 的第一个版本于 2008 年推出。Genode 的最新稳定版本是 19.05。

**Linux 和 Genode 的区别:**

<center>

| Linux 操作系统 | 基因组 |
| --- | --- |
| 它是由**莱纳斯·托瓦尔兹**开发的。 | 它是由 **Genode 实验室**开发的。 |
| 它于 1991 年推出。 | 它于 2008 年推出。 |
| 它的目标系统类型是嵌入式系统、移动设备、个人计算机、服务器、大型计算机和超级计算机。 | 它的目标系统类型是台式机、嵌入式系统和服务器。 |
| Linux 支持的计算机架构有 IA-32、x86-64、ARM、PowerPC 和 SPARC。 | Genode 支持的计算机架构有 ARM、RISC-V、IA-32 和 x86-64。 |
| Linux 中使用的内核是 Monolithic。 | 它的内核类型是微内核或单片内核。 |
| 它的包管理依赖于分发。 | 它有自定义包管理。 |
| 它的原生 API 是 LINUX/POSIX。 | 它的本土原料药是 Genode。 |
| 它有 GNU GPLv2(内核)的首选许可证。 | 它拥有 AGPL 的优先许可。 |
| 它的更新管理依赖于分发。 | 它没有更新管理。 |
| 它有默认的图形用户界面“开”。 | 它没有默认的图形用户界面“开”。 |
| Linux 支持的文件系统有 ext2、ext3、ext4、btrfs、ReiserFS、FAT、ISO 9660、UDF 和 NFS。 | Genode 支持的文件系统有 ext2、ext3、FAT32 和 ISO9660。 |
| 通过其子系统支持的非本机 API 有 Mono、Java、Win16 和 Win32。 | 通过其子系统支持的非本地应用编程接口有 POSIX、Qt、SDL 和 MirageOS。 |

</center>