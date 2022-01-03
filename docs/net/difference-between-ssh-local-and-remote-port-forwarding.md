# SSH 本地和远程端口转发的区别

> 原文:[https://www . geesforgeks . org/ssh-本地和远程端口转发的区别/](https://www.geeksforgeeks.org/difference-between-ssh-local-and-remote-port-forwarding/)

SSH 代表“**安全壳**”或“**安全插座壳**”。它是一种加密网络协议，允许两台计算机在不安全的网络(如互联网)上通信和共享数据。SSH 协议保护网络免受各种攻击。

**1。本地端口转发:**
本地端口转发是常见的端口转发类型。它用于让用户从本地计算机连接到另一台服务器，即从与安全外壳客户端运行在同一台计算机上的另一个客户端应用程序安全地转发数据。通过使用本地端口转发，阻止某些网页的防火墙能够绕过。

**2。远程端口转发:**
这种形式的端口转发支持安全外壳服务器端的应用程序。同样的通用目的也有专利。要使用远程端口转发，必须知道目标服务器的地址和两个端口号。选择的端口号取决于要使用的应用程序。

**宋承宪 LPF 与宋承宪 RPF 的区别:**

<figure class="table">

| ssh LPF | ssh rpf |
| 在这种情况下，来自 SSH 客户端的连接通过 SSH 服务器转发，然后到达目标服务器。 | 在这种情况下，来自 SSH 服务器的连接通过 SSH 客户端转发到目标服务器。 |
| LPF 允许您从本地计算机连接到另一台服务器。 | RPF 允许您从远程 SSH 服务器连接到另一台服务器。 |
| 在 OpenSSH 中，使用-L 选项配置本地端口转发。 | 在 OpenSSH 中，使用-R 选项配置本地端口转发。 |
| Linux 下 LPF 的基本语法是:ssh -L 本地 _ 端口:目标 _ 服务器 _ip:远程 _ 端口 ssh _ 服务器 _ 主机名 | Linux 下 RPF 的基本语法是:ssh -R 本地 _ 端口:目标 _ 服务器 _ip:远程 _ 端口 ssh _ 服务器 _ 主机名 |
| 例如:如果您想从笔记本电脑连接到[http://www.ubuntuforums.org](http://www.ubuntuforums.org)使用 SSH 隧道。你会的使用源端口号 8080 和目标端口 80 以及目标服务器 www.ubuntuforums.org | 例如:如果你想让一个朋友访问你的远程桌面，使用命令行 SSH 客户端。您可以使用端口号 5900 和目标服务器 localhost:ssh-r 5900:localhost:5900 guest @ jone-PC |

</figure>