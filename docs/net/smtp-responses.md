# SMTP 响应

> 原文:[https://www.geeksforgeeks.org/smtp-responses/](https://www.geeksforgeeks.org/smtp-responses/)

[简单邮件传输协议(SMTP)](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) 响应从**服务器发送到客户端**。SMTP 中的每个响应都以三位数代码开头，后面可能会有附加的文本信息。回复中的前导数字表示回复的类别。以下是不同类别的答复:

```
1. Positive completion reply
2. Positive Intermediate reply
3. Transient Negative Completion reply 
4. Permanent Negative Completion reply 
```

这些解释如下:

1.  **肯定完成回复–**
    该回复指动作成功完成。之后，可以发起新的请求。
2.  **肯定的中间回复–**
    该回复是指接受我们给出的命令，但是请求的行动处于暂停状态，并且还在等待进一步信息的接收。

*   **暂时否定完成回复–**
    该回复是指命令未被接受，请求的操作未发生。在这种情况下，错误情况是暂时的，也可以再次请求操作。*   **Permanent Negative Completion reply –**
    This reply refers that command was not accepted and requested action did not occur.

    下表列出了各种 SMTP 响应:

    <center>

    | 种类 | 密码 | 描述 |
    | --- | --- | --- |
    | 肯定
    完成
    回复 | Two hundred and eleven | 系统状态和系统帮助回复。 |
    | Two hundred and fourteen | 帮助信息。 |
    | Two hundred and twenty | <domain>服务准备就绪。</domain> |
    | Two hundred and twenty-one | <domain>服务关闭传输通道。</domain> |
    | Two hundred and fifty | 请求的邮件操作正常，已完成。 |
    | Two hundred and fifty-one | 用户不在本地；该消息将被转发至<forward-path>。</forward-path> |
    | 正面
    中间
    回复 | Three hundred and fifty-four | 开始邮件输入；以<crlf>结束。</crlf> |
    | 短暂的否定的；消极的；负面的；负的完成回答 | Four hundred and twenty-one | <domain>服务不可用，失去传输通道。</domain> |
    | Four hundred and fifty | 未采取请求的邮件操作，邮箱不可用(例如，邮箱忙)。 |
    | Four hundred and fifty-one | 请求的操作中止；处理中的本地错误。 |
    | Four hundred and fifty-two | 未采取请求的行动；系统存储系统不足。 |
    | 永久
    否定
    完成
    回复 | Five hundred | 语法错误，无法识别命令。 |
    | Five hundred and one | 参数或自变量中的语法错误。 |
    | Five hundred and two | 命令未实现。 |
    | Five hundred and three | 命令顺序错误。 |
    | Five hundred and four | 命令参数未实现。 |
    | Five hundred and fifty | 由于邮箱不可用，请求的操作未被执行(例如，找不到邮箱，无法访问)。 |
    | Five hundred and fifty-one | 用户不在本地；请试试<forward-path>。</forward-path> |
    | Five hundred and fifty-two | 请求的邮件操作中止；超出存储分配。 |
    |  | Five hundred and fifty-three | 请求的操作未被执行，因为邮箱名称不允许(例如，邮箱语法不正确。). |
    | Five hundred and fifty-four | 交易失败。 |

    </center>