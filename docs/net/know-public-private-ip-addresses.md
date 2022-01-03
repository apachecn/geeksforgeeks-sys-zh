# 知道自己的公有和私有 IP 地址

> 原文:[https://www . geesforgeks . org/know-public-private-IP-address/](https://www.geeksforgeeks.org/know-public-private-ip-addresses/)

您可能已经在 linux 终端上使用了 **ifconfig** 命令来了解系统的不同网络配置。

ifconfig 命令显示以太网或 wifi 连接的硬件地址(HWaddr)和网络地址(inet addr)。

ifconfig 命令不显示您的公共 IP 地址(如果公共和私有不同)。为此，你可以在谷歌搜索中简单输入:**我的 ip 地址是什么**，它会显示你的公共 IP 地址。

在 linux 终端上，您可以使用以下命令来知道您的 IP 地址:
公共 IP:

```
curl ifconfig.me
      or 
curl ipinfo.io/ip

```

私有 IP:

```
hostname -I

```

**参考资料:**
[linux man 词条为 ifconfig](http://www.manpagez.com/man/8/ifconfig/)
[知道你的公共 IP askubuntu](https://askubuntu.com/questions/95910/command-for-determining-my-public-ip)