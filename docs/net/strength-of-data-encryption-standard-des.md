# 数据加密标准(DES)的强度

> 原文:[https://www . geesforgeks . org/数据加密强度-标准-des/](https://www.geeksforgeeks.org/strength-of-data-encryption-standard-des/)

[数据加密标准(DES)](https://www.geeksforgeeks.org/data-encryption-standard-des-set-1/) 是一种对称密钥分组密码算法。该算法基于 Feistel 网络。该算法使用 56 位密钥加密 64 位数据块中的数据。

关于数据加密标准的强度，主要有两类担忧。它们是:

1.  对所用特定算法的担忧。
2.  对 56 位密钥使用的关注。

关于所用算法的第一个问题是利用 DES 算法的特性来解决密码分析的可能性。更严重的问题是所用密钥的长度。可以有![2^{56}](img/e3d230223e25743fd78dfe18d5489687.png "Rendered by QuickLaTeX.com")(大约 7.2 × ![10^{16}](img/4f4fc73769058c0528f133687511f68f.png "Rendered by QuickLaTeX.com")键)个可能的键，键长为 56 位。因此，暴力攻击似乎是不切实际的。

假设平均一个人必须搜索一半的密钥空间来破解密文，那么一个每微秒执行一次 DES 加密的系统可能需要一千多年的时间。但是，每微秒一个 DES 加密的假设过于保守。1998 年 7 月，当电子前沿基金会(EFF)破解了一个 DES 加密后，DES 终于被证明是不安全的。加密是在一台特殊用途的“DES 破解机”的帮助下被破解的。据报道，袭击发生不到 3 天。

简单地运行所有可能的密钥不会导致破解 DES 加密。除非给出已知的纯文本，否则攻击者必须能够将纯文本与其他数据区分开来。需要对目标纯文本有一定程度的了解，并需要一些技术来自动区分纯文本和乱码，以补充暴力方法。如果蛮力攻击是破解 DES 加密算法的唯一手段，那么使用更长的密钥显然有助于我们对抗此类攻击。如果使用 128 位密钥，通过强力保证算法不可破解。

差分密码分析、线性密码分析是对 DES 算法进行统计攻击的例子。DES 的重要替代品很少是 [AES(高级加密标准)](https://www.geeksforgeeks.org/difference-between-aes-and-des-ciphers/)和三重 DES。