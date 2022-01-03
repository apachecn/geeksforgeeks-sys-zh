# 提高多个磁盘的性能

> 原文:[https://www . geeksforgeeks . org/提高多磁盘性能/](https://www.geeksforgeeks.org/increasing-performance-of-multiple-disks/)

以前，我们只有一个磁盘，在获取数据和响应方面存在大量的时间延迟和低性能。这引发了我们如何在提高可靠性的同时提高磁盘性能的思考。然后，出现了并行性能和并发磁盘访问的概念。

[廉价磁盘冗余阵列(RAID)](https://www.geeksforgeeks.org/raid-redundant-arrays-of-independent-disks/) 是引入的一个新概念，可以同时访问文件。这个概念后来被称为独立磁盘冗余阵列。使用磁盘阵列，可以优化存储，提高性能和可靠性。

支持性能提升的主要思想是:**数据剥离**。这包括在不同磁盘之间分发数据，并以同步方式访问所有磁盘以检索数据。在多个磁盘的情况下，提高性能的主要概念包括使用并行数据访问的概念，将数据分发到几个磁盘中，而不是只保存在一个磁盘中。要做到这一点，有两个概念可以遵循。它们是位级数据条带化和块级数据条带化。

1.  Bit-level data striping can be performed to improve disk performance. This is a very molecular concept. We must take one bit from every byte of data. Then, put it on the disk. For example, if we use 8 disks, and each bit of a byte (data) corresponds to a disk, the data transmission will increase by 8 times. Reading and writing operations will involve the use of all disks. This will greatly improve the running speed.
2.  If we store a data block on disk, we call it **block-level striping** . For example, if we use 8 disks, we can process 8 block requests at the same time. If there are multiple data requests, then in this case, the increase of transmission rate will increase by 8 times. The general view is that using n disks can improve the performance by n times.

在位级条带化和块级条带化中，数据访问是并行的，速度也提高了。我们使用大量磁盘，这提高了速度和性能。但是，当任何磁盘出现故障时，整个操作都会受到影响。因此，该系统证明其可靠性非常低。