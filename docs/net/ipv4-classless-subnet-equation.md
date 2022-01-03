# IPv4 无类子网方程

> 原文:[https://www . geesforgeks . org/IP v4-无类子网-等式/](https://www.geeksforgeeks.org/ipv4-classless-subnet-equation/)

先决条件–[无类寻址](https://www.geeksforgeeks.org/ip-addressing-classless-addressing/)、[超网](https://www.geeksforgeeks.org/computer-network-supernetting/)、
T5】问题–如何计算 IP 地址子网信息(网络、广播、第一个 IP、最后一个 IP)？
计算 IPv4 子网网络 ID 的方程太简单了。

*在丙类子网中使用和测试。

首先，请记住此子网主机图(每个前缀的主机数量):

```
Network Prefix:  Number of IPs
24            :      256 IPs
25            :      128 IPs
26            :      64 IPs
27            :      32 IPs
28            :      16 IPs
29            :      8 IPs
30            :      4 IPs 
```

**使用等式:**

```
Network ID: floor(Host Address/Subnet Number of Hosts) * Subnet Number of Hosts
Broadcast ID: (Host ID + (Subnet Number of Hosts-1))
First Host: Network ID + 1
Last Host: Broadcast ID - 1

```

**Ex1: 192.168.1.65/28:**

```
65/16 = 4.0625
Network ID: 4*16 = 64           (192.168.1.64)
Broadcast ID: 64+(16-1) = 79    (192.168.1.79)
First Host ID: 64 + 1 = 65      (192.168.1.65)
Last Host ID: 79 - 1 = 78       (192.168.1.78)

```

**Ex2: 192.168.20.166/25:**

```
166/128 = 1.296875
Network ID: 1*128 = 128         (192.168.20.128)
Broadcast ID: 128+(128-1) = 255 (192.168.20.255)
First Host ID: 128 + 1 = 129    (192.168.20.129)
Last Host ID: 255 - 1 = 254     (192.168.20.254)

```

**Ex3: 192.168.30.14/29:**

```
14/8 = 1.75
Network ID: 1*8 = 8             (192.168.30.8)
Broadcast ID: 8+(8-1) = 15      (192.168.30.15)
First Host ID: 8 + 1 = 9        (192.168.30.9)
Last Host ID: 15 - 1 = 14       (192.168.30.14)

```

**Ex4: 192.168.20.86/30:**

```
86/4 = 21.5
Network ID: 21*4 = 84           (192.168.20.84)
Broadcast ID: 84+(4-1) = 87     (192.168.20.87)
First Host ID: 84 + 1 = 85      (192.168.20.85)
Last Host ID: 87 - 1 = 86       (192.168.20.86)

```