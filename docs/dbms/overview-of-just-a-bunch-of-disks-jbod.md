# 仅一堆磁盘概述(JBOD)

> 原文:[https://www . geeksforgeeks . org/只是一堆磁盘概述-jbod/](https://www.geeksforgeeks.org/overview-of-just-a-bunch-of-disks-jbod/)

**只是一堆磁盘:**

JBOD(代表“只是一堆磁盘”)是指具有一个存储盘柜的硬盘集合，这些硬盘未配置为充当[独立磁盘冗余阵列(RAID 阵列)](https://www.geeksforgeeks.org/raid-redundant-arrays-of-independent-disks/)。阵列中的多个磁盘连接到一台提供更高存储容量的服务器。

JBODs 通过组合所有磁盘使磁盘看起来像一个整体。像在 RAID 系统中一样，数据冗余地存储在多个磁盘中，这些磁盘在操作系统中显示为单个磁盘。

**JBOD 优势:**

JBOD 的一些可能好处是:

*   JBOD helps to minimize data loss. For example, we can combine 10GB drives with 40GB drives to get 50GB volumes from JBOD. This is a very small advantage, because there may be problems when expanding the existing system, provided that the drive is cheap now.
*   If the drive falls in the JBOD chassis, we can retrieve the lost files through JBOD. It depends on how the operating system manages the disk. Considering that JBOD recovery may be difficult, this is a negligible disadvantage.
*   SATA disks and controllers are cheap, which makes JBOD more cost-effective than RAID.

**在 JBOD 的劣势:**

*   Many hard drives are acting, and the drive performance is not improved.
*   If the disk is lost by mistake, you should search for a backup. Without backup, the data will disappear forever.

**JBOD v/s RAID :**

JBOD 和 RAID 是两种主要的数据存储配置。JBOD 和 RAID 之间的一些区别和相似之处包括:

**相似度:**

1.  Both are suitable for data storage.
2.  Both JBOD and RAID improve the utilization of disk space.
3.  In a disk array, data stored in multiple disks will appear on the operating system like a single disk. Similarly, in the case of JBOD, these disks will also appear on the operating system like a single disk.

**区别:**

1.  RAID is more expensive than JBOD, because RAID uses components like [SATA disk](https://www.geeksforgeeks.org/sata-full-form/) and expensive controllers.
2.  JBOD allows a combination of drives of mixed sizes, while RAID configuration only allows disks of similar sizes to be used in the array.
3.  In most cases, JBOD is more popular than RAID because they are easy to expand, just add another drive.
4.  RAID has some functions, such as supporting hard disk failure and enhancing performance, which are missing in JBOD.

**哪种配置适合你？**

如果应用程序需要大量的本地存储，则应选择 JBOD。使用 NVME 固态硬盘，JBOD 的工作本质上很快。在 RAID 中，数据存储有限，因为数据会经历奇偶校验。就 RAID 而言，RAID 0 是保留总存储容量的唯一级别，但是我们必须在从 RAID 0 中删除磁盘驱动器的同时丢失每个驱动器中的所有数据。RAID 成本更高，如果 RAID 阵列中有任何驱动器损坏，则需要很长时间才能重建。因此，考虑到这一切，JBOD 可能是您的正确选择，它允许轻松的交换、快速的读写速度、更多的数据存储等。