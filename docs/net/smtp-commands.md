# SMTP 命令

> 原文:[https://www.geeksforgeeks.org/smtp-commands/](https://www.geeksforgeeks.org/smtp-commands/)

[简单邮件传输协议(SMTP)](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) 是一种 ASCII 协议。它基于客户机-服务器模式。该服务使用 TCP 端口号 25。因此，电子邮件；通过让源机器建立到目的机器的端口 25 的 TCP，从源传送到目的机器。要发送邮件，系统必须包含客户端 MTA，要接收邮件，系统必须有服务器 MTA。SMTP 将此邮件从客户端 MTA 传输到服务器 MTA。要发送邮件，SMTP 使用两次:一次在发件人和发件人的邮件服务器之间，另一次在两个邮件服务器之间。

**SMTP 命令:**
这些命令从**客户端发送到服务器**。每个命令由一个关键字和零个或多个参数组成。这意味着也有一些关键字不包含任何参数。该命令的格式如下:

```
 Keywords : argument(s) 
```

有 14 个不同的 SMTP 命令，如下表所示:

<figure class="table">

| 序列号
 | 关键词
 | 命令表单
 | 描述
 | 用法〔t0〕 |
| --- | --- | --- | --- | --- |
| 1. | 直升机 | <sp><domain><crlf>HELO</crlf></domain></sp> | 它提供发送方的标识，即主机名。 | 命令的 |
| 2. | 邮件 | 邮寄<sp>出发地:<reverse-path></reverse-path></sp> | 它指定邮件的发件人。 | 命令的 |
| 3. | RCPT(中央处理器) | RCPT <sp>至:<forward-path>T2】</forward-path></sp> | 它指定邮件的收件人。 | 命令的 |
| 4. | 数据 | 数据 | 它指定邮件的开头。 | 命令的 |
| 5. | 放弃 | 退出 | 它会关闭 TCP 连接。 | 命令的 |
| 6. | -你好 | rset〔t0〕 | 它中止当前的邮件事务，但 TCP 连接保持打开。 | 强烈推荐 |
| 7. | 哇哦哇哦哇哦哇哦哇哦哇哦哇哦哇哦哇哦哇哦哇哦哇哦 | VRFY | 它用于确认或验证用户名。 | 强烈推荐 |
| 8. | 突出物，隆起物 | NOOP | 无操作 | 强烈推荐 |
| 9. | 转动 | 转动 | 它颠倒了发送者和接收者的角色。 | 很少使用 |
| 10. | -ESPN | 露出 | 它指定要扩展的邮件列表。 | 很少使用 |
| 11. | 帮助 | 帮助 | 它向系统发送一些特定的文档。 | 很少使用 |
| 12. | 派遣 | 发送<sp>出发地:<reverse-path></reverse-path></sp> | 它向终端发送邮件。 | 很少使用 |
| 13. | 索姆 | SOML <sp>出发地:<reverse-path></reverse-path></sp> | 如果可能的话，它向终端发送邮件；否则发送到邮箱。 | 很少使用 |
| 14. | 安全声明标记语言（Security Assertion Markup Language 的缩写） | SAML <sp>FROM :<reverse-path></reverse-path></sp> | 它向终端和邮箱发送邮件。 | 很少使用 |

</figure>