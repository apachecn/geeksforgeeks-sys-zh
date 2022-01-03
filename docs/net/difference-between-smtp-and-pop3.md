# 【SMTP 和 POP3 的区别

> 原文:[https://www . geesforgeks . org/difference-SMTP-and-pop 3/](https://www.geeksforgeeks.org/difference-between-smtp-and-pop3/)

对于发送和接收消息，我们使用两种协议，一种是 [SMTP(简单邮件传输协议)](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/)，另一种是 [POP3(邮局协议版本 3)](https://practice.geeksforgeeks.org/problems/what-is-pop) 。它们也分别被称为 PUSH 和 POP 协议。它们分别是发送和检索消息的代理、消息传输代理和消息访问代理。

【SMTP 和 POP3 的区别:

<figure class="table">

| S.NO | 简单邮件传输协议 | POP3 |
| 1. | SMTP 代表简单邮件传输协议。 | POP3 代表邮局协议第 3 版。 |
| 2. | 它用于发送消息。 | 它用于访问消息。 |
| 3. | SMTP 的端口号为 25、465 和 587，用于安全连接(TSL 连接)。 | POP3 的端口号是 110 或用于 SSL/TSL 连接的端口 995。 |
| 4. | 它是一个 MTA(消息传输代理)发送消息给接收者。 | 是 MAA(邮件访问代理)从邮箱访问邮件。 |
| 5. | 它有两个 MTA，一个是客户端 MTA(消息传输代理)，第二个是服务器 MTA(消息传输代理)。 | 它还有两个 MAA 一个是客户端 MAA(消息访问代理)，另一个是服务器 MAA(消息访问代理)。 |
| 6. | SMTP 也称为 PUSH 协议。 | POP3 也被称为 POP 协议。 |
| 7. | SMTP 将邮件从发件人的计算机传输到收件人邮件服务器上的邮箱。 | POP3 允许从收件人邮件服务器上的邮箱检索和组织邮件到收件人的计算机。 |
| 8. | 它隐含在发送者邮件服务器和接收者邮件服务器之间。 | 它隐含在接收者和接收者邮件服务器之间。 |

</figure>