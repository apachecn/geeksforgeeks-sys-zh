# 计算机网络中的 MAC 过滤

> 原文:[https://www . geesforgeks . org/MAC-计算机网络过滤/](https://www.geeksforgeeks.org/mac-filtering-in-computer-network/)

网络**适配器**有两种。有线适配器允许我们通过计算机中的以太网建立到调制解调器或路由器的连接，而无线适配器识别并连接到远程热点。每个适配器都有一个独特的标签，称为媒体访问控制地址，用于识别和验证计算机。Mac 地址以 00:00:00:00:00:00:00 或 00-00-00-00-00-00-00 的格式显示。

**关于和工作–**
MAC 过滤是一种基于访问控制的安全方法。在这种情况下，每个地址都被分配了一个 48 位地址，用于确定我们是否可以访问网络。它有助于列出您在无线网络中需要的一组允许的设备，以及您不想在无线网络中使用的拒绝的设备。它有助于防止不必要的网络访问。在某种程度上，我们可以根据某些计算机的 MAC 地址来列出它们的拒绝列表或允许列表。我们可以将过滤器配置为只允许连接到白名单中包含的设备。白名单比拒绝名单提供更高的安全性，因为路由器只允许访问选定的设备。

它用于具有多个接入点的企业无线网络，以防止客户端相互通信。接入点可以配置为只允许客户端与默认网关通话，而不允许其他无线客户端通话。它提高了访问网络的效率

路由器允许在其网络接口中配置允许的媒体访问控制地址列表，允许您选择哪些设备可以连接到您的网络。路由器具有许多旨在提高网络安全性的功能，但并非所有功能都有用。媒体访问控制看似有利，但也有一定的缺陷。
在无线网络中，拥有适当凭证(如 SSID 和密码)的设备可以向路由器进行身份验证，并加入网络，从而获得 IP 地址并访问互联网和任何共享资源。

媒体访问控制地址过滤增加了额外的安全层，可以根据商定的地址列表检查设备的媒体访问控制地址。如果客户端的地址与路由器列表中的地址匹配，则授予访问权限，否则它不会加入网络。

**Mac 过滤的步骤–**

1.  设置允许的设备列表。只有列表中的那些媒体访问控制地址将由 DHCP 提供服务。
2.  设置被拒绝设备的列表。拒绝列表中的媒体访问控制地址不会被 DHCP 服务器授予。
3.  如果媒体访问控制地址同时在允许和拒绝列表中，则该服务将被拒绝。

要启用允许、拒绝或两种设备的列表，请执行以下步骤。

1.  转到 DHCP 控制台，右键单击 IPv4 节点，然后单击属性。
2.  使用筛选器选项卡上的当前筛选器配置详细信息，并通过选择启用允许列表来使用允许列表，通过选择启用拒绝列表来使用拒绝列表。
3.  单击确定并保存更改。

**更新 MAC 过滤–**
请注意，如果在无线路由器上启用了 MAC 过滤，并且没有输入 MAC 地址，则连接到路由器的无线设备将无法连接
如果出于故障排除目的已经禁用了 Mac 过滤，我们不需要启用该功能。路由器制造商在这一领域的知识更丰富。

**做什么–**

1.  转至您的路由器设置。
    在路由器的设置中，找到选项卡或设置“媒体访问控制过滤”这可以在路由器的“无线”或“无线安全”选项中找到。在某些路由器中，媒体访问控制过滤也可以称为“媒体访问控制地址控制”、“地址保留”或“无线媒体访问控制认证”

2.  您需要将任天堂系统的媒体访问控制地址添加到允许的设备列表中，并在媒体访问控制过滤打开或启用时保存或应用此更改。如果您不希望网络打开媒体访问控制过滤，请将其关闭或禁用。

**注意–**您可以通过无线>无线媒体访问控制过滤器页面在 Linksys 无线-N 路由器上启用媒体访问控制过滤器。我们可以通过高级>安全>访问控制在 NETGEAR 路由器上做到这一点，并通过高级>网络过滤器在 D-Link 路由器上做到这一点。S

**缺点–**

*   这既耗时又乏味，尤其是如果您有许多支持无线网络的设备，因为您需要为每台设备获取媒体访问控制地址。每当我们想要购买新的计算机或移动设备，或者每当我们想要授予新设备权限时，都应该修改允许的设备列表。
*   应为电脑添加两个媒体访问控制地址，一个是有线适配器，一个是无线适配器。
*   它无法抵御知道自己在做什么的黑客。但是你可以用它来禁止孩子访问，因为他们没有足够的知识。
*   这会降低网络的安全性，因为现在黑客根本不用破解你的 WPA2 加密密码。

**安全性–**
通过使用 Wireshark 检查数据包，拥有像 Kali Linux 这样的工具集的黑客可以访问网络，因为他们可以获得允许设备的 MAC 地址，然后他们可以将设备的 MAC 地址更改为允许的 MAC 地址，并假扮该设备进行连接。他们可以使用“去验证”或“去安全”攻击，强制断开设备与无线网络的连接，或者使用空中播放向客户端发送解除关联数据包，然后在设备所在的位置进行连接。然而，无线客户端的媒体访问控制地址不能真正改变，因为它们被编码在硬件中。但是一些批评家指出 MAC 地址是可以伪造的。攻击者只需要知道其中一个有效地址。他们不需要破解加密就可以访问你的网络，也不需要破解你的 WPA2 加密密码。他们只需要假装是一台可信的计算机。

MAC 过滤将阻止普通黑客获得网络访问权限。大多数计算机用户不知道如何欺骗他们的媒体访问控制地址，更不用说找到路由器的批准地址列表了。与域过滤器不同，它们不会阻止流量流经网络。

一个普遍的疑问是，如果黑客不能连接到网络，他们如何获得我们的媒体访问控制地址。无线网络的一个弱点是，即使有 WPA2 加密网络，这些数据包上的媒体访问控制地址也没有加密。这意味着任何安装了网络嗅探软件并在您的网络范围内安装了无线网卡的人都可以轻松获取与您的路由器通信的所有媒体访问控制地址。

**问题的其他解决方案–**

*   控制想要连接到您网络的外部人员的更好的解决方案是使用来宾 Wi-Fi 网络。它将允许他们让其他人连接到您的网络，但不会让他们看到您家庭网络上的任何内容。您可以购买一台便宜的路由器，并使用单独的密码和单独的 IP 地址范围将其连接到您的网络。
*   WPA2 加密就足够了，因为它很难破解。但关键是要有一个又强又长的密码。如果有人破解了你的 WPA2 加密，他们不需要努力欺骗 MAC 过滤。如果攻击者对媒体访问控制地址过滤感到困惑，他们将无法破解您的加密。