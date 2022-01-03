# 思科路由器基本命令

> 原文:[https://www.geeksforgeeks.org/cisco-router-basic-commands/](https://www.geeksforgeeks.org/cisco-router-basic-commands/)

路由器是第 3 层设备，用于将数据包从一个网络转发到另一个网络。它根据目的 IP 地址和路由表中的条目，通过其中一个端口转发数据包。通过使用路由表，它可以找到源网络和目的网络之间的优化路径。

在这里，我们将讨论思科路由器的基本命令，如为接口分配一个 IP 地址、调出一个接口、应用启用和加密密码。

管理配置:

**为路由器提供主机名–**
它用于为设备设置名称，表明设备的身份。这很重要，因为这些主机名在广域网中用于身份验证。

我们可以将主机名设置为:

```
router(config)#hostname GeeksforGeeksrouter
GeeksforGeeksrouter(config)#
```

**应用横幅–**这些横幅专门用于向想要访问路由器的用户发出小的安全通知。我们可以根据我们的需要定制它，比如要求登录所需的凭据。

横幅的类型有:

**1 .横幅暴动─**

```
GeeksforGeeksrouter(config)#banner motd #
Enter Text message. End with character '#'
$ No unauthorized access allowed. Enter your credentials!! #
```

这里，motd 表示当天的消息，而#表示分隔符，即消息应以提供的符号结束。当进入路由器的用户执行模式时，将显示此消息

**2。执行横幅–**当用户通过 VTY 线路登录时，该横幅将显示在屏幕上。

**3。登录横幅–**此横幅将在横幅移动后但登录前显示。

这些横幅用于使登录互动。

**设置密码–**
有五个密码用于保护思科设备:

**1。启用密码–**启用密码用于保护特权模式。该密码将以明文形式通过命令“显示运行配置”显示。现在这些都被秘密密码取代了。

```
router(config)#enable password GeeksforGeeks 
```

**2。启用秘密密码–**这也用于保护特权模式，但区别在于它将在“显示运行配置”中显示为密码。如果设置了两个密码，此密码将覆盖启用密码。

```
router(config)#enable secret GeeksforGeeks 
```

**3。线路控制台密码–**当用户通过控制台端口进行访问时，会询问该密码。

```
router(config)#line console 0
router(config-line)#password GeeksforGeeks 
router(config-line)#login
```

**4。线路 VTY 密码–**当用户想要通过 VTY 线路(telnet 或 ssh)访问路由器时，会询问该密码。
显示了远程登录密码的以下配置。

```
router(config)#line VTY 0 4
router(config-line)#password GeeksforGeeks 
router(config-line)#exit
```

**5。辅助密码–**该密码将保护辅助端口。

```
router(config)#line aux 0
router(config-line)#password GeeksforGeeks 
router(config-line)#login
```

**为路由器接口分配 IP 地址–**
我们知道路由器是第 3 层设备，因此路由器的每个端口都应该有一个 IP 地址才能工作。默认情况下，路由器的端口没有 IP 地址，其线路协议也关闭。

```
router(config)#interface fa0/0
router(config-if)#ip address 192.168.1.1 255.255.255.0
router(config-if)#no shut
```

在这里，我们首先必须指定路由器的接口，我们希望在该接口上给出一个 IP 地址。然后，我们将进入接口模式，在该模式下，我们将给出一个 IP 地址，如图所示，后跟其子网掩码(255.255.255.0)。然后，我们通过 no shut 命令对路由器端口进行了管理性设置。

**复制和擦除配置–**
我们可以手动将运行配置(RAM 中的配置)复制到启动配置(NVRAM 中的配置)。因此，下次路由器启动时，它将加载我们复制的配置(因为默认情况下会加载 NVRAM 的配置)。

```
router#copy running-config startup-config
```

要清除 NVRAM 的配置，请使用命令

```
router#erase startup-config
```