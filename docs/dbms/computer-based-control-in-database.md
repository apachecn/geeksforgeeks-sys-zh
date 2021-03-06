# 数据库中基于计算机的控制

> 原文:[https://www . geesforgeks . org/基于计算机的数据库控制/](https://www.geeksforgeeks.org/computer-based-control-in-database/)

在本文中，我们将讨论基于计算机的控件的概述，并将详细讨论多用户数据库环境中可用的基于计算机的控件。我们一个一个来讨论。

**概述:**
从物理控制到管理程序，针对计算机系统威胁的不同形式的对策。尽管基于计算机的控制范围已经存在，但是[数据库管理系统](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)的安全性并不比操作系统好，因为它们之间有密切的联系。如今，在多用户数据库环境中有许多基于计算机的控件可用。

**数据库中可用的基于计算机的控制:**
大部分如下。

*   授权和认证
*   访问控制
*   视图
*   备份和恢复
*   完整
*   加密和解密
*   磁盘阵列工具

我们一个一个来讨论。

**授权和认证:**

*   使主体(用户)能够合法访问系统或系统对象的权限或特权的授予称为授权。
*   授权控制可以内置于软件中，不仅控制用户可以访问的系统种类，还控制用户可以使用它做什么。
*   身份验证过程包括请求访问对象的主体的身份验证。
*   身份验证是数据库管理系统识别用户并证明其身份以查看数据库的过程。
*   要在数据库环境中对用户进行身份验证，需要以下两个元素。

1.  用户标识
2.  身份验证令牌

*   用户标识允许安全组件识别用户，并通过提供正确的身份验证令牌(只有用户知道的密码)来验证用户身份。成功验证用户后，验证用户标识将映射到验证标识。

**访问控制:**

*   对数据库系统进行访问控制的方法之一是基于特权的授予和撤销。特权允许用户创建或访问一些数据库对象，如表、视图、索引等

**视图:**

*   该机制的主要概念是通过对某些用户隐藏部分数据库来提供灵活且最强大的安全机制。
*   视图是一个虚拟表。
*   视图不存储任何自己的数据，但它就像一个窗口，通过它可以查看或更改表中的数据。
*   基表是指视图所基于的表。

**备份和恢复:**

*   定期将数据库及其日志文件复制到离线存储介质的过程称为备份。
*   在日志文件中，备份副本和捕获的信息用于将数据库恢复到当前状态。

**完整性:**

*   在数据库系统中，数据完整性意味着数据的完整性、正确性和一致性。
*   这是数据库保护的另一种形式。在关系数据库系统中，可以使用完整性规则或约束来实现数据完整性。
*   无论对数据库做了什么更改，都不会丢失数据一致性。

**加密和解密:**

*   加密是一种用于保护敏感数据的技术，例如通过某些类型的通信网络传输的信用卡号码。
*   在数据库管理系统的正常安全机制不充分的情况下，加密可用于为数据库的敏感部分提供额外的保护。
*   如果数据没有加密，就说是纯文本。
*   如果数据是加密的，就说是密文。
*   如果过程是将纯文本转换为密文，则称为加密。
*   如果过程是将密文转换为纯文本，则称解密。

**RAID 工具:**

*   RAID 可以表示为“独立磁盘冗余阵列”。运行数据库管理系统的硬件必须是容错的，这意味着即使其中一个硬件组件出现故障，数据库管理系统也必须继续运行。
*   RAID 最初代表廉价磁盘冗余阵列，但最近 RAID 中的“我”开始代表独立。
*   磁盘阵列有许多不同的磁盘配置，称为磁盘阵列级别，如下所示。

<figure class="table">

| 没有。 | 磁盘阵列级别 | 类型 |
| --- | --- | --- |
| 1. | RAID 0 | 非冗余。 |
| 2. | RAID 1 | 反映 |
| 3. | RAID 2 | 纠错码 |
| 4. | RAID 3 | 比特交织奇偶校验 |
| 5. | RAID 4 | 块交错奇偶校验 |
| 6. | RAID 5 | 块交错分布式方 |
| 7. | RAID 6 | 这是 5 号假期的延长 |

</figure>