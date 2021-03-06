# 存储的跨站点脚本和反映的跨站点脚本之间的差异

> 原文:[https://www . geesforgeks . org/存储跨站点脚本和反射跨站点脚本的区别/](https://www.geeksforgeeks.org/difference-between-stored-cross-site-scripting-and-reflected-cross-site-scripting/)

[跨站点脚本](https://www.geeksforgeeks.org/what-is-cross-site-scripting-xss/)是一种客户端攻击，黑客将恶意代码注入易受攻击的 web 应用程序或网站。这种攻击会对企业及其客户端造成巨大的损害，后果可能包括——窃取密码、重定向到恶意网站、页面内容修改等。如果攻击者获得经过身份验证的用户的会话 cookies，他可以将自己模拟为经过身份验证的用户，并代表经过身份验证的用户继续执行任务。XSS 漏洞已被用于创建社交网络蠕虫、传播恶意软件、污损网站和费西合唱团获取凭据。

**跨站点脚本有两种类型:**

1.  储存在 XSS。
2.  XSS 想道。

**1。存储 XSS:** 黑客将恶意代码直接注入数据库或服务器的漏洞。在这里，应用程序或网站从未经授权的来源接收恶意数据或代码，并在未经检查的情况下将其存储在系统中。当受害者在浏览器中打开受影响的网页时，XSS 攻击代码会作为 HTML 代码的一部分显示给受害者的浏览器(就像合法的注释一样)。因此，一旦网页在其浏览器中被查看，受害者将最终执行恶意脚本。

**2。反射 XSS:** 该漏洞允许黑客以 HTML 代码的形式将恶意代码注入受害者的浏览器。用户只有在点击代码时才会被感染。与存储的 XSS 相比，反射的 XSS 不太危险，因为恶意内容不会永久存储在数据库/服务器中。攻击者可以通过多种方式诱使受害用户发出他们控制的请求，以发送反射的 XSS 攻击。其中包括在攻击者控制的网站上放置链接，或者通过电子邮件、推文或广告弹出窗口发送链接。

<figure class="table">

| 

**储存的 XSS**

 | 

**反射 XSS**

 |
| --- | --- |
| 也被称为永久 XSS。 | 也被称为临时 XSS。 |
| 恶意代码存储在应用程序中。 | 恶意代码不会存储在应用程序中。 |
| 对 web 应用程序或网站造成更多损害。 | 对 web 应用程序或网站造成的损害较小。 |
| 面向所有使用网络应用程序或网站的用户。 | 目标是少数使用网络应用程序或网站的用户。 |
| 当受害者访问受损网页时，恶意代码就会被激活。 | 点击链接后，恶意代码就会被激活。 |
| 更难表演。 | 更容易执行。 |

</figure>