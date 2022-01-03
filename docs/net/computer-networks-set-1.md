# 计算机网络|第 1 集

> 原文:[https://www.geeksforgeeks.org/computer-networks-set-1/](https://www.geeksforgeeks.org/computer-networks-set-1/)

GATE CS 2012 考试中提出了以下问题。

**1)互联网栈中应用层的协议数据单元(PDU)为**
(A)段
(B)数据报
(C)报文
(D)帧

答案(C)
[互联网栈(或 TCP/IP)](http://en.wikipedia.org/wiki/Internet_protocol_suite) 中应用层的[协议数据单元](http://en.wikipedia.org/wiki/Protocol_data_unit)称为报文。

**2)以下哪种传输层协议用于支持电子邮件？**
(一)SMTP
(二)IP
(三)TCP
(四)UDP

答案(C)
电子邮件使用 [SMTP](http://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) 作为应用层协议。SMTP 使用 [TCP](http://en.wikipedia.org/wiki/Transmission_Control_Protocol) 作为传输层协议。

**3)在 IPv4 寻址格式中，c 类地址下允许的网络数量为**
(a)2^14
(b)2^7
(c)2^21
(d)2^24

答案(C)
在 C 类中，8 位为主机 Id 预留，24 位为网络 Id 预留。在这 24 个网络标识位中，前 3 位固定为 110。所以剩下的 21 位可以用于不同的网络。详见[本](http://en.wikipedia.org/wiki/Classful_network)。

**4)互联网服务提供商(ISP)拥有以下基于 CIDR 的 IP 地址块:245.248.128.0/20。互联网服务提供商希望将这一大块地址的一半给组织 A，四分之一给组织 B，同时保留其余的地址。以下哪一项是 A 和 B 的有效地址分配？**
(A) 245.248.136.0/21 和 245 . 248 . 128 . 0/22
(B)245 . 248 . 128 . 0/21 和 245 . 248 . 128 . 0/22
(C)245 . 248 . 132 . 0/22 和 245 . 248 . 132 . 0/21
(D)222

回答(A)
由于[路由前缀](http://en.wikipedia.org/wiki/Subnetwork)是 20，ISP 有 2^(32-20)或 2^12 地址。在这些 2^12 地址中，一半(或 2^11)地址必须提供给组织 a，四分之一(2^10)地址必须提供给组织 b。因此，组织 a 的路由前缀将是 21。对于 B，将是 22。如果我们看到问题中给出的所有选项，则只剩下选项(A)和(B)，因为只有这些选项具有相同数量的路由前缀。现在我们需要从选项(A)和(B)中进行选择。
要为组织 A 分配地址，ISP 需要从 245.248.128.0 中取出前 20 位，并将第 21 位固定为 0 或 1。同样，ISP 需要为组织 B 固定第 21 位和第 22 位，如果我们仔细查看选项(A)和(B)，可以看到组织 B 的第 21 位和第 22 位在两个选项中都被认为是 0。所以组织 A 的第 21 位必须是 1。现在取 245.248.128.0 的前 20 位和第 21 位为 1，我们得到组织 A 的地址为 245.248.136.0/21

**请参见**[**GATE Corner**](http://geeksquiz.com/gate-corner-2/)**查看往年所有论文/解答/说明、教学大纲、重要日期、笔记等。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。