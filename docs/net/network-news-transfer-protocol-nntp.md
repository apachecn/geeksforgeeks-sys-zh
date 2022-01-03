# 网络新闻传输协议(NNTP)

> 原文:[https://www . geesforgeks . org/network-news-transfer-protocol-nntp/](https://www.geeksforgeeks.org/network-news-transfer-protocol-nntp/)

**网络新闻传输协议(NNTP)** 是 UseNet 的底层协议，UseNet 是一个世界性的讨论系统，其中包含被称为新闻的帖子或文章。网络新闻传输协议用于将新闻从一个网络传输到另一个网络。它是专门为传递新闻/文章而设计的。网景、Opera 和 Internet Explorer 等浏览器都包含 NNTP 客户端，或者一个名为 newsreader 的特殊应用程序可以用作 NNTP 客户端。NNTP 服务器公司管理着新闻集团的全球网络。

**历史:**
新闻组最初使用的是 Unix 到 Unix 复制协议(UUCP)。在这个协议中，服务器复制本地磁盘上的所有新闻，海报和读者登录这些服务器直接从本地磁盘访问文章。随着互联网使用的增加，有必要使个人计算机能够访问 UseNet。因此，NNTP 的设计思路类似于[简单邮件传输协议(SMTP)](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) 。它是由包括布雷恩·坎特、菲尔·拉普利、桑特在内的多位投稿人制作的。奥·巴伯，埃里克·费尔。Brain Kantor 和 Phil Lapsley 于 1986 年 3 月编写了 RFC 977“网络新闻传输协议”。

**工作:**
NNTP 是一套客户端/新闻阅读器与服务器交互检索新闻组的规则。NNTP 客户端使用“ARTICLE”之类的命令来检索一篇文章，或者使用“NEWS”来检索整个新闻组，从而与服务器进行通信。这些命令大多由新闻阅读器软件直接解释，该软件发送和接收来自服务器的信号。

端口 563 或 119 由 NNTP 客户端/新闻阅读器使用。Post 433 由服务器使用，因此它也被称为 NNSP。

新闻组由多台服务器托管。这个分布式网络中的服务器是简单的对等体，它们拥有与它们共享文章的其他对等体的信息。一篇新文章被添加到服务器，服务器定期发送添加的文章到它的对等服务器。服务器不需要存储网络上的所有新闻组，它可以选择存储哪些新闻组，前提是它的对等方拥有这些新闻组。如果对等方没有，那么它可以找到拥有这些新闻组的新对等方。任何人都可以使用像 Apache James 和 Leaf node 这样的软件来设置个人新闻组。