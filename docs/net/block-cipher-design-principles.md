# 分组密码设计原则

> 原文:[https://www . geesforgeks . org/block-cipher-design-principles/](https://www.geeksforgeeks.org/block-cipher-design-principles/)

**分组密码**内置于 Feistel 密码结构中。分组密码有特定的轮数和生成密文的密钥。为了定义算法的复杂程度，很少考虑设计原则。

这些解释如下:

1.  **回合数–**
    回合数是设计标准中经常考虑的，它只是反映了适合算法的回合数，使其更加复杂，在 DES 中，我们有 16 个回合确保其更加安全，而在 AES 中，我们有 10 个回合使其更加安全。
2.  **Design of function F –**
    The core part of the Feistel Block cipher structure is the Round Function. The complexity of cryptanalysis can be derived from the Round function i.e. the increasing level of complexity for the round function would be greatly contributing to an increase in complexity.

    为了增加舍入函数的复杂性，舍入函数中还包括雪崩效应，因为纯文本中单个位的改变会由于雪崩效应的存在而产生有害的输出。

3.  **密钥调度算法–**
    在 Feistel 分组密码结构中，每一轮都会生成一个子密钥，增加了密码分析的复杂度。雪崩效应使得派生子密钥变得更加复杂。解密必须非常小心，才能得到实际输出，因为其中存在雪崩效应。