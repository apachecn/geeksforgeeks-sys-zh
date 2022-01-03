# 与 SQL 注入相关的风险

> 原文:[https://www . geesforgeks . org/risks-associated-on-SQL-injection/](https://www.geeksforgeeks.org/risks-associated-with-sql-injection/)

[SQL 注入](https://www.geeksforgeeks.org/sql-injection-2/)是数据库系统最常见的威胁。它会导致非常安全或机密的数据丢失。这只不过是对数据系统或账户的未经授权的访问。

以下是与 SQL 注入相关的风险:

1.  **通过通过身份验证:**
    在渗透测试期间，最重要的是关注通过身份验证，因为攻击者可以像授权用户一样访问数据库，并且他可以在数据库上执行他想要的任务。
2.  **识别可注射参数:**
    攻击者将收集关于 web 应用程序后端数据库结构的信息，并将动态内容包含到网站中。这可能会导致访问者安装恶意代码，并可能重定向到恶意网站。

*   **Executing Remote Commands :**
    Executing these remote commands will provide attackers a tool to execute arbitrary commands on the database.

    例如，远程用户可以从远程 SQL 交互界面执行存储的数据库过程和函数。

    *   **[【拒绝服务】](https://www.geeksforgeeks.org/deniel-service-prevention/) :**
    攻击者可以用请求淹没服务器，这样他就有权力停止对有效用户的服务，或者他可以删除一些数据。*   **数据库指纹打印:**
    攻击者可以确定后端使用的数据库类型，以便他可以使用与特定 DBMS 中的弱点相对应的特定于数据库的攻击。