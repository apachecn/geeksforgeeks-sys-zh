# 什么是同产地政策(SOP)？

> 原文:[https://www . geeksforgeeks . org/同根同源-政策-sop/](https://www.geeksforgeeks.org/what-is-same-origin-policy-sop/)

同一来源策略是一种浏览器安全功能，它限制由一个来源加载的文档或脚本访问另一个来源的文档或脚本或与之交互。原点由协议、主机和端口组成。

#### **例如，考虑以下 URL:**

> https://geeksforgeeks.com

在上面的例子中“https://”是协议，“geeksforgeeks.com”是主机，端口是“80”。

注意:默认情况下，网站使用端口 80。

相同来源策略是必要的，因为当浏览器从一个来源向另一个来源发出 HTTP 请求时，所有相关数据(即 cookies、身份验证令牌、会话或任何相关数据)都会作为请求的一部分发送。如果另一个来源是恶意的，它将能够访问受害用户的所有信息。

#### 示例:

> 如果没有相同来源的政策，你访问一个恶意网站，它将能够读取你的社交网络帐户的所有信息。

当两个源具有相同的协议、主机和端口时，它们被称为是相同的。

让我们将“https://geeksforgeeks.com”的来源与下表中的来源进行比较。

<figure class="table">

| **URL** | **同根同源？** |
| https://geeksforgeeks.com/example1 | 是的，相同的协议、主机和端口。只有网址路径不同。 |
| https://geeksforgeeks.com/example/example.html  | 是的，相同的协议、主机和端口。只有网址路径不同。 |
| http://geeksforgeeks.com/example | 不，协议不同。 |
| https://practice.geeksforgeeks.com/example | 不，主人不一样。 |
| http://www.geeksforgeeks.com/example | 不，主机和协议不同 |
| https://geeksforgeeks.com:81/example | 不，端口不同 |

注意:Internet Explorer 将允许“https://geeksforgeeks:81/example”，因为 IE 在应用相同的起源策略时不考虑端口号。

### 同一原产地政策何时实施限制？

当涉及两个不同来源时，浏览器应用相同来源策略。

*   iframe 中的内容不能被页面访问，除非它们来自同一个源。
*   不允许 XMLHttpRequests。
*   特定站点的会话 Cookies 不能发送到不同来源的页面。

注意:在 cookies 的情况下，不检查协议和端口。仅选中主机。

同源政策并没有完全限制两个来源之间的互动。浏览器检查两个来源之间的交互是否构成威胁，如果不是，它允许交互。

通常允许页面资源的跨来源加载。您可以从不同的站点嵌入带有标签的图像、带有

### 同源政策够了吗？

同源策略实施了一些安全性，但不足以防止各种攻击。其中一些是:

*   跨站点请求伪造(CSRF)攻击，主要利用不同的来源。这就是为什么反 CSRF 令牌应该被用在相同来源政策之外。
*   跨站点脚本(XSS)攻击也可以通过同源策略来防止，但是为了防止这种攻击，必须限制从外部源加载脚本，这可能会破坏 web 应用程序的功能。

</figure>