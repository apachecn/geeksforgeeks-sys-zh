# Linux 中的 Netstat 命令

> 原文:[https://www.geeksforgeeks.org/netstat-command-linux/](https://www.geeksforgeeks.org/netstat-command-linux/)

Netstat 命令显示各种网络相关信息，如网络连接、路由表、接口统计、伪装连接、多播成员身份等。,

**一些实用的 netstat 命令示例:**

1.  **-a -all** : Show both listening and non-listening sockets. With the –interfaces option, show interfaces that are not up

    ```
    # netstat -a | more : To show both listening and 
    non-listening sockets.
    ```

    ![](img/3b352f942c10db5e6922e0412e618f7b.png)
    ![](img/baee10b9c38cd80d7ccd6c71f264e9e7.png)

2.  **List all tcp ports.**

    ```
    # netstat -at : To list all tcp ports.

    ```

    ![](img/277422e7ff734bec2b44b352eb640eab.png)

3.  **List all udp ports.**

    ```
    # netstat -au : To list all udp ports.

    ```

    ![](img/b4a2bcc3812a9abb74aad00878b78ed1.png)

4.  **List only listening ports.**

    ```
    # netstat -l : To list only the listening ports.

    ```

    ![](img/50cd9353160c50940ce78906789d6411.png)

5.  **List only listening TCP ports.**

    ```
    # netstat -lt : To list only the listening tcp ports.

    ```

    ![](img/7b713eca136d43ded5eb11c43a9f2ef8.png)

6.  **List only listening UDP ports.**

    ```
    # netstat -lu : To list only the listening udp ports.

    ```

    ![](img/905b47e3a7951a09035c74fc07277886.png)

7.  **List only the listening UNIX ports**

    ```
    # netstat -lx : To list only the listening UNIX ports.

    ```

    ![](img/2c85b05d42ca90b148072f951fbc87fc.png)

8.  **List the statistics for all ports.**

    ```
    # netstat -s : To list the statistics for all ports.

    ```

    ![](img/f38930f36e5da81c644d14d26dc3e95b.png)

9.  **List the statistics for TCP (or) UDP ports.**

    ```
    # netstat -st(TCP) : To list the statistics for TCP ports.

    ```

    ![](img/f62c6ab6eae7db74a01d667d2fdfdc81.png)

    ```
    # netstat -su(UDP) : List the statistics for UDP ports.

    ```

    ![](img/4b1c4ac72dd01a6a45abdc42bc0d1b4c.png)

10.  **Display PID and program names in the output.**

    ```
    # netstat -pt : To display the PID and program names.

    ```

    ![](img/5fc8bb2309925da771d57101c70b5c9a.png)

11.  **Print the netstat information continuously.**

    netstat 将每隔几秒钟连续打印信息。

    ```
    # netstat -c : To print the netstat information continuously.

    ```

    ![](img/438cc6ba58c5846ad6ad06af04cc0d09.png)

12.  **The non-supportive address families in the system.**

    ```
    # netstat --verbose : To get the non-supportive
    address families in the system.

    ```

    ![](img/c4bb31245971482a5c32852c2c21281a.png)

    ```
    At the end, we have something like this : 

    ```

    ![](img/6545ccbfaf2c2bc5ea4012b1fffb3445.png)

13.  **The kernel routing information.**

    ```
    # netstat -r : To get the kernel routing information.

    ```

    ![](img/608f76169933fd829a8fcfbb5b91c2d6.png)

14.  **The port on which a program is running.**

    ```
    # netstat -ap | grep ssh : To get the port
    on which a program is running.

    ```

    ![](img/7c3718573f502d4bdc8b2d8ccc5dd8c8.png)

15.  **Which process is using a particular port:**

    ```
    # netstat -an | grep ':80' : To get the process
    which is using the given port.

    ```

    ![](img/a3328ef64e9e996f9ccd536ef7616d63.png)

16.  **List of network interfaces.**

    ```
    # netstat -i : To get the list of network interfaces.

    ```

    ![](img/af51a2da10076a51770ae4fd9076e450.png)

    ```
    Display extended information on the interfaces 
    (similar to ifconfig) using netstat -ie:

    # netstat -ie : To display extended information 
    on the interfaces

    ```

    ![](img/be26f4d203bab12e38d430f5cf74ef29.png)

     **参考:**
    [netstat](http://man7.org/linux/man-pages/man8/netstat.8.html)Linux 手册页

    本文由 **[基什莱·维尔马](https://www.linkedin.com/in/kishlayverma/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。