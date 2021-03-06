# 返回-N 和选择性重复协议的区别

> 原文:[https://www . geesforgeks . org/back-n-and-selected-repeat-protocol/](https://www.geeksforgeeks.org/difference-between-go-back-n-and-selective-repeat-protocol/)

[回退 N 协议](https://www.geeksforgeeks.org/sliding-window-protocol-set-2-receiver-side/)和[选择性重复协议](https://www.geeksforgeeks.org/sliding-window-protocol-set-3-selective-repeat/)都是滑动窗口协议的类型。
这两种协议的主要区别在于，在发现发送帧中的可疑或损坏后，back-n 协议会重新传输所有帧，而选择性重复协议只会重新传输损坏的帧。

现在，我们将看到它们之间的区别:

| S.NO | 后退协议 | 选择性重复协议 |
| 1. | 在回退协议中，如果发现发送的帧可疑，则所有帧都将从丢失的数据包重新发送到发送的最后一个数据包。 | 在选择性重复协议中，只有那些被发现可疑的帧才被重新传输。 |
| 2. | 回退协议的发送方窗口大小为 N | 选择性重复协议的发送方窗口大小也是 n |
| 3. | 回退协议的接收窗口大小为 1。 | 选择性重复协议的接收器窗口大小为 n |
| 4. | 回退协议没有那么复杂。 | 选择性重复协议更复杂。 |
| 5. | 在回退协议中，发送方和接收方都不需要排序。 | 在选择性重复协议中，接收端需要排序来对帧进行排序。 |
| 6. | 在回退协议中，确认类型是累积的。 | 在选择性重复协议中，确认类型是独立的。 |
| 7. | 在回退协议中，无序数据包不被接受(丢弃)，整个窗口被重新传输。 | 在选择性重复协议中，无序数据包被接受。 |
| 8. | 在回退协议中，如果接收方收到一个损坏的数据包，那么整个窗口也会被重新传输。 | 在选择性重复协议中，如果 receive 收到损坏的数据包，它会立即发送否定确认，因此只有选择性数据包会被重新传输。 |
| 9. | 回退 N 协议的效率为

```
N/(1+2*a)
```

 | 选择性重复协议的效率也是

```
N/(1+2*a)
```

 |