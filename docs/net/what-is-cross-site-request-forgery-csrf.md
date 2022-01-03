# 什么是跨站点请求伪造(CSRF)

> 原文:[https://www . geesforgeks . org/什么是跨站点-请求-伪造-csrf/](https://www.geeksforgeeks.org/what-is-cross-site-request-forgery-csrf/)

**跨站点请求伪造(CSRF)** 是最严重的漏洞之一，可以通过各种方式利用——从在用户不知情的情况下更改用户信息到完全访问用户帐户。

现在几乎每个网站都使用 cookies 来维护用户会话。由于 [HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) 是一个“无状态”协议，因此没有内置的方法来保持用户对一系列请求的身份验证。从用户体验的角度来看，每次操作都要求用户提供凭证是一个非常糟糕的想法，这就是为什么使用 cookies 的原因。Cookies 对于这个目的非常有效，并且如果它们拥有足够的熵、密码强度并且通过安全通道传输(使用 [HTTPS](https://www.geeksforgeeks.org/whats-difference-http-https/) )则是安全的。

但是，有一个问题，每当向网站提出请求时，浏览器都会向该网站提交 cookies，而不会检查请求的“来源”。这就是 CSRF 出现的地方。

攻击者将一些代码放在他的网站上，向目标网站发出真正的外观请求。目标网站的 cookies 将由浏览器在请求中添加。这将使伪造的请求成为合法请求，它的行动将成功执行。

**攻击面:**
针对 CSRF 的攻击面大多是 HTTP 请求，导致与受害者相关的东西发生变化，例如:姓名、电子邮件地址、网站甚至密码。它有时也被用来改变身份验证的状态。(登录 CSRF，注销 CSRF)不太严重，但在某些情况下仍有问题。

**剥削:**
考虑一个网站 example.com 和攻击者的网站 evil.com。还假设受害者已经登录，并且他的会话由 cookies 维护。攻击者将:

1.  找出他需要代表受害者执行的动作并找出其终点(例如，要在 target.com 上更改密码，会向包含新密码作为参数的网站发出 [POST 请求](https://www.geeksforgeeks.org/get-post-requests-using-python/)。)
2.  将 [HTML 代码](https://www.geeksforgeeks.org/html-basics/)放在 evil.com 的网站上，该代码将模仿对 target.com 的合法请求(例如，以方法作为帖子的表单和包含新密码的隐藏输入字段)。
3.  确保通过使用“自动提交”或引诱受害者点击提交按钮来提交表单。

当受害者访问 evil.com 并提交该表单时，受害者的浏览器会向 target.com 请求更改密码。浏览器还会将 cookies 附加到请求中。服务器将其视为真正的请求，并将受害者的密码重置为攻击者提供的值。这样受害者的账户就被攻击者接管了。

**预防:**

*   **在用户端:**
    用户端防范在浏览体验方面效率非常低，一次只能浏览单个标签页，不使用“记得我”功能就可以进行防范。
*   **在服务器端:**
    在服务器端实现 CSRF 保护的方法有很多，其中使用 CSRF 令牌最为流行。CSRF 令牌是绑定到用户会话的字符串，但不会自动提交。网站只有在收到有效的 CSRF 令牌和 cookies 时才会继续运行，因为攻击者无法知道用户特定的令牌，所以攻击者不能代表用户执行操作。