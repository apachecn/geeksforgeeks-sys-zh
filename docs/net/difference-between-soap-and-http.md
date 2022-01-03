# 【SOAP 和 HTTP 的区别

> 原文:[https://www . geesforgeks . org/soap 和-http 的区别/](https://www.geeksforgeeks.org/difference-between-soap-and-http/)

**1。[简单对象访问协议(SOAP)](https://www.geeksforgeeks.org/basics-of-soap-simple-object-access-protocol/) :**
简单对象访问协议(SOAP)是节点间交换结构化数据的网络协议。它使用 XML 格式来传输消息。它工作在应用层协议之上，如 HTML 和用于符号和传输的 [SMTP](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) 。SOAP 允许进程在整个平台、语言和操作系统中进行通信，因为像 HTTP 这样的协议已经安装在所有平台上。

**2。 [HTTP](https://www.geeksforgeeks.org/http-full-form/) :**
HTTP 是 1989 年由欧洲核子研究中心(Cern)的蒂姆·伯纳斯·李(Tim Berners Lee)创建的应用层协议，目前它被用于网络上的大部分数据传输。它是在万维网上使用超文本文件进行数据通信的基础。该协议负责服务器在网络上发送信息时必须采取的行动。当一个网址被输入到浏览器中时，这个协议向服务器发送一个 HTTP 请求，然后一个 HTTP 响应被发送回浏览器。

**SOAP 和 HTTP 的区别:**

<center>

| 没有。 | 肥皂 | 超文本传送协议 |
| 1. | SOAP 代表简单对象访问协议。 | HTTP 代表超文本传输协议。 |
| 2. | 它是基于 XML 的，用于发送和接收消息。 | 它被用来在互联网上传递信息。 |
| 3. | 它支持网络套接字或 WS-Addressing、WS-Security、SwA。 | 它不支持网络套接字或 WS-Addressing、WS-Security、SwA。 |
| 4. | HTTP 是通过 TCP 和 IP 实现的。 | SOAP 是通过 HTTP。 |
| 5. | 它支持针对 WSDL 运行时检查。 | 它不支持针对 WSDL 的运行时检查。 |
| 6. | 它支持自动处理消息传输优化机制(MTOM)。 | 它也支持 MTOM，但是它必须使用 MIME 消息域，并且设计流程应该明确处理附件。 |
| 7. | 该协议的设计以数据为中心。 | 该协议的设计以文档为中心。 |
| 8. | 这是一个轻量级的数据交换协议。 | 它不像 SOAP 那样是轻量级的数据传输协议。 |

</center>