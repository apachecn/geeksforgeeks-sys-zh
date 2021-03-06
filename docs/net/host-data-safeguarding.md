# 主机数据保护

> 原文:[https://www.geeksforgeeks.org/host-data-safeguarding/](https://www.geeksforgeeks.org/host-data-safeguarding/)

主机包括发送或接收数据或服务的客户端和服务器。保护主机数据至关重要，因为如果网络罪犯窃取数据或设备出现故障，组织可能会丢失数据。下面给出了一些保护主机数据的方法:

**加密:**
加密使用复杂的算法改变数据，使其不可读。一个特殊的键把不可读的信息再次返回到可读的数据中。用户可以在 Windows 中利用一个名为 BitLocker 的组件对整个硬盘进行加密。要使用 BitLocker，硬盘上必须至少有两个卷可用。只有加密数据的用户才能访问加密文件。文件加密使用块密码。

**数据备份:**
备份数据是防止数据丢失的最佳方法之一。在数据备份中，计算机信息的副本存储在可移动备份介质中。如果计算机硬件出现故障，一旦系统正常工作，用户就可以从备份中恢复数据。使用密码保护备份。此时，管理员在恢复备份介质上的数据之前输入密码。为了提高安全性，请将备份保存到异地存储区域。

**文件访问控制:**
文件访问控制提供了授予和撤销对有价值文件的访问权限的能力。如果用户只需要访问一个文件，就不应该选择访问服务器上的所有文件。

权限类型:

*   **写:**
    用户可以新建文件和文件夹，修改已有文件和文件夹。
*   **Read:**
    用户可以打开文件和文件夹进行阅读。
*   **修改:**
    用户可以修改和删除已有文件和文件夹，但不能新建。
*   **完全控制:**
    用户可以读取文件内容，创建新文件和文件夹，以及修改现有文件和文件夹。
*   **读取和执行:**
    用户可以读取文件和文件夹的内容并执行程序。