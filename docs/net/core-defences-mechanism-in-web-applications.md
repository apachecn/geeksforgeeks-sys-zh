# 网络应用中的核心防御机制

> 原文:[https://www . geesforgeks . org/core-defenses-mechanism-in-web-applications/](https://www.geeksforgeeks.org/core-defences-mechanism-in-web-applications/)

我们将 web 应用程序中的核心防御分为三个方面:处理用户访问、处理用户输入和处理攻击者。这些解释如下。

**1。处理用户访问:**
第一个任务是根据用户(管理员用户、匿名用户、普通用户)处理访问。大多数网络应用程序使用三种相互关联的安全机制来处理访问:身份验证、会话管理和访问控制，如下所述。

1.  **认证–**
    检查用户或匿名用户有效性的用户名和密码机制是基本机制。如今，甚至更高级的机制，如两步验证，也被实现。所以，黑客们总是检查这些机制地缺陷。蛮力是最常见的。必须对这些输入应用限制和输入验证，以保护应用程序的基本功能。
2.  **会话管理–**
    之后，用户通过了认证的第一步，可能要进行管理并提供访问管理，这主要是通过令牌机制来完成的。漏洞的主要领域来自于令牌生成方式的缺陷，使攻击者能够猜测颁发给其他用户的令牌，以及令牌处理方式的缺陷，使攻击者能够捕获其他用户的令牌。因此，程序员可以实现令牌有效性时间检查和不易被攻击者猜到的困难加密令牌。

*   **Access Control –**
    On the basis of received credentials application decided the level of access and due to complex nature these mechanism are often defective. Developers often make ? awed assumptions about how users will interact with the application and frequently make oversights by omitting access control checks from some application functions. So, provide proper mechanism.

    **2。处理用户输入:**
    大多数缺陷是在应用程序的输入处理中发现的。任何不需要的输入甚至可能导致 SQL 注入的数据泄露或存储的 XSS 的令牌丢失，更多的攻击可能会发生并损害您的应用程序。因此，加强这些机制就变得非常必要。用户输入可以是用户名、评论、搜索、表单，有时也使用 cookies。

    **处理用户输入的方法–**
    我们无法在输入时猜测用户的想法或方法。所以，我们应该采用“拒绝已知的坏”的“RKB”方法。

    *   **Reject Known Bad –**
        This, method consists of a blacklist according to which characters are blocked. In general, this is regarded as the least effective approach to validating user input, for two main reasons. First, a vulnerability in a web application can be exploited using a wide variety of input, and second, techniques for exploitation are at a constant change.

        黑名单过滤器可以通过以下方式绕过:

        ```
        1\. If SELECT is blocked, try SeLeCt
        2\. If or 1=1-- is blocked, try or 2=2--
        3\. If alert(‘xss’) is blocked, try prompt(‘xss’) 
        ```

        通过在表达式之间使用非标准字符来中断应用程序执行的标记化，可以绕过旨在阻止特定关键字的筛选器。

        例如:

        ```
        SELECT/*foo*/username, password/*foo*/FROM/*foo*/users 
        ```

        空字节旁路示例。
        例如:

        ```
        %00alert(1)
        ```

    *   **接受已知良好(AKG)–**
        这种方法是“RKB”方法的倒数，在这种方法中，我们不能拒绝不良输入。相反，我们可以创建一个白名单。因此，应用程序只能接受列出的输入，所有其他输入都被应用程序拒绝。这种方法比拒绝已知错误的方案更安全。

    *   **净化–**
    在这种方法中，收到的数据必须进行净化。可能会从数据中删除恶意字符，只留下安全字符，或者在执行进一步处理之前对其进行适当编码或“转义”。例如，针对跨站点脚本攻击的通常防御措施是在将危险字符嵌入应用程序页面之前对其进行 HTML 编码。但是如果攻击者了解清理机制，它可能会被绕过。*   **安全数据处理–**
    大多数网络应用程序漏洞的出现是因为用户提供的数据以不安全的方式处理。漏洞通常可以忽略，不是通过验证输入本身，而是通过确保对其执行的处理是安全的。在某些情况下，可以使用安全的编程方法来避免常见的问题。例如，可以通过正确使用参数化查询进行数据库访问来防止 SQL 注入攻击。*   **语义检查–**
    但是，由于存在一些漏洞，攻击者提供的输入与普通的非恶意用户可能提交的输入相似。使它具有恶意的是提交它的不同情况。例如，攻击者可能试图通过更改隐藏表单字段中传输的帐号来访问另一个用户的银行帐户。再多的语法验证也无法区分用户的数据和攻击者的数据。为了避免未经授权的访问，应用程序需要验证提交的帐号是否属于提交它的用户。*   **多步验证–**
    这些天我们都在使用很多安全服务，比如 gmail 等，它为我们提供了两步或者我们可以说多步验证。但所有这些验证都是为了用户识别而不是数据验证。

**3。处理攻击者:**
在处理错误时，我们必须考虑以下几点:处理错误、维护审计日志、向管理员发出警报以及对攻击做出反应，解释如下。

1.  **处理错误–**
    短期内，攻击者首先试图收集有关应用程序的信息。因此，应用程序中的所有错误机制都不能提供任何描述性信息，即不能泄露任何关于数据库、系统架构或路径细节等的信息。
2.  **Maintaining Audit –**
    Audit logs are important while investigate events such an incident, effective audit logs should enable the application’s owners to understand exactly what has taken place, which vulnerabilities were exploited, whether the attacker gained unwanted access to data or performed any unauthorized actions, and, as far as possible, provide evidence of the intruder’s identity.

    与身份验证功能、密钥事务、任何包含表明明显恶意意图的已知攻击字符串的请求相关的所有事件。

3.  **提醒管理–**
    可能有某种机制可以提醒应用程序的管理员应用程序中的任何异常活动，如来自特定 IP 的高 ping 请求。
4.  **对攻击做出反应–**
    许多安全关键型应用程序包含内置机制，可对被识别为潜在恶意用户做出防御反应。因为大多数应用程序是不同的，攻击者必须执行不同的测试来发现漏洞，我们将识别出许多潜在的恶意请求并阻止它们。由于这个原因，一些 web 应用程序采取自动的反应措施来挫败以这种方式工作的攻击者。例如，他们可能会越来越慢地响应攻击者的请求或终止攻击者的会话，要求他在继续攻击之前登录或执行其他步骤。