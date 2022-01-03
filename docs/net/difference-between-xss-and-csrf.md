# XSS 和 CSRF 的区别

> 原文:[https://www . geesforgeks . org/difference-XSS-and-csrf/](https://www.geeksforgeeks.org/difference-between-xss-and-csrf/)

**1。 [XSS](https://www.geeksforgeeks.org/what-is-cross-site-scripting-xss/) :**
XSS 是网络应用程序中发现的一个计算机安全漏洞，该漏洞使网络罪犯能够将客户端脚本注入用户查看的网页中。网络罪犯让受害者的浏览器执行攻击者在访问可信网站时注入的脚本(大部分是用 JavaScript 编写的)。网络罪犯有几种方法将 JavaScript 注入受害者信任的网站。它不需要经过身份验证的会话，并且当易受攻击的网站不执行验证或转义输入的基本操作时，它会被利用。

**2。 [CSRF](https://www.geeksforgeeks.org/what-is-cross-site-request-forgery-csrf/) :**
跨站点请求伪造是最严重的计算机安全漏洞之一，可以通过各种方式利用，从在用户不知情的情况下更改用户信息到完全访问用户帐户。网络罪犯试图利用现有受害者的背景(如 cookies)强迫/欺骗您提出您不希望的请求。每次你与网站互动时，它的服务器都会检查你随请求发送的 cookie，这样它就知道是你。

**XSS 和 CSRF 的区别:**

<center>

| 没有。 | XSS | CSRF(无线电频率) |
| 1. | XSS 代表跨站点脚本。 | CSRF 代表跨站点请求伪造。 |
| 2. | 网络罪犯将恶意客户端脚本注入网站。添加该脚本是为了给受害者造成某种形式的漏洞。 | 恶意攻击的创建方式是，用户在不知道攻击的情况下向目标网站发送恶意请求。 |
| 3. | 在这种情况下，由未经验证的数据注入任意数据。 | 检索和执行攻击包取决于浏览器的功能和特性。 |
| 4. | 执行此攻击需要 JavaScript。 | 执行此攻击不需要 JavaScript。 |
| 5. | 该网站接受恶意代码。 | 恶意代码存储在第三方网站中。 |
| 6. | 容易受到 XSS 攻击的网站也容易受到 CSRF 攻击。 | 完全不受 XSS 攻击类型影响的站点仍然容易受到 CSRF 攻击。 |
| 7. | 相比之下，XSS 的危害更大。 | 相比之下，CSRF 的危害较小。 |
| 8. | 利用 XSS 漏洞，攻击者可以做他/她想做的任何事情。 | 利用 CSRF 漏洞，攻击者只能做易受攻击的 URL 所做的事情。​ |

</center>