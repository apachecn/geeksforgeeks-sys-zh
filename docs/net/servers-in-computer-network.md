# 计算机网络中的服务器

> 原文:[https://www.geeksforgeeks.org/servers-in-computer-network/](https://www.geeksforgeeks.org/servers-in-computer-network/)

在计算中，**服务器**是计算机**程序或设备**，其为作为其他程序或设备的被叫客户端提供功能。这种架构被称为**客户端-服务器模型**。单个整体计算分布在多个进程或设备上。服务器可以提供各种称为服务的功能。这些服务包括在多个客户端之间共享数据或资源，或者为一个客户端执行计算。单个服务器可以服务多个客户端，单个客户端可以使用多个服务器。客户端进程可以在同一设备上运行。它还可以通过网络连接到服务器，在不同的设备上运行。服务器示例可以包括数据库服务器、邮件服务器、打印服务器、文件服务器、网络服务器、应用服务器和游戏服务器。

最常见的客户端-服务器系统是通过**请求-响应模型**实现的。，即客户端向服务器发送请求。在这个模型中，服务器执行一些操作，并将响应发送回客户端，通常带有结果或确认。将计算机指定为服务器级硬件意味着它专用于在其上运行服务器。这意味着它比标准的个人电脑更强大、更可靠。但是大型计算集群可能由许多相对简单、可替换的服务器组件组成。

**服务器类型及其应用:**

1.  **Application server –** 
    These servers hosts web apps (computer programs that run inside a web browser) allowing users in the network to run and use them preventing the installation a copy on their own computers. These servers need not be part of the World Wide Web. There clients are computers with a web browser. 
2.  **Catalog server –** 
    These servers maintains an index or table of contents of information that can be found across a large distributed network. Distributed network may include computers, users, files shared on file servers, and web apps. Examples of catalog servers are Directory servers and name servers. Their clients are any computer program that needs to find something on the network. Example can be a Domain member attempting to log in, an email client looking for an email address, or a user looking for a file 
3.  **Communications server –** 
    These servers maintains an environment needed for one communication endpoint to find other endpoints and then communicates with them. These servers may or may not include a directory of communication endpoints and a presence detection service, depending on the openness and security parameters of the network. Their clients are communication endpoints. 
4.  **Computing server –** 
    These servers share vast amounts of computing resources which include CPU and random-access memory over a network. Any computer program that needs more CPU power and RAM than a personal computer can probably afford can use these types of servers. The client must be a networked computer to implement the client–server model which is necessity. 
5.  **Database server –** 
    These servers maintains and shares any form of database over a network. A database is a organized collections of data with predefined properties that may be displayed in a table. Clients of these servers are spreadsheets, accounting software, asset management software or virtually any computer program that consumes well-organized data, especially in large volumes. 
6.  **Fax server –** 
    These severs share one or more fax machines over a network which eliminates the hassle of physical access. Any fax sender or recipient are the clients of these servers. 
7.  **File server –** 
    Shares files and folders, storage space to hold files and folders, or both, over a network Networked computers are the intended clients, even though local programs can be clients 
8.  **Game server –** 
    These servers enables several computers or gaming devices to play multiplayer games. Personal computers or gaming consoles are their clients. 
9.  **Mail server –** 
    These servers makes email communication possible in the same way as a post office makes snail mail communication possible. Clients of these servers are senders and recipients of email 
10.  **Print server –** 
    These severs share one or more printers over a network which eliminates the hassle of physical access. Their clients are computers in need of printing something. 
11.  **Proxy server –** 
    This server acts as an intermediary between a client and a server accepting incoming traffic from the client and sending it to the server. Reasons to use a proxy server includes content control and filtering, improving traffic performance, preventing unauthorized network access or simply routing the traffic over a large and complex network. There clients are any networked computer. 
12.  **Web server –** 
    These servers hosts web pages. A web server is responsible for making the World Wide Web possible. Each website has one or more web servers. There clients are computers with a web browser.