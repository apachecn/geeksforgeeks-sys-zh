# TELNET 简介

> 原文:[https://www.geeksforgeeks.org/introduction-to-telnet/](https://www.geeksforgeeks.org/introduction-to-telnet/)

[**TELNET**](https://practice.geeksforgeeks.org/problems/explain-telnet) 代表**TE**termina**L NET**工作。这是一种使一台计算机能够连接到本地计算机的协议。它是由 [**ISO**](https://www.geeksforgeeks.org/iso-full-form/) 给出的虚拟终端服务的标准 [**TCP/IP 协议**](https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/) 。开始连接的计算机称为**本地计算机**。正在连接的计算机，即接受连接的计算机，称为**远程计算机**。当本地和远程计算机之间建立连接时。在 telnet 操作期间，在远程计算机上执行的任何操作都将由本地计算机显示。Telnet 基于客户机/服务器原理运行。本地计算机使用 telnet 客户端程序，远程计算机使用 telnet 服务器程序。

**远程登录命令:**
远程登录的命令由前缀字符“解释为命令”(IAC)标识，其代码为 255。IAC 后面是命令和选项代码。该命令的基本格式如下图所示:

![](img/2dd32f74f2a3f826c55b4db5a084aa6e.png)

**图–**远程登录命令格式

以下是一些重要的**远程登录命令**:

<figure class="table">

| 字符
 | 十进制
 | 二进制
 | 意思是
 |
| --- | --- | --- | --- |
| 将 | Two hundred and fifty-one | Eleven million one hundred and eleven thousand and eleven | 1.提议启用。
2。接受启用请求。
 |
| 将不会 | Two hundred and fifty-two | Eleven million one hundred and eleven thousand one hundred | 1.拒绝启用的请求。
2。提议禁用。
3。接受禁用请求。
 |
| 防御命令(Defense Order) | Two hundred and fifty-three | 11111101` | 1.批准启用请求。
2。请求启用。
 |
| 不 | Two hundred and fifty-four | Eleven million one hundred and eleven thousand one hundred and ten | 1.不批准启用的请求。
2。批准禁用提议。
3。请求禁用。
 |

以下是一些与 telnet 一起使用的**常用选项【T1:** 

<figure class="table">

| 代码
 | 选项
 | 意思是
 |
| --- | --- | --- |
| Zero | 二进制的 | 它解释为 8 位二进制传输。 |
| one | 回声 | 它会将一侧接收到的数据反射到另一侧。 |
| three | 压制继续 | 它将抑制数据后的前进信号。 |
| five | 状态 | 它将请求远程登录的状态。 |
| six | 计时标记 | 它定义了时间标记。 |
| eight | 线宽 | 它指定线条宽度。 |
| nine | 页面大小 | 它指定一页中的行数。 |
| Twenty-four | 终端类型 | 它设置终端类型。 |
| Thirty-two | 临界速度 | 它设定了终端速度。 |
| Thirty-four | 线路模式 | 它将变为线路模式。 |

**操作模式:**
大多数 telnet 实现以以下**三种模式之一操作:**

```
Default mode
Character mode
Line mode
```

**默认模式:**

*   如果没有调用其他模式，则使用该模式。
*   客户端在这种模式下执行回显。
*   在这种模式下，用户键入一个字符，客户端在屏幕上回显该字符，但直到整行完成后才发送。

**人物模式:**

*   在此模式下键入的每个字符都由客户端发送到服务器。
*   服务器在这种模式下通常会将字符回显在客户端的屏幕上。

**线路模式:**

*   线条编辑，如呼应，字符删除等。是从客户端完成的。
*   客户端将整行发送到服务器。

</figure>

</figure>