# 使用局域网唤醒协议通过互联网远程启动电脑的程序。

> 原文:[https://www . geesforgeks . org/program-remote-power-PC-internet-use-wake-LAN-protocol/](https://www.geeksforgeeks.org/program-remotely-power-pc-internet-using-wake-lan-protocol/)

[局域网唤醒(WoL)](https://en.wikipedia.org/wiki/Wake-on-LAN) 是一种以太网或令牌环计算机网络标准，允许计算机被网络消息打开或唤醒。

*   消息通常由连接到同一局域网的设备(如智能手机)上执行的程序发送到目标计算机。
*   也可以使用子网定向广播或 WOL 网关服务从另一个网络发起消息。
*   等效术语包括广域网唤醒、远程唤醒、局域网通电、局域网通电、局域网恢复、局域网恢复和局域网唤醒。

**工作原理**

*   局域网唤醒(“WOL”)是使用一种称为魔法包的特殊设计的包来实现的，它被发送到网络中的所有计算机，其中包括要被唤醒的计算机。
*   魔术包包含目的计算机的媒体访问控制地址，一个内置于计算机中每个网络接口卡(“网卡”)或其他以太网设备的识别号，使其能够在网络上被唯一识别和寻址。
*   具有局域网唤醒功能的关机或关机计算机将包含网络设备，这些设备能够在系统关机时以低功耗模式“监听”传入的数据包。
*   如果收到指向设备的媒体访问控制地址的神奇数据包，网卡会向计算机的电源或主板发出信号，启动系统唤醒，这与按下电源按钮的方式非常相似。
*   魔术包在数据链路层(OSI 模型中的第 2 层)发送，发送后，使用网络广播地址广播给给定网络上的所有连接设备；不使用 IP 地址(现场视察模型中的第 3 层)。

为了让局域网唤醒正常工作，部分网络接口需要保持开启。这将消耗少量待机功率，远低于正常工作功率。因此，在不需要时禁用局域网唤醒功能会略微降低已关闭但仍插在电源插座上的计算机的功耗。

**魔法包结构**
魔法包是一个广播帧，在其有效载荷内的任何地方包含 6 个字节的全部 255 (FF FF FF FF 以十六进制表示)，后面是目标计算机的 48 位 MAC 地址的 16 次重复，总共 102 个字节。
由于魔法包只扫描上面的字符串，实际上没有被完整的协议栈解析，它可以作为任何网络和传输层协议发送，尽管它通常作为 UDP 数据报发送到端口 0、7 或 9，或者作为以太网类型 0x0842 直接通过以太网发送。

**标准魔法包有以下基本限制:**

1.  需要目标计算机的媒体访问控制地址(也可能需要安全密码)。
2.  不要提供交货确认。
3.  可能无法在本地网络之外工作。
4.  需要目标计算机上局域网唤醒的硬件支持。
5.  大多数 802.11 无线接口在低功耗状态下不会保持链路，并且无法接收神奇的数据包。

局域网唤醒实现被设计得非常简单，并且可以由网络接口卡上的电路以最小的功耗快速处理。因为局域网唤醒在 IP 协议层之下运行，所以需要媒体访问控制地址，这使得 IP 地址和域名没有意义。

## C++

```
// C program to remotely Power On a PC over the
// internet using the Wake-on-LAN protocol.
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include <string.h>
#include <sys/types.h>

int main()
{
    int i;
    unsigned char toSend[102],mac[6];
    struct sockaddr_in udpClient, udpServer;
    int broadcast = 1 ;

    // UDP Socket creation
    int udpSocket = socket(AF_INET, SOCK_DGRAM, 0);

    // Manipulating the Socket
    if (setsockopt(udpSocket, SOL_SOCKET, SO_BROADCAST,
                  &broadcast, sizeof broadcast) == -1)
    {
        perror("setsockopt (SO_BROADCAST)");
        exit(EXIT_FAILURE);
    }
    udpClient.sin_family = AF_INET;
    udpClient.sin_addr.s_addr = INADDR_ANY;
    udpClient.sin_port = 0;

    //Binding the socket
    bind(udpSocket, (struct sockaddr*)&udpClient, sizeof(udpClient));

    for (i=0; i<6; i++)
        toSend[i] = 0xFF;

    // Let the MAC Address be ab:cd:ef:gh:ij:kl
    mac[0] = 0xab;  // 1st octet of the MAC Address
    mac[1] = 0xcd;  // 2nd octet of the MAC Address
    mac[2] = 0xef;  // 3rd octet of the MAC Address
    mac[3] = 0xgh;  // 4th octet of the MAC Address
    mac[4] = 0xij;  // 5th octet of the MAC Address
    mac[5] = 0xkl;  // 6th octet of the MAC Address

    for (i=1; i<=16; i++)
        memcpy(&toSend[i*6], &mac, 6*sizeof(unsigned char));

    udpServer.sin_family = AF_INET;

    // Broadcast address
    udpServer.sin_addr.s_addr = inet_addr("10.89.255.255");
    udpServer.sin_port = htons(9);

    sendto(udpSocket, &toSend, sizeof(unsigned char) * 102, 0,
             (struct sockaddr*)&udpServer, sizeof(udpServer));
    return 0;
}
```

输出:

```
This program will power on the switched-off PC
whose MAC Address is used in this program (the 
PC and the Host computer must be connected over
LAN). 
```

本文由 [**基什莱·维尔马**](https://www.linkedin.com/in/kishlayverma/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

**参考:**
[【https://en.wikipedia.org/wiki/Wake-on-LAN】](https://en.wikipedia.org/wiki/Wake-on-LAN)
发现有不正确的地方请写评论，或者想分享以上讨论话题的更多信息。