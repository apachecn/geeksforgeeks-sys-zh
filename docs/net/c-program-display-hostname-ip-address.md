# 显示主机名和 IP 地址的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-display-hostname-IP-address/](https://www.geeksforgeeks.org/c-program-display-hostname-ip-address/)

有很多方法可以找到本地机器的*主机名*和 *IP 地址*。这里有一个使用 C 程序查找主机名和 IP 地址的简单方法。

我们将使用以下功能:-

**gethostname()**:gethostname 函数检索本地计算机的标准主机名。

**gethostbyname()**:gethostbyname 函数从主机数据库中检索与主机名对应的主机信息。

**inet _ ntoa()**:inet _ ntoa 函数将(Ipv4)互联网网络地址转换为互联网标准点分十进制格式的 ASCII 字符串。

## C/C++

```
// C program to display hostname
// and IP address
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <errno.h>
#include <netdb.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>

// Returns hostname for the local computer
void checkHostName(int hostname)
{
    if (hostname == -1)
    {
        perror("gethostname");
        exit(1);
    }
}

// Returns host information corresponding to host name
void checkHostEntry(struct hostent * hostentry)
{
    if (hostentry == NULL)
    {
        perror("gethostbyname");
        exit(1);
    }
}

// Converts space-delimited IPv4 addresses
// to dotted-decimal format
void checkIPbuffer(char *IPbuffer)
{
    if (NULL == IPbuffer)
    {
        perror("inet_ntoa");
        exit(1);
    }
}

// Driver code
int main()
{
    char hostbuffer[256];
    char *IPbuffer;
    struct hostent *host_entry;
    int hostname;

    // To retrieve hostname
    hostname = gethostname(hostbuffer, sizeof(hostbuffer));
    checkHostName(hostname);

    // To retrieve host information
    host_entry = gethostbyname(hostbuffer);
    checkHostEntry(host_entry);

    // To convert an Internet network
    // address into ASCII string
    IPbuffer = inet_ntoa(*((struct in_addr*)
                           host_entry->h_addr_list[0]));

    printf("Hostname: %s\n", hostbuffer);
    printf("Host IP: %s", IPbuffer);

    return 0;
}
```

Output:

```
Hostname: cContainer
Host IP: 10.98.162.101

```

*输出因机器而异*