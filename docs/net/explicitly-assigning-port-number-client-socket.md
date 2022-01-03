# 在套接字

中为客户端明确分配端口号

> 原文:[https://www . geesforgeks . org/explicit-assignment-port-number-client-socket/](https://www.geeksforgeeks.org/explicitly-assigning-port-number-client-socket/)

先决条件:[C/c++](https://www.geeksforgeeks.org/socket-programming-cc/)中的 Socket 编程。
在套接字编程中，当服务器和客户端连接时，操作系统会向客户端提供任何随机端口号来运行，一般来说，我们并不关心它，但在某些情况下，客户端可能有防火墙，只允许特定端口号上的传出连接。因此，操作系统提供给客户端的端口号很可能已被客户端防火墙阻止。在这种情况下，我们需要**显式或强制地将任何端口号分配给它可以操作的客户端**。

有些协议，如[**【NFS】**](https://en.wikipedia.org/wiki/Network_File_System)协议，要求客户端程序只在某个端口号上运行，因此在这种情况下，客户端只需要强制分配该端口号，因为它在 111 或 2049 上运行的是[端口号](https://serverfault.com/questions/377170/which-ports-do-i-need-to-open-in-the-firewall-to-use-nfs)。这可以使用在客户端套接字中指定特定端口号的 bind()系统调用来完成。

下面是服务器和客户端程序的实现，其中客户端将被强制分配一个端口号。

**服务器端程序**

## C

```
// C program to demonstrate
// socket programming in finding ip address
// and port number of connected client
// on Server Side
#include<stdio.h>
#include<sys/types.h>
#include<sys/socket.h>
#include<sys/un.h>
#include<string.h>
#include<netdb.h>
#include<netinet/in.h>
#include<arpa/inet.h>
#include<string.h>

int main()
{
    // Two buffers for message communication
    char buffer1[256], buffer2[256];
    int server = socket(AF_INET, SOCK_STREAM, 0);
    if (server < 0)
        printf("Error in server creating\n");
    else
        printf("Server Created\n");

    struct sockaddr_in my_addr, peer_addr;
    my_addr.sin_family = AF_INET;
    my_addr.sin_addr.s_addr = INADDR_ANY;

    // This ip address will change according to the machine
    my_addr.sin_addr.s_addr = inet_addr("10.32.40.213");

    my_addr.sin_port = htons(12000);

    if (bind(server, (struct sockaddr*) &my_addr, sizeof(my_addr)) == 0)
        printf("Binded Correctly\n");
    else
        printf("Unable to bind\n");

    if (listen(server, 3) == 0)
        printf("Listening ...\n");
    else
        printf("Unable to listen\n");

    socklen_t addr_size;
    addr_size = sizeof(struct sockaddr_in);

    // Ip character array will store the ip address of client
    char *ip;

    // while loop is iterated infinitely to
    // accept infinite connection one by one
    while (1)
    {
        int acc = accept(server, (struct sockaddr*) &peer_addr, &addr_size);
        printf("Connection Established\n");
        char ip[INET_ADDRSTRLEN];
        inet_ntop(AF_INET, &(peer_addr.sin_addr), ip, INET_ADDRSTRLEN);

        // "ntohs(peer_addr.sin_port)" function is
        // for finding port number of client
        printf("connection established with IP : %s and PORT : %d\n",
                                            ip, ntohs(peer_addr.sin_port));

        recv(acc, buffer2, 256, 0);
        printf("Client : %s\n", buffer2);
        strcpy(buffer1, "Hello");
        send(acc, buffer1, 256, 0);
    }
    return 0;
}
```

输出:

```
Server Created
Binded Correctly
Listening ...
Connection Established
connection established with IP : 10.32.40.213 and PORT : 12010
Client : Hello
```

**客户端程序**

## C

```
// C program to demonstrate socket programming
// as well as explicitly assigning a port number
// on Client Side
#include<stdio.h>
#include<sys/types.h>
#include<sys/socket.h>
#include<sys/un.h>
#include<string.h>
#include<netdb.h>
#include<netinet/in.h>
#include<arpa/inet.h>
#include<stdlib.h>

int main()
{
    // Two buffer are for message communication
    char buffer1[256], buffer2[256];
    struct sockaddr_in my_addr, my_addr1;
    int client = socket(AF_INET, SOCK_STREAM, 0);
    if (client < 0)
    printf("Error in client creating\n");
    else
        printf("Client Created\n");

    my_addr.sin_family = AF_INET;
    my_addr.sin_addr.s_addr = INADDR_ANY;
    my_addr.sin_port = htons(12000);

    // This ip address will change according to the machine
    my_addr.sin_addr.s_addr = inet_addr("10.32.40.213");

    // Explicitly assigning port number 12010 by
    // binding client with that port
    my_addr1.sin_family = AF_INET;
    my_addr1.sin_addr.s_addr = INADDR_ANY;
    my_addr1.sin_port = htons(12010);

    // This ip address will change according to the machine
    my_addr1.sin_addr.s_addr = inet_addr("10.32.40.213");
    if (bind(client, (struct sockaddr*) &my_addr1, sizeof(struct sockaddr_in)) == 0)
        printf("Binded Correctly\n");
    else
        printf("Unable to bind\n");

    socklen_t addr_size = sizeof my_addr;
    int con = connect(client, (struct sockaddr*) &my_addr, sizeof my_addr);
    if (con == 0)
        printf("Client Connected\n");
    else
        printf("Error in Connection\n");

    strcpy(buffer2, "Hello");
    send(client, buffer2, 256, 0);
    recv(client, buffer1, 256, 0);
    printf("Server : %s\n", buffer1);
    return 0;
}
```

输出:

```
Client Created
Binded Correctly
Client Connected
Server : Hello
```

**参考**:https://stackoverflow . com/questions/4118241/what-客户端-情况-需要-绑定

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。