# 双因素认证类型

> 原文:[https://www . geeksforgeeks . org/双因素身份验证类型/](https://www.geeksforgeeks.org/types-of-two-factor-authentication/)

[双因素认证](https://www.geeksforgeeks.org/saving-saves-passwords-two-factor-authentication/)是指使用各种认证方法中任意两种自力更生的方法。双因素身份验证用于确保用户已被识别以访问安全系统并提高安全性。由于移动计算机的基本安全责任，双因素身份验证首先在笔记本电脑上实施。通过使用双因素身份验证，未经授权的用户使用移动设备访问安全数据或系统变得更加困难。

双因素身份验证意味着要进行身份验证，任何两个身份验证因素都是必需的。安全系统所有者使用的各种类型的双因素身份验证如下:

**1。无线令牌:**
双因素身份验证中使用的一种安全形式是令牌。无线令牌是一种高级类型的令牌，其中完成了身份验证因素的自动配对，并且不需要键入字符序列。这两者使得认证过程变得容易。在这种类型的认证中，通过自动报警来防止对移动设备的不必要的访问。

**2。虚拟令牌:**
虚拟令牌是双因素认证中的新概念。虚拟令牌利用用户现有的互联网设备，这减少了通常与多因素解决方案的实施和保存相关的支出。该解决方案也不会遭受中间人攻击和其他形式的在线欺诈，因为用户的互联网设备直接与认证网站通信。

**3。磁卡:**
双因素身份验证的一种解决方案是将磁卡与安全的加密读卡器连接起来。磁卡可以是信用卡、借记卡、ATM 卡等。每张磁条卡都有自己不同的特征，比如卡上的指纹，即磁指纹。磁条包含磁指纹，这是一个很大的好处，没有卡将需要重新发行。为了确定卡的真实性，在每次刷卡时都会提供一个称为动态数字标识符的相关数字，该数字可以被评分并与激活值相匹配。

**4。短信一次性密码:**
短信一次性密码通过使用作为短信发送给用户的信息作为登录过程的一部分，确保双因素身份验证。用户在短信中收到一个唯一的临时个人识别码。然后，用户将该代码输入网站，以证明他的身份。除了简单的用户名和密码之外，这个过程还提供了一个额外的在线安全层。

**5。附加电话令牌:**
在这种类型的认证中，手机被用作处理器，并由 java ME 客户端形式的安全令牌组成。如同使用移动电话作为处理器一样，这种认证容易受到 MITM 攻击。在这种方法中，攻击是可能，其中受害者已经输入他们的登录凭证到一个伪造的网站。该网站将使用新协议将这些凭据传递给适当的网站。然后，这个合适的网站会向用户的移动设备发送一次性密码。受害者将一次性密码输入伪造的网站，然后该网站将该密码转发到适当的网站，欺诈者可以从该网站使用该密码完成访问。

**6。通用串行总线:**
在认证过程中，通用串行总线令牌以各种形式使用。通用串行总线令牌的登录凭证存储容量通常比智能卡大得多。它不能装在钱包里，但可以很容易地装在钥匙圈上。它们的建立和支持成本很高，容易遭受各种形式的盗窃和欺诈。

**7。移动签名:**
移动签名是通过使用私钥在任何 SIM 卡上的移动设备上创建的数字签名。在这个系统中，要签名的文本是移动电话安全的 SIM 卡。然后在用户收到的文本的帮助下，用户在输入个人识别码之前检查文本，以创建签名，然后将签名发送回服务提供商。典型的公钥基础设施系统用于验证签名。