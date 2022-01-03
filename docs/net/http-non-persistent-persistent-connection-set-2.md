# HTTP 非持久&持久连接|第二集(练习题)

> 原文:[https://www . geesforgeks . org/http-非持久-持久-连接-set-2/](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection-set-2/)

先决条件: [HTTP 非持久&持久连接–设置 1](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/)

对于问题观点，你需要知道非持久连接被称为 *HTTP 1.0* ，持久连接被称为 *HTTP 1.1* 。

*   **非持久连接**:需要对每个对象进行一次又一次的连接设置发送。
*   **持久连接**:不需要反复设置连接。多个对象可以使用连接。

**问题:**假设你有一个包含 30 个嵌入图像的基础 HTML 文件，图像&基础文件足够小，可以放入一个 TCP 段。在以下情况下需要多少 RTT 才能检索到基本文件&图像:
(一)无并联
的非持续连接(二)有 10 个并联
的非持续连接(三)无衬管
的持续连接(四)有衬管
的持续连接(假设 RTT 主导所有其他时间)

**说明:**
2rt 是初始需要的连接一个用于 TCP 连接，一个用于 HTML 基础文件。

```
Total time = 2RTT + transmit time
```

**(i)无并行连接的非持久连接:**
这里，对于每个映像，需要 2 个 RTT，一个用于 TCP 连接，一个用于要发送的映像。
因此 30 张图像的传输时间= 2*(30 RTT) = 60 RTT
总时间= 2 RTT+60 RTT = 62RTT

**(ii)10 路并联的非持久连接:**
这里可以同时发送 10 张图片。
因此对于 30 个图像，它需要->2 *(30/10)= 6 个时间间隔
总时间= 2 个 RTT + 6 个 RTT = 8 个时间间隔

**(iii)无流水线的持久连接:**
这里一次又一次的需要 TCP 连接。
因此对于 30 个图像，它需要- > 30 个 RTT
总时间= 2 RTT + 30 RTT = 32RTT

**(iv)与管道内衬的持久连接:**
由于是持久连接，所以不需要反复进行 TCP 连接。
管道内衬意味着在一个包中只能发送合适的图像。
在管道连接中，我们可以用 1RTT 发送所有图像。
总时间= 2 RTT+1 RTT = 3rt

本文由 **SHAURYA UPPAL** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。