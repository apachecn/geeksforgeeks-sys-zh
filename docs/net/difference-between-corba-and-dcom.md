# 【CORBA 和 DCOM 的区别

> 原文:[https://www . geesforgeks . org/difference-on-CORBA-and-DCOM/](https://www.geeksforgeeks.org/difference-between-corba-and-dcom/)

CORBA 和 DCOM 是两种处理分布式对象的中间件解决方案。这些解决方案提供了对分布式计算对象更好的控制，但问题是哪种技术将成为标准。让我们看看他们之间的详细比较。

**1。公共对象请求代理架构(CORBA) :**
公共对象请求代理架构是分布式对象的详细规范。它是由对象管理组引入的。该体系结构描述了一种具有独立于平台的对象总线的语言，称为 ORB(对象请求代理)。这些使对象能够透明地发出请求并接收来自远程对象的响应。这也支持处理并发和处理异常。

**2。分布式组件对象模型(DCOM) :**
分布式组件对象模型是微软以其 Window NT 作为捆绑包推出的。DCOM 在 Windows 中使用了 Internet Explorer，这有望吸引开发人员使用他们拥有的东西，而不是购买。DCOM 也是一个对象总线，有助于对象接口的规范和调用支持分布式环境的动态对象导出。这支持代码共享，并要求使用对象接口声明共享代码。

**CORBA 与 DCOM 的区别:**

<center>

| 的基础 | 公共对象请求代理结构（同 Common Object Request Breaker Architecture） | DCOM |
| --- | --- | --- |
| 介绍人 | 它是由对象管理小组推出的 | 它是由微软推出的 |
| 关注 | 首先关注企业，然后是桌面 | 首先关注桌面，然后关注企业 |
| 平台 | 它在 Unix、Windows 和 Macintosh 上都有。 | 它可与视窗 NT 一起使用，并完全支持所有版本的视窗、Unix 和麦金塔 |
| 对象实现 | 只要 IDL 可以映射到这种语言，就支持各种语言 | 许多语言都支持 Java、COBOL、C++和 Delphi，但是规范是用二进制语言完成的 |
| 客户机/服务器接口 | 客户端的接口是存根，服务器端是骨架 | 客户端的接口是代理，服务器端是存根 |
| 对象激活和定位 | 这里，对象适配器用于激活，而 ORB 用于定位 | 这里，SCM(服务控制管理器)用于激活和定位 |
| 遗产 | 当每个接口都继承自 CORBA 对象时，支持接口级继承。 | 对象实现 *IUnknown* 接口时支持多重继承。 |
| 碎片帐集 | 它不提供通用的分布式垃圾收集 | 它通过 ping 线提供通用分布式垃圾收集。 |
| 异常处理 | 异常对象负责处理 | 异常被抛出到 *HRESULT* 中，对于其他异常*必须实现 ISupportErrorInfo* 接口 |
| 有效性 | 它由多家供应商提供 | 它可以通过单一供应商获得 |

</center>