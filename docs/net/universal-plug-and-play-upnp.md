# 通用即插即用(UPnP)

> 原文:[https://www.geeksforgeeks.org/universal-plug-and-play-upnp/](https://www.geeksforgeeks.org/universal-plug-and-play-upnp/)

**通用即插即用(UPnP)** 是一种网络协议或一组网络协议，支持个人电脑、WiFi、移动设备、打印机等设备。为了共享服务和数据以及娱乐目的，发现彼此并建立连接。UPnP 旨在用于住宅网络。UPnP 可以被认为是即插即用的扩展，它使用户能够将设备直接连接到计算机，而无需对设备或计算机进行任何手动配置。

UPnP 允许像打印机、个人电脑、移动设备等家用电器之间的直接联网。它使用既定的行业标准协议，如 [TCP/IP](https://www.geeksforgeeks.org/tcp-ip-model/) 、XML、简单对象访问协议(SOAP)[UDP](https://www.geeksforgeeks.org/user-datagram-protocol-udp/)、 [DHCP(动态主机配置协议)](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/)、 [DNS(域名系统)](https://www.geeksforgeeks.org/domain-name-server-dns-in-application-layer/)。UPnP 技术最初是由 UPnP 论坛推广的，该论坛是由各种供应商发起的。

**工作:**
UPnP 假设设备与[互联网协议(IP)寻址](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)兼容，用于使用其上构建的协议，如[超文本传输协议(HTTP)](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) 、[可扩展标记语言(XML)](https://www.geeksforgeeks.org/xml-basics/) 、[传输控制协议(TCP)](https://www.geeksforgeeks.org/tcp-ip-model/) 、[用户数据报协议(UDP)](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) 。它使用这些协议来通告设备的存在和数据传输。它使用 UDP 上的端口 1900。

*   **寻址:**

1.  UPnP 使用 IP 寻址。因此，当它启动时，它充当[动态主机配置协议(DHCP)](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) 客户端，为自己分配一个 IP 并搜索 DHCP 服务器。
2.  如果没有找到 DHCP 服务器，设备会使用名为 AutoIP 的过程为自己分配一个 IP，该过程会为其本地网络分配一个唯一的 IP。
3.  如果在 DHCP 事务期间，设备通过域名服务器(DNS)获得域名，它将使用该域名，否则它将使用其 IP。

*   **Simple Service Discovery Protocol (SSDP):**
    SSDP is the protocol used by UPnP devices to discover each other.
    1.  当设备被添加到网络时，它允许设备通过发送 SSDP 活消息向网络上的其他设备通告它的服务。
    2.  SSDP 还允许设备被动收听来自网络上其他设备的 SSDP 活动消息。
    3.  当两台设备发现对方时，会交换一条发现消息，其中包含设备类型及其服务等基本信息。*   **Device Description:**
    When devices discover each other, for the devices to learn more about each other they exchange information in XML format. These messages contain information like Manufacturer name, Model Name, Manufacturer Websites, services provided by device, parameters or arguments to be passed to the device for a service, etc.*   **Service Calls:**
    After getting information about the device and it’s services, the control point can call for the service to the URL provided by manufacturer, this call is much like a programming function call. This is done by a protocol known as Simple Object Access Protocol(SOAP) which passes XML messages.*   **General Event Notification Architecture (GENA):**
    GENA is the architecture used for event notification in UPnP. This is used by services to respond to service calls. A control point can subscribe to a device’s event notification, each device has a set of Model variables, when there is a change in them, control point gets notified. These messages are also sent in XML format.*   **Presentation:**
    A device may contain a manufacturer website URL for presentation, this can be used by a control point to retrieve information and also can be used by the user to customize the device settings on a web browser.

    **UPnP 的优势:**

    1.  它可以用于穿越网络地址转换或防火墙打孔。
    2.  它允许真正的即插即用兼容性。
    3.  它得到了各种大厂商和公司的支持，如微软和英特尔，这使它成为行业标准。
    4.  它是家庭设备和网络的理想架构。

    **UPnP 的缺点:**

    1.  控制点不需要任何身份验证，因此您计算机上的任何程序都可以请求转发一个 UPnP 端口
    2.  UPnP 没有正式的实现，因此每个路由器都有自己的实现，许多实现都有 bug，或者给恶意软件一个开放的通道
    3.  您网络上的任何恶意程序都可以使用 UPnP，就像合法程序使用它一样。