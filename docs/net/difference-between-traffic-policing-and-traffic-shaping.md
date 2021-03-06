# 交通监管与交通塑造的区别

> 原文:[https://www . geeksforgeeks . org/流量监管和流量整形的区别/](https://www.geeksforgeeks.org/difference-between-traffic-policing-and-traffic-shaping/)

**1。交通监管:**
交通监管基本上是一种机制，通过对符合指定速率的数据包采取行动来监控任何网络中的流量。网络中的策略会检查存储桶中的令牌数量。在流量监管中，一个令牌通常代表一个字节的流量。它可用于控制入站和出站流量。它还保持对过量流量的控制。

**2。流量整形:**
流量整形基本上是一种拥塞控制机制，它延迟一些数据包，使其与其他流量分量持平。它增加了数据包的延迟和带宽。它通过给数据包一些延迟，使流量符合一定的速率。流量整形只能用于控制出站流量。它还对数据包进行排队。

**交通监管与交通塑造的区别:**

<center>

| 没有 | 交通警察 | 流量整形 |
| --- | --- | --- |
| 1. | 流量监管是一种监控任何网络流量的机制。 | 流量整形是一种拥塞控制机制，会导致数据包延迟。 |
| 2. | 速率大于流量监管速率的数据包将被丢弃。 | 它缓冲速率大于流量整形速率的数据包。 |
| 3. | 交通警察不会造成延误。 | 流量整形会导致数据包延迟。 |
| 4. | 令牌值以每秒字节数计算。 | 令牌值以每秒位数计算。 |
| 5. | 在交通监管中，不执行交通排队。 | 流量整形中不执行流量排队。 |
| 6. | 交通监管支持交通评论。 | 流量整形不支持流量评论。 |
| 7. | 流量监管可用于控制出站或入站流量。 | 交通监管只能用于控制出站流量。 |

</center>