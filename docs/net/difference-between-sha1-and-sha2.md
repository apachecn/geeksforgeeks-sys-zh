# SHA1 和 SHA2 的区别

> 原文:[https://www . geeksforgeeks . org/sha1 和 sha2 之间的差异/](https://www.geeksforgeeks.org/difference-between-sha1-and-sha2/)

**1。 [SHA1(安全哈希算法 1)](https://www.geeksforgeeks.org/sha-1-hash-in-java/) :**
SHA1 是美国国家安全局设计的密码哈希函数。它接受一个输入并产生一个 160 位的哈希值。此外，这个函数产生的输出被转换成一个 40 位长的十六进制数。它是美国联邦信息处理标准。它于 1995 年首次出版。它是 1993 年出版的 SH0 的继承者。
**例:**

```
Data : Geeksforgeeks
SHA1 : bc7623b7a94ed3d8feaffaf7580df3eca4f5f5ca 
```

**2。SHA2(安全散列算法 2) :**
SHA1 也是一个密码散列函数，由美国国家安全局设计。它是使用 Merkle-Damgard 结构从单向压缩函数构建的。所使用的压缩函数是使用分类分组密码的戴维斯-迈耶结构构建的。它于 2001 年首次出版。它是 SH1 的继承者。
**例:**

```
Data : Geeksforgeeks
SHA2(256) : 86d755349c6b9f95f365c6ffe7734f25bf2b00cabe8c6bc5f2b8b746c1aac332 
```

**SHA1 和 SHA2 的区别:**

<center>

| SHA1 | SHA2 |
| --- | --- |
| 它是美国国家安全局为取代 SH0 而设计的密码散列函数。 | 它是美国国家安全局为取代 SH1 而设计的加密散列函数。 |
| 它出版于 1995 年。 | 虽然它是在 2001 年出版的。 |
| 它产生 160 位哈希值。 | 它产生 224、256、384 或 512 位哈希值。 |
| 它是 SH0 的继承者，SH2 的前身。 | 它是 SH1 的后继者和 SH3 的前身。 |
| 它不太安全。 | 虽然它更安全。 |
| 它的结构基于 Merkle-Damgard 建筑。 | 其结构基于 Merkle-Damgard 结构，具有 Davies-Meyer 压缩功能。 |
| SHA1 证书不可靠。 | SHA2 有更多改进的证书。 |
| 它生成较小的散列。 | 同时它会生成更大的哈希。 |
| SHA1 生成的哈希很弱。 | 而 SHA2 生成的哈希比较强。 |
| 现在还没有广泛使用。 | 虽然它被广泛使用。 |

</center>