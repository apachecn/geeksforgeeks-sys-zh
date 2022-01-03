# TCP-Vegas 基本概念

> 原文:[https://www.geeksforgeeks.org/basic-concept-of-tcp-vegas/](https://www.geeksforgeeks.org/basic-concept-of-tcp-vegas/)

**简介:**
TCP Reno 和 TCP Tahoe 模型只有在系统发生一定的丢包时，才能判断网络中的拥塞情况。因此，在这些模型中，我们对数据包进行了补偿，以检测网络中的拥塞。在这些模型中，当发生分组丢失时，窗口大小减小，系统进入拥塞避免阶段。

而 TCP Vegas 会在任何数据包丢失发生之前感知网络中的拥塞，并立即减小窗口大小。因此，TCP Vegas 处理拥塞时不会发生任何数据包丢失。

TCP Vegas 使用往返时间来增加或减少拥塞窗口。测量预期和当前吞吐量，将其差值与某个最小和最大阈值进行比较。在比较的基础上，我们增加、减少或不改变拥塞窗口。

然后，解释了 TCP Vegas 的一些缺点。这些是处理发现数据转发和反向流动的差异，重新路由等。所以，TCP Vegas 在这些条件下并没有表现得更好。

经过实验和仿真，一些论文证明，TCP Vegas 的性能比 Tahoe 和 Reno 等其他 TCP 模型好 40-70%。

**TCP Vegas :**
这是一种完全不同的带宽管理方法，TCP 是第一次尝试。并且基于分组丢失发生之前的拥塞检测。
TCP Vegas 通过测量数据包的往返时间来控制拥塞窗口。在这种情况下，我们找到了额外的数据，这是通过减去网络中的预期数据和实际数据来测量的。将这些额外的数据与两个阈值(即αα和ββ)进行比较，从而增加或减少窗口大小。

所以算法中的步骤如下。

*   发送方测量预期流量，即 cwnd/BaseRTT。
*   然后，发送方通过使用数据包的实际往返时间来找到当前的流量。
*   在发送方计算机之后，队列中的额外数据，即额外数据=(预期-实际)* BaseRTT

所以，TCP Vegas 中使用的公式如下。

```
α <= (expectedOutput-actualOutput)*baseRTT <= β

where -
expectedOutput = window size divided by baseRTT, 
actualOutput = window size divided by currentRTT
baseRTT = It is the minimum RTT measured so far.
extra data in the netwoek = (expectedOutput-actualOutput)*baseRTT

```

所以有 3 种情况如下。

*   **案例-1 :**
    如果网络中的额外数据大于 Beta，则窗口大小会减小。

    ```
    cwnd=cwnd+1
    ```

*   **案例-2 :**
    如果网络中的额外数据小于 alpha，则窗口大小增加。

    ```
    cwnd=cwnd-1
    ```

*   **案例-3 :**
    如果额外数据位于封闭区间【α，β】之间，则窗口大小不变。

    ```
    cwnd=cwnd
    ```

**注意–**
应用上述情况之一后，在下一轮中再次重复相同的循环，并根据结果窗口大小减小、增大或不变。当网络不拥塞时，实际流量将接近预期流量。而当网络拥塞时，实际流量将小于预期流量。
TCP Vegas 试图利用网络的带宽，而不会造成网络拥塞。TCP Vegas 的窗口大小收敛到一个介于 w + alpha 和 w + beta 之间的点。TCP Vegas 具有拥塞控制能力，也赋予了网络稳定性，但不能充分利用带宽。