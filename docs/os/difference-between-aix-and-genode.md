# AIX 和 Genode 的区别

> 原文:[https://www . geesforgeks . org/difference-AIX-and-genode/](https://www.geeksforgeeks.org/difference-between-aix-and-genode/)

**1。AIX :**
AIX 是 IBM 提供的一系列专有操作系统。AIX 代表高级交互执行。最初它是为 IBM RT PC RISC 工作站设计的，后来它被用于各种硬件平台，如 IBM RS/6000 系列、基于 PowerPC 的系统、System-370 大型机、PS-2 个人计算机和苹果网络服务器。它是已通过开放集团 UNIX 03 标准认证的五个商业操作系统之一。AIX 的第一个版本于 1986 年推出。AIX 的最新稳定版本是 7.2。

**2。Genode :**
Genode 是由 Genode Labs 提供的免费开源操作系统。它由一个微内核抽象层和一组用户空间组件组成。它可以用作个人计算机操作系统的基础，也可以用作客户操作系统的虚拟机监视器。它主要是为台式机、嵌入式系统和服务器设计的。Genode 的第一个版本于 2008 年推出。Genode 的最新稳定版本是 19.05。

**AIX 和 Genode 的区别:**

<center>

| 没有。 | [计]高级交互执行程序（Advanced Interactive Executive） | 基因组 |
| --- | --- | --- |
| 1. | 它是由 **IBM** 开发并拥有的。 | 它是由 **Genode 实验室**开发的。 |
| 2. | 它于 1986 年推出。 | 它于 2008 年推出。 |
| 3. | 目前稳定的版本是 7.2。 | 目前稳定版本是 19.05。 |
| 4. | 它的内核类型是带有模块的单片。 | 它的内核类型是微内核或单片内核。 |
| 5. | 它的目标系统类型是服务器、网络连接存储和工作站。 | Genode 支持的计算机架构有 ARM、RISC-V、IA-32 和 x86-64。 |
| 6. | AIX 支持的计算机架构有 POWER、PowerPC-AS、PowerPC 和 Power ISA。 | AmigaOS 4 支持的计算机架构是 PowerPC。 |
| 7. | AIX 支持的文件系统有 JFS、JFS2、ISO 9660、UDF、NFS、SMBFS 和 GPFS。 | Genode 支持的文件系统有 ext2、ext3、FAT32 和 ISO9660。 |
| 8. | 它有首选的专有许可证。 | 它拥有 AGPL 的优先许可。 |
| 9. | 其更新管理是服务更新管理助理(SUMA)。 | 它没有更新管理。 |
| 10. | 它的子系统不支持非本机 API。 | 通过其子系统支持的非本地应用编程接口有 POSIX、Qt、SDL 和 MirageOS。 |
| 11. | 它的原生 API 是 SysV/POSIX。 | 它的本土原料药是 Genode。 |

</center>