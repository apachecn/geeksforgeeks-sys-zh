# AAA(认证、授权和计费)配置(本地)

> 原文:[https://www . geeksforgeeks . org/AAA-身份验证-授权-计费-配置-本地/](https://www.geeksforgeeks.org/aaa-authentication-authorization-and-accounting-configuration-locally/)

先决条件–[AAA(认证、授权和计费)](https://www.geeksforgeeks.org/computer-network-aaa-authentication-authorization-and-accounting/)
为了提供访问网络资源的安全性，使用了 AAA。AAA 是一个基于标准的框架，用于控制谁被允许使用网络资源(通过身份验证)、他们被授权做什么(通过授权)以及捕获访问网络时执行的操作(通过计费)。

AAA 可以通过使用本地数据库(设备的运行配置)或使用外部 ACS 服务器来实现。这里，我们将只讨论设备本地的 AAA 配置。

**AAA 配置–**
现在，在本例中，我们正在路由器上配置 AAA 身份验证。它包括以下步骤:-
**1。在路由器上启用 AAA**

```
router1(config)#aaa new-model
```

aaa 是通过命令 AAA 新型号启用的。

**2。创建默认身份验证列表–**

```
router1(config)#aaa authentication 
                     login default local
```

它由 aaa 认证登录默认本地命令启用。
在这个命令中，default 表示我们将使用默认的方法列表，local 表示我们将使用本地数据库。

**3。将列表应用于 vty 线路–**

```
router1(config)#line vty 0 4
router1(config)#login authentication default
router1(config)#exit
```

创建默认方法列表后，我们必须将其应用于 vty 线路，这样，无论何时某个用户试图通过 SSH 或 telnet 访问路由器，该用户都必须提供已配置的凭据。

**4。在路由器上创建本地用户–**

```
router1(config)#username GeeksforGeeks 
           privilege 15 password saurabh 
```

这是最重要的一步，因为我们必须创建一个本地数据库，在其中提供用户名(作为 geeksforgeeks)、权限级别 15 和密码(作为 saurabh)。

**注意–**我们在 vty 线路上应用的默认方法列表将强制用户(希望访问路由器的用户)在希望通过 telnet 或 ssh 进行远程访问时输入这些凭据。

**5。调试 aaa 认证–**
我们可以通过命令“调试 aaa 认证”看到 AAA 认证消息。

```
router1#debug aaa authentication 
```

![](img/3dd001eca45ed624237f936284215319.png)

```
 router2# telnet 10_1_1_1
Trying 10_1_1_1 .... Open
User Access Verification
Username: geeksforgeeks
Password:
router1> 
```

现在，我们将从路由器 2 (ip 地址–10 . 1 . 1 . 2/24)远程登录路由器 1 (ip 地址-10 . 1 . 1 . 2/24)，它将要求如图所示的凭据。

![](img/28f8c6f345e5c102bc62eee0617ac495.png)

一旦用户输入凭据，我们就可以看到身份验证消息。除此之外，如果我们想在请求凭据之前应用横幅，我们可以使用所示的命令应用它。

```
router1(config)#aaa authentication 
        banner " welcome to our network" 
```

如果我们想添加用户名和密码提示，我们可以使用下面显示的命令来应用它。

```
router1(config)#aaa authentication 
       username-prompt "enter your username" 
router1(config)#aaa authentication 
       password-prompt "enter your password" 
```

此外，如果我们想在用户输入的凭据错误时显示一条消息，那么我们可以使用下面显示的命令来显示。

```
router1(config)#aaa authentication 
 fail-message "wrong username or password. 
  Please try again..." 
```

此外，我们可以限制用户输入错误凭据的尝试次数。第三次尝试输入凭据后，会话将自动终止。

```
router1(config)#aaa authentication 
       attempts login 3
```