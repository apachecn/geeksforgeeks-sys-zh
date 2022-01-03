# 从给定的 IP 地址找到数据库管理员的替代方法

> 原文:[https://www . geesforgeks . org/alternate-method-to-find-DBA-from-给定 ip-address/](https://www.geeksforgeeks.org/alternate-method-to-find-dba-from-given-ip-address/)

以前的方法[从 IP 地址](https://www.geeksforgeeks.org/finding-dba-from-given-ip-address/)中查找 DBA 还有一个缺点，就是如果我们只需要查找网络的 DBA，而不需要查找网络的网络 Id，但是用那种方法，不查找网络的网络 Id 就不能得到网络的 DBA。

在这种方法中，我们将使用快捷方式来查找网络标识和数据库管理员。使用这种方法，我们可以找到网络的数据库管理员，而不需要找到网络的网络标识。两种方法的共同点是我们需要找到 IP 地址属于哪一类。

每个 [IP 地址](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)都有:-

```
1. Net bits
2. Host bits  
```

*   **查找网络标识的方法–**对于网络标识，主机位全为零。
*   **查找数据库管理员的方法–**对于数据库管理员，主机位都是 1。

**例-1:**
IP = 144.89.69.120
这个属于 B 类，
在 B 类中，16 位是净位，16 位是主机位。
因此，

```
Net Id = 144.89.0.0
DBA = 144.89.255.255  
```

**例-2:**
IP = 62.89.99.123
这个属于 A 类，
在 A 类中，8 位是净位，24 位是主机位。
因此，

```
Net Id = 62.0.0.0
DBA = 62.255.255.255   
```