# 自适应安全设备(ASA)的基本配置

> 原文:[https://www . geeksforgeeks . org/basic-自适应安全配置-设备-asa/](https://www.geeksforgeeks.org/basic-configuration-of-adaptive-security-appliance-asa/)

先决条件–[自适应安全设备(ASA)](https://www.geeksforgeeks.org/computer-network-adaptive-security-appliance-asa-features/)
自适应安全设备(ASA)是一款思科安全设备，将传统防火墙功能与 VPN、入侵防御和防病毒功能相结合。它有能力在攻击扩散到网络之前提供威胁防御。

作为管理员，我们必须确保防止未经授权访问我们的防火墙。我们可以设置登录密码，为此启用密码。此外，我们将讨论在 ASA 接口上配置一个 IP 地址。

**管理配置–**

**调出接口，给 ASA 分配一个 IP 地址。**
要在 ASA 的接口上配置一个 IP 地址，我们必须配置 4 件事:

**1。调出界面–**
进入全局界面模式后，使用 **no shut** 命令调出界面。

**2。为 ASA–**
的接口分配一个 IP 地址，打开接口后，通过命令分配一个 IP 地址

```
IP address IP_address Subnet_Mask  
```

这与我们为路由器接口分配 IP 地址的方式相同。但不同的是，我们也可以在没有子网掩码的情况下为 ASA 接口分配一个 IP 地址。

```
IP address IP_address
```

现在，如果我们不给出子网掩码，它会自动采用有类子网掩码。例如，如果我们将 192.168.1.1 分配给 ASA 接口，它将自动采用 255.255.255.0 作为子网掩码。

**3。为 ASA 接口指定名称–**
在 ASA 中，我们也为接口指定名称，否则接口将关闭。最常见的名称是“内部”、“外部”或“非军事区”。这些名称在应用策略时使用，但在转发流量时没有任何作用。
我们可以通过以下命令为 ASA 接口指定一个名称:

```
nameif NAME 
```

名称是您想要给接口的名称。

**4。为接口指定安全级别–**
安全级别是一个从 0 到 100 的整数值。它告知接口的可信度，即哪个接口最可信。0 表示不太可信，而 100 表示最可信。
如果我们为接口提供名称 INSIDE，它将自动为其提供安全级别 100，如果我们提供任何其他名称，如 OUTSIDE 或 DMZ，它将自动为其分配 0，但可以手动更改。
我们可以通过以下命令为接口分配安全级别:

```
Security-level {value} 
```

下面是一个示例，我们将提供 IP 地址 192.268.1.1 和子网掩码 255.255.255.0，名称为 INternet，安全级别为 100。

```
asa(config)#int e0
asa(config-if)#no shut
asa(config-if)#ip address 192.168.1.1 255.255.255.0
asa(config-if)#nameif INSIDE 
asa(config-if)#security level 100
```

**将主机名赋予 ASA–**
它用于为设备设置名称，表明设备的身份。它由路由器上使用的相同命令给出

```
asa(config)#hostname ciscoasa
ciscoasa(config)#
```

**设置密码–**
由于 ASA 是一个安全设备，默认情况下，当我们尝试进入特权模式时，它会要求输入密码。默认情况下，没有设置密码，因此只需点击输入，我们就可以进入特权模式。

**启用密码–**
启用密码用于保护特权模式。在路由器中，该密码在运行配置中以明文显示，但在 ASA 中，该密码是加密的(因此不需要启用密码)。)密码是区分大小写的密码，最多包含 16 个字母数字和特殊字符。我们可以通过以下方式设置启用密码

```
asa(config)#enable password GeeksforGeeks 
```

或者通过命令

```
asa(config)#enable passwd GeeksforGeeks 
```

其中 GeeksforGeeks 是密码。
如果我们想禁用该密码或设置默认密码，只需输入命令。

```
asa(config)#enable password 
```

**登录密码–**
该密码用于通过 Telnet 或 SSH 访问 ASA。默认情况下，登录密码为“思科”。我们可以通过命令改变它

```
asa(config)#password GeeksforGeeks 
or 
asa(config)#passwd GeeksforGeeks 
```

其中 GeeksforGeeks 是登录密码。

**使用本地数据库登录:**
在设备上配置了本地数据库(用户名和密码)，以便可以用于登录目的。它的配置方式与路由器上的配置方式相同。可以使用命令在设备上配置本地数据库

```
asa(config)#username SAURABH password GeeksforGeeks 
```

其中 SAURABH 是用户名，密码是 GeeksforGeeks。
如果我们希望 ASA 使用其本地数据库进行登录，那么我们可以使用命令

```
asa(config)#aaa authentication serial console LOCAL
```

这里，注意 LOCAL 是区分大小写的