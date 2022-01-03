# 【Rootkit 和病毒的区别

> 原文:[https://www . geeksforgeeks . org/rootkit 和病毒的区别/](https://www.geeksforgeeks.org/difference-between-rootkit-and-virus/)

**1。 [Rootkit](https://www.geeksforgeeks.org/malware-and-its-types/) :**
Rootkit 是一组应用程序，一种类型的[恶意软件](https://www.geeksforgeeks.org/malware-and-its-types/)，旨在感染目标 PC，并允许攻击者安装一组工具，授予他对计算机的持久远程访问权限。这种恶意软件通常伪装成“藏在显眼的地方”的普通文件，这样你的反病毒软件就会忽略它们。它允许管理员级别访问计算机或计算机网络。其动机是从您的计算机中窃取身份信息，通常是为了获得对系统的控制。很难检测和清除，需要专门的工具来清除。

**2。[病毒](https://www.geeksforgeeks.org/types-of-virus/) :**
病毒是附加在另一个可执行文件上的恶意可执行代码，它可以是无害的，也可以修改或删除数据。当计算机程序带着病毒运行时，它会执行一些操作，如从计算机系统中删除文件。病毒无法通过远程控制。

**Rootkit 和病毒的区别:**

<center>

| 没有。 | 提权软件包 | 病毒 |
| 1. | Rootkit 是一组恶意程序，允许管理员级别访问计算机网络。 | 病毒是附加在另一个可执行文件上的恶意可执行代码，它可能是无害的，也可能修改或删除数据。 |
| 2. | rootkit 的主要目的是窃取身份信息，通常是为了控制系统。 | 病毒的主要目的是修改信息。 |
| 3. | 检测和删除 rootkit 是一个复杂的过程，通常需要使用专门的工具。 | 防病毒软件用于防范病毒。 |
| 4. | Rootkit 是恶意软件的一种。 | 病毒是恶意软件的一种。 |
| 5. | 它给予攻击者未经授权的系统访问和控制。 | 它可以控制数据和资源，导致错误，破坏系统，降低性能。 |
| 6. | 危害更大。 | 相比之下，它的危害较小。 |
| 7. | TDSS、ZeroAccess、Alureon 和 Necurs 是一些常见的 rootkit。 | 常驻病毒和非常驻病毒是两种类型的病毒。 |

</center>