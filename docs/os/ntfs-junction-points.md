# NTFS 连接点

> 原文:[https://www.geeksforgeeks.org/ntfs-junction-points/](https://www.geeksforgeeks.org/ntfs-junction-points/)

**连接点**(通常也称为 [NTFS](https://www.geeksforgeeks.org/ntfs-full-form/) 连接点或目录连接点)是一种类型的**重解析点**，它包含到目录的链接，该目录充当该目录的别名。连接点的工作类似于符号链接，但仅适用于目录。连接点虽然作为符号链接紧密实现，但却是 Windows 独有的功能。该功能最初是在 Windows 2000 附带的 NTFS 3.0 中引入的。虽然类似于**符号链接**，但它的工作方式是独特的。在本文中，我们将了解连接点的优点、缺点和用途。

由于连接点是重分析点的一种类型，我们将它与其他重分析点进行比较，以找出优点和缺点。

**交叉点的优势:**

*   Directory intersection was introduced in [Windows](https://www.geeksforgeeks.org/interesting-facts-about-windows/) 2000, so it is compatible with later Windows iterations ( **symbolic link** was introduced in windows vista).
*   Less time to solve.
*   Administrator permissions are not required during the creation process (as opposed to symbolic links).
*   The absolute path of the destination is stored, so there is no problem related to the relative path.

**连接点的缺点:**

*   Remote SMB or UNC paths are not supported.
*   Only directories are supported.
*   Only supported on Windows OS, the usage rate is reduced due to incompatibility with other operating systems.

**交叉点的用法:**

*   The operating system allows the old directory path on Windows by pointing the intersection to a newer path and using the intersection.
*   Because connection points are handled at the file system level, they can be used for path redirection, so they can be used to point to paths that do not exist on the drive.
*   The defection method used as directory link in Windows version before Vista.