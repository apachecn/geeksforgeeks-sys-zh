# 当我们输入网址时会发生什么

> 原文:[https://www . geesforgeks . org/what-what-what-当-we-type-a-url/](https://www.geeksforgeeks.org/what-happens-when-we-type-a-url/)

[URL](https://www.geeksforgeeks.org/url-full-form/) 代表统一资源定位符。网址是你可以在浏览器地址栏中找到的网站地址。它指的是互联网上的资源，可以是图像、超文本页面、音频/视频文件等。

**示例:**

```
https://practice.geeksforgeeks.org/ 
```

**什么是 [DNS](https://www.geeksforgeeks.org/domain-name-server-dns-in-application-layer/) :**
DNS 是域名系统的简称。像电话簿一样，域名系统维护和映射网站的名称，即网址，以及它链接到的特定 IP 地址。互联网上的每个网址都有一个唯一的 IP 地址，该地址是托管所请求网站的服务器的计算机的地址。

**当我们输入网址时会发生什么的步骤:**

1.  浏览器检查缓存中的 DNS 条目，找到网站对应的 [IP 地址](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)。
    寻找后续缓存。如果在一个中没有找到，则继续检查下一个，直到找到为止。
    *   浏览器缓存
    *   操作系统缓存
    *   路由器缓存
    *   ISP 缓存
2.  如果在缓存中找不到，ISP(互联网服务提供商)的 DNS 服务器将启动 DNS 查询，以查找承载域名的服务器的 IP 地址。
    使用包含请求的信息内容和目的地 IP 地址的小数据包发送请求。
3.  浏览器使用同步(SYN)和确认(ACK)消息启动与服务器的 [TCP(传输控制协议)](https://www.geeksforgeeks.org/tcp-and-udp-in-transport-layer/)连接。
4.  浏览器向网络服务器发送 [HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) 请求。获取或发布请求。
5.  主机上的服务器处理该请求并发回响应。它以某种格式组装响应，如 JSON、 [XML](https://www.geeksforgeeks.org/xml-basics/) 和 HTML。
6.  服务器发送一个 HTTP 响应以及响应的状态。
7.  浏览器显示 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 内容
8.  最后，完成。