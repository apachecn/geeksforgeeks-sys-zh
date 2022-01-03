# 微内核和单片内核的区别

> 原文:[https://www . geeksforgeeks . org/微内核和单片内核的区别/](https://www.geeksforgeeks.org/difference-between-microkernel-and-monolithic-kernel/)

**什么是内核？**
[内核](https://www.geeksforgeeks.org/kernel-in-operating-system/)是计算机操作系统核心的计算机程序，对系统中的一切都有完全的控制权。它管理计算机和硬件的操作。
**有五种果仁:**

1.  微内核，只包含基本功能；
2.  单片内核，包含许多设备驱动程序。
3.  混合核
4.  外核
5.  纳米内核

但是在本教程中，我们将只研究微内核和单片内核。

**1。** [**微内核**](https://www.geeksforgeeks.org/microkernel-in-operating-systems/) **:**
内核管理计算机的操作，在微内核中用户服务和内核服务在不同的地址空间中实现。用户服务保存在用户地址空间中，内核服务保存在内核地址空间中。

**2。** [**单片内核**](https://www.geeksforgeeks.org/monolithic-kernel-and-key-differences-from-microkernel/) **:**
在单片内核中，整个操作系统以内核模式作为单个程序运行。用户服务和内核服务在同一个地址空间中实现。

**微内核和单片内核的区别:**

<figure class="table">

| **微内核** | **单片内核** |
| 在微内核用户服务和内核中，服务被保存在不同的地址空间中。 | 在单片内核中，用户服务和内核服务都保持在同一个地址空间中。 |
| 操作系统设计复杂。 | 操作系统易于设计和实现。 |
| 微内核的尺寸更小。

 | 单片内核比微内核大。 |
| 更容易添加新功能。 | 难以添加新功能。 |
| 要设计一个微内核，需要更多的代码。 | 与微内核相比，代码更少 |
| 一个组件的故障不会影响微内核的工作。 | 单片内核中一个组件的故障会导致整个系统的故障。 |
| 执行速度低。 | 执行速度快。 |
| 扩展微内核很容易。 | 扩展单片内核并不容易。 |
| **示例:** Mac OS X。 | **示例:**微软 Windows 95。 |

</figure>