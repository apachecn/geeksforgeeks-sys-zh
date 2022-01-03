# 什么是 SameSite Cookies 和 CSRF 保护？

> 原文:[https://www . geesforgeks . org/what-is-same site-cookies-and-csrf-protection/](https://www.geeksforgeeks.org/what-is-samesite-cookies-and-csrf-protection/)

CSRF 代表跨站点请求伪造。它允许攻击者通过电子邮件或其他方式精心设计一个被操纵的请求，从而在网站上做出改变状态的动作，而你目前被认证为你自己。CSRF 的意图不是读取敏感数据，而是为了攻击者的利益而写入或更改您的数据。

### CSRF 的示例场景

例如，您登录了您的网上银行网站 https://mybank.com。在您的网上银行应用程序中进行资金转账的请求网址如下所示:

```
https://mybank.com/transferFunds.do?beneficiary=Siva&amount=500
```

攻击者想把你的钱转到他的账户上。所以他制作了一封包含以下内容的电子邮件，

> ![’Logo](’https://mybank.com/transferFunds.do?beneficiary=Attacker&amount=50000′)

当您打开此电子邮件时，会从您的浏览器发出一个呼叫，您登录到您的网上银行帐户，将资金转移到攻击者的帐户。因此，只要打开电子邮件，你的账户就会被记入借方，因为你已经登录了银行网站。该图像可能看起来破碎，并显示替代文本，但攻击者成功地实现了他所期望的，即在您的银行网站上进行改变状态的借记帐户操作。

由于攻击者可以精心设计并向您发送在您的浏览器上执行的请求，因此攻击者无法读取特定于您的帐户的数据。CSRF 的主要意图是执行写操作。

### 常规 CSRF 保护机制

由于 CSRF 是一个严重的脆弱性，迄今为止已经尝试了多种保护机制。

1.  **POST 方法代替 GET 的用法:**有一种误解，认为只有 *GET* 方法容易受到 CSRF 攻击。可以向用户发送一个由 JavaScript 控制的 HTML 表单链接，当打开该链接时，用户可以使用 JavaScript 的 *POST* 方法自动提交到目标网站。所以这种方法并不能有效抵御 CSRF 的攻击。
2.  **反 CSRF 令牌:**对于网站生成的每个链接，网站还会在请求参数或请求头中附加一个反 CSRF 令牌。这应该是攻击者无法预测或篡改的强加密哈希。该网站还在其响应 cookie 中设置了此哈希。只有当包含 CSRF 令牌的参数与 CSRF cookie 匹配时，请求才会被允许继续。否则，请求失败。该 CSRF cookie 可以在每个会话或每个请求中生成一次，并且必须立即失效。起草并向您发送请求的攻击者不会知道当前会话/请求的 CSRF cookie 是什么。因此，所有带有 CSRF cookie 保护的状态改变行为都会破坏 CSRF 的攻击尝试。

### 相同的站点属性

对于与任何网站相关联的每个 cookie，都可以设置一个名为 SameSite 的属性。这是为了保护网站免受 CSRF 攻击。在不使用单独的 cookie 来保护网站免受 CSRF 攻击的情况下，可以将 SameSite 属性设置为网站的会话 cookie，该会话 cookie 指示是否应该仅在链接来自同一网站、第三方网站等时才发送授权用户进入网站的 cookie。，此属性控制此 cookie 传递行为。

### 使用相同站点 cookie 解决 CSRF 问题

由于这是所有网站的共同问题，每个网站都必须维护一个机制来生成、传递和无效 CSRF 令牌，Chrome 现在引入了 SameSite cookie，其基本目的是保护 CSRF。

几乎所有的网站都使用基于 Cookie 的用户认证机制。一旦用户使用他/她的凭证登录到一个网站，该网站就会在浏览器会话中设置一个 cookie。这用于响应用户对此特定站点的进一步请求，而无需再次登录。这个 cookie 被称为会话 cookie。在会话 cookie 的 SameSite 属性中使用以下值之一，网站可以保护自己免受 CSRF 攻击。

在一个域上设置的所有 cookie 都可以有一个与之关联的 SameSite cookie 属性值。SameSite cookie 可以采用以下值之一:

```
SameSite : strict
```

用*设置的 cookie 相同站点:严格的*将禁止 cookie 发送到所有第三方网站。只有当域与设置 cookie 的路径相同时，才会发送 cookie。

```
SameSite : none
```

设置有*相同站点的 Cookies:无*将禁用基于相同站点的保护。该网站可能使用自己的 CSRF 保护机制。

```
SameSite : Lax
```

用*设置的 cookie 相同站点:Lax* 将允许发送 cookie 仅用于顶级导航。当您没有添加 SameSite 属性时，Lax 被认为是默认行为。

因此，如果您使用*相同站点:严格，*设置会话 cookie，即使没有专用的 CSRF cookie，从第三方网站生成的到您网站的链接也不会包含会话 cookie。因此，不可能对他们进行 CSRF 袭击。

它变得越来越普遍，因为所有现代浏览器都在考虑实现这种行为，以保护其用户免受 CSRF 攻击。