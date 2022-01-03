# 计算机网络| AAA(认证、授权和计费)

> 原文:[https://www . geesforgeks . org/computer-network-AAA-authentication-authorization-and-accounting/](https://www.geeksforgeeks.org/computer-network-aaa-authentication-authorization-and-accounting/)

管理员可以通过控制台访问路由器或设备，但如果他坐在远离该设备的地方，则非常不方便。所以，最终，他必须远程访问那个设备。

但是由于远程访问可以通过使用一个 IP 地址来实现，因此，未经授权的用户可以使用相同的 IP 地址进行访问。因此，为了安全起见，我们必须进行身份验证。此外，设备之间交换的数据包应该加密，这样任何其他人都不能捕获敏感信息。因此，一个名为 AAA 的框架被用来提供额外的安全级别。

**AAA(认证、授权、计费)–**
AAA 是一个基于标准的框架，用于控制谁被允许使用网络资源(通过认证)，他们被授权做什么(通过授权)，以及捕获访问网络时执行的操作(通过计费)。

1.  **Authentication –** 
    The process by which it can be identified that the user, which wants to access the network resources, valid or not by asking some credentials such as username and password. Common methods are to put authentication on console port, AUX port, or vty lines. 

    作为网络管理员，如果有人想要访问网络，我们可以控制如何对用户进行身份验证。其中一些方法包括使用该设备(路由器)的本地数据库或向外部服务器(如 ACS 服务器)发送身份验证请求。要指定用于身份验证的方法，将使用默认或自定义的身份验证方法列表。

2.  **Authorization –** 
    It provides capabilities to enforce policies on network resources after the user has gained access to the network resources through authentication. After the authentication is successful, authorization can be used to determine what resources is the user allowed to access and the operations that can be performed. 

    例如，如果初级网络工程师(不应访问所有资源)想要访问设备，则管理员可以创建一个视图，该视图只允许用户执行特定命令(方法列表中允许的命令)。管理员可以使用授权方法列表来指定如何授权用户使用网络资源，即通过本地数据库或 ACS 服务器。

3.  **Accounting–**
    它提供了监视和捕获用户在访问网络资源时发生的事件的方法。它甚至监控用户访问网络的时间。管理员可以创建一个会计方法列表，以指定应该对什么进行会计处理，以及会计记录应该发送给谁。

**AAA 实现:** AAA 可以通过使用设备的本地数据库或使用外部 ACS 服务器来实现。

*   **local database –** If we want to use the local running configuration of the router or switch to implement AAA, we should create users first for authentication and provide privilege levels to users for Authorization. 
*   **ACS server –** This is the common method used. An external ACS server is used (can be ACS device or software installed on Vmware) for AAA on which configuration on both router and ACS is required. The configuration includes creating a user, separate customized method list for authentication, Authorization, and Accounting. 

    客户端或网络访问服务器(NAS)向 ACS 服务器发送身份验证请求，服务器根据用户提供的凭据决定是否允许用户访问网络资源。

**注意–**如果 ACS 服务器未能通过身份验证，管理员应在方法列表中提及使用设备的本地数据库作为备份，以实现 AAA。