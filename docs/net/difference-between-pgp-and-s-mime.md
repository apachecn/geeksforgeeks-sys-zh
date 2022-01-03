# PGP 和 S/MIME 的区别

> 原文:[https://www . geesforgeks . org/difference-PGP-and-s-mime/](https://www.geeksforgeeks.org/difference-between-pgp-and-s-mime/)

**1。相当好的隐私(PGP) :**
PGP 是一个开源软件包，旨在保护电子邮件安全。菲尔·齐默曼开发的。它提供了密码学的基本需求。在这一过程中，采取了多个步骤来保护电子邮件，这些步骤是，

```
1. Confidentiality
2. Authentication
3. Compression
4. Resemble
5. Segmentation
6. E-mail compatibility 
```

**2。安全/多用途互联网邮件扩展(S/MIME) :**
S/MIME 是[多用途互联网邮件扩展(MIME)](https://www.geeksforgeeks.org/multipurpose-internet-mail-extension-mime-protocol/) 的安全增强版本。其中，[公钥密码](https://www.geeksforgeeks.org/public-key-encryption/)用于电子邮件的数字签名、加密或解密。用户获得一个具有可信权限的公钥-私钥对，然后在电子邮件应用程序中适当使用这些密钥。

**PGP 和 S/MIME 的区别:**

<center>

| S.NO | 电子邮件加密程序 | S/MIME |
| --- | --- | --- |
| 1. | 它是为处理纯文本而设计的 | 虽然它被设计来处理电子邮件以及许多多媒体文件。 |
| 2. | 与 S/MIME 相比，PGP 的成本更低。 | 而 S/MIME 比较贵。 |
| 3. | PGP 适合个人和办公室使用。 | 虽然它有利于工业应用。 |
| 4. | PGP 的效率不如 S/MIME。 | 而它比 PGP 更有效率。 |
| 5. | 这取决于用户密钥交换。 | 而它依赖于用于密钥交换的分层有效证书。 |
| 6. | PGP 相对不太方便。 | 同时由于所有应用的安全转换，它比 PGP 更方便。 |
| 7. | PGP 包含 4096 个公钥。 | 而它只包含 1024 个公钥。 |
| 8. | PGP 是强加密的标准。 | 虽然它也是强加密的标准，但也有一些缺点。 |
| 9. | PGP 也被用于虚拟专用网络。 | 虽然它不用于虚拟专用网络，但它仅用于电子邮件服务。 |
| 10. | PGP 使用 **Diffie hellman 数字签名**。 | 而它使用的是 **Elgamal 数字签名**。 |

</center>