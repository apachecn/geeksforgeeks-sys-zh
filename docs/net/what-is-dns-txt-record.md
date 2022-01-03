# 什么是 DNS TXT 记录？

> 原文:[https://www.geeksforgeeks.org/what-is-dns-txt-record/](https://www.geeksforgeeks.org/what-is-dns-txt-record/)

[域名系统(DNS)](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/) 在维护整个互联网基础设施方面起着至关重要的作用，因此它的故障使得系统对用户来说不可达。DNS 将数据与每个参与实体的不同域名连接起来。此应用程序或模型是使用 Microsoft visual basic 6.0 和 access 数据库开发的。域名系统维护一个域名目录(就像我们的电话簿一样)，并将它们翻译成 IP(互联网协议)地址。这使得域名容易被人们记住，这样他们就可以很容易地在电脑或机器上访问网站(GOOGLE、YOUTUBE、GMAIL)，而不是通过搜索 IP 地址来访问网站。

**TXT 记录:**
TXT 记录用于提供域管理员连接文本和区域的能力。文本可以是人类可读的，也可以是机器可读的。可以将这些记录添加到它们各自的域设置中。该记录允许区域头将任何文本内容插入到域名系统记录中。这些记录被用于不同的目的。

一个模型是所有权验证:为了证明你拥有该区域，供应商可能希望你在你的空间和电子邮件安全中添加一个具有特定价值的 TXT 记录。一个域可以有多个 TXT 记录。TXT 记录包含大量文本，每个字符串最多 255 个字符，带有特殊字符和空格。

**DNS TXT 记录格式:**

```
 *Record: geeksforgeeks.com  /  type: TXT /  value: "attribute=value"  / TTL(Time to Live)*
```

证明你是那个域名的实际所有者。许多供应商，例如谷歌、Office 365 等，经常要求在域名系统区域中包含一个不常见的验证码。

可以使用***$ dig TXT your-domain.com**或**$ nslookup-type = TXT your-domain.com***来检查 TXT 记录

**DNS TXT 记录的常见用途:**

*   **站点验证记录–**
    该记录表明了对域的责任，并可用于将管理(例如，微软 365 和 G-Suite)与特定领域联系起来。
*   **DKIM 记录–**
    该记录存储了途中审批电子邮件时使用的重要数据。请注意，商业电子邮件不支持给 DKIM 记录一个私钥。
*   **SPF 记录–**
    该记录用于向邮件交易演示哪些主机被批准为某个域发送信件。这通过让邮件服务器根据该区域的 SPF 记录检查邮件的发送地址来减少垃圾邮件。
*   **DMARC 记录–**
    基于域的消息身份验证报告和一致性记录改进了网络钓鱼和电子邮件欺骗攻击。