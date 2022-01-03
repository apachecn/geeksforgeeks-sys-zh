# cookie |网络安全

> 原文:[https://www.geeksforgeeks.org/cookies-network-security/](https://www.geeksforgeeks.org/cookies-network-security/)

一个 [**网络服务器**](https://www.geeksforgeeks.org/web-server-and-its-type/) 将某些消息传输到网络浏览器，这样网络服务器就可以监控用户在特定网站上的活动，这些消息被称为**cookie**。它是网站存储在您的计算机上的一小段信息，并在您在该网站上迭代时使用它。当您再次访问网站时，浏览器会将信息发送回网站。

*   The web browser stores messages/information in a text file, and then every time the browser requests a page from the server, the messages/information will be sent back to the server.
*   The main purpose of cookies is to identify users, perhaps to prepare customized web pages for them.
*   The name *cookie is* An object derived from UNIX is called *magic cookie.* These are tokens attached to users or programs, which are switched according to the input area of users or programs.
*   Cookies have no malicious behavior on the computer system, that is, they are just a text file that can be deleted at any time-they are not plug-ins or programs.
*   Cookie can't be used to spread viruses or access your hard disk.

**Cookies** 无法读取你的硬盘来找出你的信息，但是，你提供给网站的任何个人信息，包括信用卡或借记卡信息，都很可能存储在 cookie 中，除非你已经关闭了对隐私构成威胁的 cookie。cookie 将只包含您免费提供给网站的信息。

不要在不可信的网站或网页上提供您的凭据信息。它可能会丢失您的数据和信息。

**Cookies 的用途:**

*   Session management–-Cookies let websites allow users to recall their personal login information and preferences.
*   Tracking-E-commerce websites use cookies to track the products that users have browsed before, and allow websites to recommend other products that you are interested in.
*   Personalization–This is a customized advertisement, which is the main way cookies use to personalize your conversation.

**饼干参数:**

饼干有 ***六个*** 参数可以传递给它们:

1.  ***Name of biscuit*** -determines the name of biscuit.
2.  ***The value of biscuits*** -determine the value of biscuits.
3.  ***Expiration date of cookies*** -determines the time that cookies remain active in your browser.
4.  ***Valid path of cookie*** -Set the URL path of cookie to be valid. Web pages or websites other than the cookie path cannot use the cookie.
5.  ***Valid field of cookie*** -This makes the path parameter go further. This enables pages on any server to access cookie when a site uses multiple servers in a domain.
6.  ***Require secure connection*** -It stipulates that cookie can only be used under secure server conditions, such as sites using SSL.