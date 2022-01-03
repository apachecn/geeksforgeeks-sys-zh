# 压缩 IPv6 地址

> 原文:[https://www.geeksforgeeks.org/compression-of-ipv6-address/](https://www.geeksforgeeks.org/compression-of-ipv6-address/)

[IPv6 地址](https://www.geeksforgeeks.org/internet-protocol-version-6-ipv6/)是 IP 地址版本 6 的简称。它基本上是一个 128 位地址。在 IPv6 地址中，十六进制表示法是首选。IPv6 十六进制表示法总共有 8 个字段，每个字段由 16 位组成。
因此，总位数是 8×16 = 128

**压缩规则:**
基本上有三个压缩规则:

*   **Rule-1:** When only 0 (zero) is available in a field then it is removed from the IPv6 address notation. 

```
IPv6 = FE82:1234:0:1235:1416:1A12:1B12:1C1F

After compression,
IPv6 = FE82:1234::1235:1416:1A12:1B12:1C1F 
```

*   **Rule-2:** When continuous 0s (zeros) are available in IPv6 address notation then all zeros are replaced by **::**. 

```
IPv6 = FE82:0:0:0:0:1A12:1234:1A12

After compression,
IPv6 = FE82::1A12:1234:1A12 
```

*   **Rule-3:** When zeros are present in discontinuous places then at only one junction, 0s (zeros) are replaced by **::**. 

```
IPv6 = 2001:1234:0:0:1A12:0:0:1A13

After compression,
IPv6 = 2001:1234::1A12:0:0:1A13
          or
     = 2001:1234:0:0:1A12::1A13 
```

**未指定的地址:**当以十六进制表示 IPv6 时，所有字段都为 0。它由…表示。

```
:: = 0:0:0:0:0:0:0:0
```

**环回地址:**在 IPv6 的十六进制表示法中，除最后一个字段外，所有字段都是 0，最后一个字段值是 1。它由::1 表示。

```
::1 = 0:0:0:0:0:0:0:1
```