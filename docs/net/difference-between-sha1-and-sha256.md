# SHA1 和 SHA256 的区别

> 原文:[https://www . geeksforgeeks . org/sha1 和-sha256 之间的差异/](https://www.geeksforgeeks.org/difference-between-sha1-and-sha256/)

**1。 [SHA1(安全哈希算法 1)](https://www.geeksforgeeks.org/sha-1-hash-in-java/) :**
SHA1 指的是美国国家安全局提出的加密哈希函数。它接受输入并产生 160 位哈希值的输出。此外，这个函数产生的输出被转换成一个 40 位长的十六进制数。它被称为美国联邦信息处理标准。它于 1995 年首次出版。它是 1993 年出版的 SH0 的继承者。

**示例:**

```
Data : Geeksforgeeks
SHA1 : bc7623b7a94ed3d8feaffaf7580df3eca4f5f5ca

```

**2。SHA256 :**
SHA-256 是一个更安全、更新的密码哈希函数，于 2000 年作为 SHA 函数的新版本推出，并于 2002 年被采纳为 FIPS 标准。允许使用哈希生成器工具为任何字符串或输入值生成 SHA256 哈希。此外，它生成 256 个哈希值，内部状态大小为 256 位，原始消息大小最多为 2 <sup>64</sup> -1 位。

**示例:**

```
Data : Geeksforgeeks
SHA256 : e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
```

**SHA1 和 SHA256 的区别:**

<center>

| 没有。 | SHA1 | SHA256 |
| 1. | SHA1 是 SHA 的第一个版本，它生成一个 160 位的哈希值。 | SHA256 是生成 256 位哈希值的 SHA2 类型。 |
| 2. | SHA1 的内部国家规模为 160。 | SHA256 的内部状态大小为 256。 |
| 3. | 相比之下，它不太安全。 | 它比 SHA1 更安全。 |
| 4. | SHA1 的输出大小是 160 位。 | SHA256 的输出大小为 256 位。 |
| 5. | 它被 SSL 证书颁发机构用来签署证书。 | 这是区块链常用的散列函数。 |
| 6. | 它的位大小更小，因此更容易受到攻击。 | 它有 256 位，因此提高了安全性。 |

</center>