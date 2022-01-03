# 维加斯 A(修改后的 TCP-Vegas )

> 原文:[https://www.geeksforgeeks.org/vegas-a-modified-tcp-vegas/](https://www.geeksforgeeks.org/vegas-a-modified-tcp-vegas/)

维加斯 A 是 [TCP](https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/) 维加斯的修改。拉斯维加斯的 A 代表适应性。TCP Vegas 有一个固定值的常量 alpha 和 beta。因此，当它与 TCP Reno 连接时，它并没有做得更好。因此，在维加斯 A 中，这些常数不是固定的，而是根据吞吐量和队列中的额外数据而变化。

首先，常数α和β的值分别为 1 和 3，即，

```
α = 1 and β = 3
```

维加斯 A 的这些值根据网络条件动态变化。维加斯 A 的拥塞恢复和慢启动阶段与 TCP 维加斯相同。这些改变仅在避免拥塞时进行

算法中使用的术语解释如下。

```
Tht = actual throughput at time t
Tht-rtt = actual throughput at previous rtt
```

基于差异值，即队列中的额外数据，出现了如下三种情况。

*   **Case-1 :**
    If the value of diff lies between the constant alpha and beta i.e.

    ```
    α <= diff <= β
    ```

    那么，它也有如下两种情况。

    1.  If the value of actual throughput at time t is greater than the value of actual throughput at time (t-rtt) i.e.

        ```
        Tht > Tht-rtt
        ```

        然后，将窗口大小增加 1，

        ```
        cwnd = cwnd + 1
        ```

        ```
        α = α +1, β = β + 1
        ```

    2.  If the value of actual throughput at time t is less than or equal to the value of actual throughput at time (t-rtt) i.e.

        ```
        Tht <= Tht-rtt
        ```

        然后，对和，α，β不进行任何更新。

        常量值会发生变化，因为即使两个常量之间存在差异，吞吐量也会增加。
        因此，网络没有被充分利用，仍有一些带宽剩余。因此，发送数据的速率增加。
        恒定值增加是因为随着吞吐量的增加，为了最好地利用可用带宽，我们必须增加α和β值。

*   **Case-2 :**
    If the value of diff is less than the constant alpha i.e

    ```
    α > diff
    ```

    然后，它有以下三种情况。

    1.  If the value of alpha is greater than 1 and the value of actual throughput at time t is greater than the value of actual throughput at time (t-rtt) i.e.

        ```
        α > 1 and Tht > Tht-rtt
        ```

        然后，将窗口大小增加 1，

        ```
        cwnd = cwnd + 1
        ```

    2.  Else If the value of alpha is greater than 1 and the value of actual throughput at time t is less than the value of actual throughput at time (t-rtt) i.e.

        ```
        α > 1 and Tht < Tht-rtt
        ```

        然后将窗口大小减小 1，并将α和β的值都减小 1，

        ```
        cwnd = cwnd – 1,
        α = α -1,
        β = β -1
        ```

    3.  Else if value of alpha is 1 i.e,

        ```
        α = 1
        ```

        然后，将窗口大小增加 1。

*   **Case-3 :**
    If the value of diff is greater than beta i.e,

    ```
    diff > β
    ```

    然后，增加将窗口的大小减少 1，也将α和β的值减少 1。

    ```
    cwnd = cwnd -1
    α = α - 1
    β = β - 1
    ```

    在维加斯 A 中，较小的 if diff 值并不总是意味着系统中的带宽利用率较低，因为可能存在 alpha 值较大的情况，但是当拥塞发生时，较小的吞吐量值仍然可以使 diff 小于 alpha。因此，我们需要减小窗口大小以及α和β的值。