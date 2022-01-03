# 什么是 CDP(思科发现协议)攻击？

> 原文:[https://www . geesforgeks . org/what-are-CDP-Cisco-discovery-protocol-attachments/](https://www.geeksforgeeks.org/what-are-cdp-cisco-discovery-protocol-attacks/)

CDP 是思科设备使用的第 2 层协议；它用于发现网络中其他直接连接的思科设备，这允许设备自动配置它们的连接，因此它简化了连接和配置。

一般来说，大多数思科设备都启用了[](https://www.geeksforgeeks.org/what-is-cisco-discovery-protocol-cdp/)**。由于路由器不循环它，所以 CDP 数据通过定期广播传输，定期广播保存在本地的思科设备 CDP 表中。**

**CDP 数据库由大量关于设备的数据组成，如功能、IP 地址、原生 [VLAN、](https://www.geeksforgeeks.org/types-of-virtual-lan-vlan/)软件版本、平台版本等。当所有这些信息通过受损的系统落入恶意用户手中时，他们可以利用这些信息找到攻击网络的漏洞。通常作为 DoS 攻击执行。恶意用户还可以制作伪造的 CDP 数据包，并将其转发给其他设备，因为 CDP 未经身份验证。**

### ****可能的攻击:****

*   ****Telnet 攻击:** [Telnet](https://www.geeksforgeeks.org/introduction-to-telnet/) 是一种不安全的协议，恶意用户可以使用该协议远程访问网络设备。然后，他们可以对交换机上的虚拟终端发起暴力攻击来破解密码。**
*   ****暴力密码攻击:**对于这种攻击，恶意用户使用一个常见密码列表以及一个可以通过使用字典列表中的每个单词来建立 telnet 会话的程序。如果密码没有被字典列表攻击破解，那么在下一步的暴力攻击中，恶意用户可能会使用组合攻击来破解密码。**
*   ****Telnet DoS 攻击:** Telnet 可以用于 DoS 攻击，在这种情况下，恶意用户可以利用交换机上运行的 Telnet 服务器软件中的一个 bug，该 bug 可以使 Telnet 服务不可访问。这可以与其他各种直接攻击一起使用，以防止管理员在攻击期间远程访问重要设备和交换机管理。**
*   ****CVE-2020-3110 或思科视频监控 8000 系列 IP 摄像机中的 RCE 和 DoS 漏洞 CDP:** 恶意用户可以通过向受影响的 IP 摄像机转发伪造的 CDP 数据包来利用此漏洞，此漏洞允许未经身份验证的用户远程执行代码，还可以允许他们意外地重新加载受影响的摄像机，从而导致 DoS 情况。**
*   ****CVE-2020-3111 或思科 IP 电话的 RCE 和拒绝服务漏洞:**这可能允许恶意未授权用户以 root 权限执行 RCE 攻击，还可能允许他们重新加载任何受影响的 IP 电话，从而导致类似拒绝服务的情况。**
*   ****CVE-2020-3118 或思科 IOS XR 软件 CDP 的格式字符串漏洞:**针对思科 IOS XR 软件的 CDP 执行中的此漏洞可能会让未经授权的恶意用户执行任意代码，还可能导致受影响设备上的重新加载，从而导致堆栈溢出。**

### ****防范 CDP 攻击:****

**为了防止 CDP 攻击，可以考虑以下几点。**

***   Users can disable cdp on devices or ports that do not need CDP by using the "Do not run CDP" command.*   To prevent violent password attacks, users should frequently change their passwords to strong passwords.*   Acl ( [access control list](https://www.geeksforgeeks.org/access-lists-acl/) ) can be used to restrict access to virtual terminal lines.*   Users should disable CDP on routers connected to external networks.**

### ****检测:****

**在 CDP 监视器的帮助下可以监视 CDP 的变化，这个 CDP 程序有助于发现网络上的 CDP 变化；它可以通过提示消息框通知用户，也可以发送警告电子邮件。由于可以从 CDP 监视器发送自定义的 CDP 数据包，因此它也有助于 CDP 欺骗攻击。**