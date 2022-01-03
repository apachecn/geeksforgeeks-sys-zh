# 网络和网络通信过程

> 原文:[https://www . geesforgeks . org/networks-and-process-of-network-communication/](https://www.geeksforgeeks.org/networks-and-process-of-network-communications/)

如果有人感兴趣或者愿意加入[网络安全](https://www.geeksforgeeks.org/difference-between-cyber-security-and-information-security/)的世界。他/她必须熟悉[网络通信](https://www.geeksforgeeks.org/network-and-communication/)是如何发生的。因为网络安全分析师的基本工作是跟踪网络上发生的事件。事故记录存储在涉及网络的系统的日志文件中。这些日志文件包含网络协议操作的日志。通过地址，我们可以轻松识别哪些主机连接到组织，或者有多少远程主机通过互联网连接。

借助日志文件中的这些地址，我们可以轻松识别哪些主机已连接或试图连接到组织中的主机。协议的其他地址可以提供网络连接试图做什么的信息，以及这种行为对于连接是正常的、可疑的还是危险的。如果有，分析人员会追踪该威胁，以确保组织及其数据的安全。我们必须了解正常网络是如何工作的，这样我们才能捕捉到黑客或网络中任何可疑软件造成的任何异常行为。网络协议作为网络的大脑工作，网络服务提供我们想要使用网络执行的任务。

### 网络类型

这些网络有不同的范围，从 2 台设备到连接在一个网络上的数百万台设备。一些类型的网络如下:

1.  **Small home network-** It connects several interconnected devices (1-10) and the Internet.
2.  **Small office/home office network (SOHO)-** Small office/home office or SOHO network enables computers in home offices or remote offices to connect to corporate networks or access centralized shared resources.
3.  **Medium-large network-** This type of network is used by institutions or organizations or schools with hundreds to thousands of interconnected devices from many locations.
4.  **World Wide Web-** It is the largest existing interconnected network in the world. It is a collection of private and non-private networks, which we basically call a network of networks.

### 客户机-服务器通信

顾名思义，客户需要一些东西，而服务器意味着服务的人。服务器是安装了软件的设备，使计算机能够向这些网络上的终端设备提供信息。服务器可以是单用途的，只提供像网页这样的单一信息，也可以是多用途的，如提供网页、电子邮件、文件传输。

网络中所有连接的设备都参与网络通信，这些设备被归类为 **HOST** 。主机是网络的端点或节点。每当我们在网络浏览器上搜索东西时，网络浏览器就像网络客户端一样，试图连接到网络服务器，或者当我们使用电子邮件服务时，电子邮件客户端试图连接到电子邮件服务器。基本上，对于网络上的不同服务，存在不同的服务器。客户端计算机安装软件，如网络浏览器、电子邮件、文件传输，以显示从服务器获得的数据。

### 典型会话:

在典型的网络中，用户连接到学校或学院的网络，或者某个组织试图连接到该学院或组织或世界某个地方的服务器。在这个会话中，它建立了许多连接。让我们看看这些会议的一些例子。

*   **Student Conversations-** Let's look at an example. Archie is a clever student in his class. His teacher assigned him an assignment, which he must submit until the end of the day. So Archie took his tablet, connected to **school network** and searched for his homework. After clicking the search button, a radio wave will be generated, and the search data of Archit will be used as a binary string with the device address, so that the information can be returned to the device. Therefore, the data is wirelessly submitted to the school network. Then, the search is converted into **electric signal** and spread through the school wired network until they reach the place where the school network is connected to **Internet service provider (ISP) network.** All the searched data flows to ISP together with thousands of data on the optical network, and this only happens in a few seconds.
*   **Surgeon's Meeting-** Dr. Sinhale is a great surgeon, but during the operation, he often needs to consult the radiologist for the operation. His hospital uses a special technology called T2 Cloud T3\. Cloud allows hospitals to store patient reports, MRI and X-rays in a centralized location that can be accessed through the Internet. Whenever X-ray and MRI are taken, it will be digitized into computer data, and then the hospital computer will send it to the cloud service. Security is also a problem, so data is sent in encrypted form. When the encrypted data is transmitted to the data center of the cloud service provider through the Internet, it cannot be intercepted and read. The data is also addressed so that it can be transmitted from the cloud data center to the right service. In this way, Dr. Sinhale can work with experts from different places, share patients' reports and images and discuss them.