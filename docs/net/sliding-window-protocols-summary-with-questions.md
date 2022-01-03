# 带问题的滑动窗口协议摘要

> 原文:[https://www . geesforgeks . org/滑动窗口-协议-带问题摘要/](https://www.geeksforgeeks.org/sliding-window-protocols-summary-with-questions/)

**先决条件–**[停止&等待](https://www.geeksforgeeks.org/stop-and-wait-arq/)、[返回 N](https://www.geeksforgeeks.org/sliding-window-protocol-set-2-receiver-side/) 、[选择性重复](https://www.geeksforgeeks.org/sliding-window-protocol-set-3-selective-repeat/)

### 所有协议的总结–

在开始提问之前，快速回顾一下所有协议。

**停车等待–**

1.  发送器窗口大小(W <sub>s</sub> ) = 1
2.  接收器窗口大小(W <sub>r</sub> ) = 1
3.  序号≥ 1 + 1
4.  使用独立确认
5.  丢弃无序数据包
6.  丢包？超时后重新传输数据包
7.  确认丢失？超时后重新发送数据包
8.  效率= 1/(1+2a)，其中 a = T <sub>p</sub> / T <sub>t</sub>

**返回 N–**

1.  发送器窗口大小 W <sub>s</sub> = N
2.  接收器窗口大小 W <sub>r</sub> = 1
3.  序号≥ N + 1
4.  能否使用累积或独立确认取决于确认计时器
5.  丢弃无序数据包
6.  丢包？从窗口限制内的最后一个数据包回溯到丢失的数据包，并重新传输它们
7.  确认丢失？如果在超时前没有收到，则重新发送整个窗口大小
8.  效率= N/(1+2a)其中 a = T <sub>p</sub> / T <sub>t</sub>

**选择性重复–**

1.  发送器窗口大小 W <sub>s</sub> = N
2.  接收器窗口大小 W <sub>r</sub> = N
3.  序号≥ N + N
4.  仅使用独立确认
5.  可以接受无序数据包
6.  丢包？超时后只重发丢失的数据包
7.  确认丢失？如果超时前没有收到，重新发送
8.  效率= N/(1+2a)其中 a = T <sub>p</sub> / T <sub>t</sub>

### 练习问题–

*   **例-1。**在停止和等待协议中，每 4 个<sup>第</sup>个数据包丢失，我们总共需要发送 10 个数据包，那么发送所有数据包需要多少次传输？
*   **Explanation –**

    ```
    1 2 3 4 5 6 7 8 9 10 (Initially)
          ^
    1 2 3 4 4 5 6 7 8 9 10 (Packet no. 4 retransmitted) 
                  ^
    1 2 3 4 4 5 6 7 7 8 9 10 (Packet no. 10 retransmitted)
                           ^
    1 2 3 4 4 5 6 7 7 8 9 10 10 (Result)

    ```

    因此，我们重新传输了包号 4、7、10
    总计数= 13

*   **例-2。**在 S & W 协议中，如果错误概率为 p，要发送的数据包数量为‘n’。我们要发多少包？
*   **解释–**
    总重传次数
    = n * p<sup>0</sup>+n * p<sup>1</sup>+n * p<sup>2</sup>+n * p<sup>3</sup>+n * p<sup>4</sup>+…
    = n(1+p+p<sup>2</sup>+p<sup>3</sup>+p<sup>4</sup>+…)
*   ****例-3。**在 GBN 发送器窗口大小= 10，T<sub>p</sub>= 49.5 毫秒&T<sub>T</sub>= 1 毫秒。给定带宽= 1000 bps，协议的效率和吞吐量是多少？**
*   ****解释–**
    效率= N/(1+2a)，N = 10(给定)，a = T<sub>p</sub>/T<sub>T</sub>= 49.5
    效率= 10/(1 + 2 * 49.5) = 10/100 = 0.1 或 10%
    吞吐量=效率*带宽
    = 0.1 * 1000 = 100**
*   ****例-4。**在 GB3 中，如果每 5 个数据包丢失一次&我们需要发送 10 个数据包，那么需要重传多少次？**
*   ****Explanation –**

    ```
    1 2 3 4 5 6 7  | 8 9 10 
            ^   $            (packet no. 5 lost)
    1 2 3 4 5 6 7 5 6 7 8 9 | 10
                  *   ^   $       
    1 2 3 4 5 6 7 5 6 7 8 9 7 8 9 10
                            *   ^  $
    1 2 3 4 5 6 7 5 6 7 8 9 7 8 9 10 9 10 (count starts from * till ^)
    (from ^ to $ retranmission is done)

    ```

    **注意–**从最后一个数据包是窗口大小到丢失的口袋，我们重新发送整个窗口。
    传输总数= 18** 
*   ****例-5。**在 SR W <sub>s</sub> = 5 中，我们发送了 10 个数据包，其中每丢失 5 个数据包，找到重传次数了吗？**
*   ****Explanation –**

    ```
    1 2 3 4 5 6 7 8 9 10
            ^
    1 2 3 4 5 5 6 7 8 9 10
                      ^
    1 2 3 4 5 6 7 8 9 9 10

    ```

    我们在这里看到，在服务请求中没有窗口大小的作用，只有丢失的数据包被重新发送。
    总传输量= 12** 
*   ****Example-6.** If there is K bits sequence no. define require sender window size and receiver window size for S&W, GBN & SR?

    **解释–**
    给定，K 位，对于 S&W<sub>S</sub>= 1 和 W <sub>r</sub> = 1
    对于 GBN，W <sub>s</sub> = 2 <sup>K</sup> -1 和 W <sub>r</sub> = 1
    对于 SR，W <sub>s</sub> = 2 <sup>K-1</sup> 和 W <sub>r</sub>

    本文由 [**SHAURYA UPPAL**](https://www.linkedin.com/in/shaurya-uppal-3b7a6373/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**