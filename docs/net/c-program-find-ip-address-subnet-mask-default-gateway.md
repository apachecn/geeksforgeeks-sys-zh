# C 程序查找 IP 地址、子网掩码&默认网关

> 原文:[https://www . geesforgeks . org/c-program-find-IP-address-子网掩码-默认-网关/](https://www.geeksforgeeks.org/c-program-find-ip-address-subnet-mask-default-gateway/)

**术语**

**[IP 地址](https://www.geeksforgeeks.org/ip-addressing-classless-addressing/):**IP 地址是互联网协议地址的缩写，是一个网络硬件的识别号。拥有一个 IP 地址允许设备通过基于 IP 的网络(如互联网)与其他设备通信。

**子网掩码:**子网掩码是一个 32 位数字，用于通过将 IP 地址分为网络地址和主机地址来区分 IP 地址的网络组成部分。子网掩码用于设计连接本地网络的子网，并确定一个 IP 地址属于哪个子网。

**默认网关:**默认网关充当接入点或 IP 路由器，联网的计算机使用它向另一个网络或互联网中的计算机发送信息。默认只是指默认使用该网关，除非应用程序指定了另一个网关。默认网关允许网络上的计算机与另一个网络上的计算机通信。没有它，网络就与外界隔绝。

**使用系统命令**

为了获得 IP 地址、子网掩码和默认网关，我们在 cmd 中执行 ipconfig 命令。在这里，我们将从< stdlib.h >开始利用 system()借助一个 C 程序执行一个系统操作:

```
#include <stdio.h>
#include <stdlib.h>

int main()
{
  system("c:\\windows\\system32\\ipconfig");
  return 0;
}
```

**使用 execl 命令**

这将显示 IPv4 地址、子网掩码和默认网关。同样的操作也可以用 execl()函数来执行。为了稍后执行，我们编写代码:

```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int main()
{
  execl("c:\\windows\\system32\\ipconfig", "ipconfig", 0);
  return 0;
}
```

**输出:**
![](https://media.geeksforgeeks.org/wp-content/uploads/Captihure-1024x852.jpg)

本文由 **Amaryta Ranjan Saikia** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。