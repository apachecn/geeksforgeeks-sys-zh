# 提前和延迟令牌释放的区别

> 原文:[https://www . geeksforgeeks . org/早期和延迟令牌发布的区别/](https://www.geeksforgeeks.org/difference-between-early-and-delayed-token-release/)

先决条件–[令牌环](https://www.geeksforgeeks.org/efficiency-of-token-ring/)

**1。早期令牌发布:**

*   发送方在释放令牌之前不会等待数据包完成旋转。数据一传输，令牌就被释放。
*   环中存在多个数据包。
*   不如延迟令牌释放可靠。

**2。延迟令牌释放:**

*   在这种情况下，发送方发送数据包并等待，直到整个数据包完成环的往返并返回。当发送方收到整个数据包时，它会释放令牌。
*   在一个实例中，环中只有一个数据包。
*   比早期令牌发布更可靠。

**提前和延迟令牌释放的区别:**

<center>

| 早期令牌释放 | 延迟令牌释放 |
| 发送方在释放令牌之前不会等待数据包完成旋转。 | 在这种情况下，发送方发送数据包并等待，直到整个数据包完成环的往返并返回。 |
| 数据一传输，令牌就被释放。 | 当发送方收到整个数据包时，它会释放令牌。 |
| 例如，环中存在多个数据包。 | 在任何情况下，环中都只有一个数据包。 |
| 与延迟令牌发布相比，不太可靠。 | 与早期令牌发布相比更可靠。 |
| 令牌持有时间(THT) = T <sub>t</sub>其中，T <sub>t</sub> =传输延迟 | 令牌持有时间(THT) = T <sub>t</sub> + T <sub>p</sub>其中，T <sub>t</sub> =传输延迟，
T <sub>p</sub> =传播延迟 |
| 由于环中存在多个数据包，因此可能会发生冲突。 | 冲突是不可能的，因为在任何情况下环中都只有一个数据包。 |
| 周期时间= T <sub>p</sub> + N * (T <sub>t</sub> )
其中，
T <sub>t</sub> =传输延迟
T <sub>p</sub> =传播延迟
N =环内站数 | 周期时间= T<sub>p</sub>+N *(T<sub>T</sub>+T<sub>p</sub>)
其中，
T <sub>t</sub> =传输延迟
T <sub>p</sub> =传播延迟
N =环内站数 |
| 效率=(N * T<sub>T</sub>)/(T<sub>p</sub>+N *(T<sub>T</sub>)
其中，
T <sub>t</sub> =传输延迟
T <sub>p</sub> =传播延迟
N =环内站数 | 效率=(N * T<sub>T</sub>)/(T<sub>p</sub>+N *(T<sub>T</sub>+T<sub>p</sub>)
其中，
T <sub>t</sub> =传输延迟
T <sub>p</sub> =传播延迟
N =环内站数 |

</center>