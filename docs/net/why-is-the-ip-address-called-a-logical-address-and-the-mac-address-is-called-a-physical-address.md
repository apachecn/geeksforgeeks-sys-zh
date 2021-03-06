# 为什么 IP 地址叫“逻辑”地址，MAC 地址叫“物理”地址？

> 原文:[https://www . geesforgeks . org/为什么 ip 地址被称为逻辑地址，mac 地址被称为物理地址/](https://www.geeksforgeeks.org/why-is-the-ip-address-called-a-logical-address-and-the-mac-address-is-called-a-physical-address/)

让我们试着深刻理解，为什么 IP 地址被称为“逻辑”地址，而 MAC 地址被称为“物理”地址。

**什么是 MAC？**

*   媒体访问控制也称为机器访问控制，就像一种序列号，分配给网络适配器的每个组件，没有两个网络适配器拥有相同的媒体访问控制地址。

**计算机网络中的媒体访问控制地址或物理地址:**
该媒体访问控制也称为物理地址或硬件地址，因为它字面上标识了一个硬件项目。这些媒体访问控制地址使用 3 种数字系统，并且都遵循相同的格式。这些地址可以是“通用管理”或“本地管理”。

只有制造商为设备分配了“通用管理”物理地址。这些地址被称为“老化地址”。路由器、智能手机、平板电脑实际上，任何包含网卡的设备都可以通过 Wifi 或以太网连接，并且都有一个唯一的 Mac 地址。

这个媒体访问控制地址就像每个设备的指纹，这意味着它们像物理标识符一样识别每个设备，就像对人类来说指纹被认为是认证的标准来源一样。这些媒体访问控制地址由电气和电子工程学会(IEEE)定义和管理。在媒体访问控制地址中，前 3 个八位字节标识发布标识符的组织，称为组织标识符。

由于媒体访问控制地址从根本上处理识别网络组件的物理细节，所以它们也有一个昵称“物理地址”，这是正确的，因为它们的基本操作是识别网络的物理或硬件组件，如

**MAC 地址的优势:**
网卡的 MAC 地址可以被路由器用来给电脑分配一个静态 IP，字面意思就是路由器可以被配置成检测 MAC 地址的存在。媒体访问控制地址可用于限制对计算机网络的访问，以防止外部设备未经授权访问网络。

与 IP 地址相比，路由器的 MAC 地址可以更准确地定位人。一些互联网服务提供商使用这个媒体访问控制地址来验证他们的用户。

**什么是 IP 地址？**
IP 地址是用于识别互联网或本地网络中设备的唯一地址，IP 是互联网协议的首字母缩略词，互联网协议是管理网络通信中传输的数据的一组规则。IP 地址可以被称为标识符，它使信息能够在网络通信中传输。

**计算机网络中的 IP 地址:**
IP 地址是一串数字，由句点分隔的数字生成。这些 IP 地址表示为一组 4 位数字。这些 ip 地址的范围从 0.0.0.0 到 255.255.255.255，每个设备都获得一个逻辑计算的 IP 地址，该 IP 地址在网络通信中充当该特定设备的标识符。

该 IP 地址不是随机生成的，而是由互联网号码分配机构(IANA)数学生成的，该机构是互联网名称与号码分配机构(ICANN)的一个内部部门。

**IP 地址的优势:**
专用 IP 地址的使用减少了服务器的停机时间。这些 IP 地址可以有效地远程访问网络通信中的设备。

IP 地址有助于使设备作为文件传输协议服务器运行。IP 地址提供了一层防止 IP 禁止的保证，这意味着通过控制网络攻击的风险来严格监控外部访问请求。

**结论:**
我们从这篇文章的主要议程是了解为什么 MAC 地址被称为“物理地址”，IP 地址被称为“逻辑地址”。

媒体访问控制地址被称为“物理地址”，因为它是网络通信中分配给硬件组件的唯一标识符，它被设计为一种指纹来物理识别组件。

另一方面，IP 地址被称为逻辑地址，因为它是为识别网络通信中的设备而进行逻辑计算的。

媒体访问控制地址和 IP 地址的主要目的是识别网络组件，但唯一的区别是媒体访问控制地址工作是识别硬件组件，而 IP 地址识别逻辑组件，通过考虑这种工作方式，它们的昵称分别创建。