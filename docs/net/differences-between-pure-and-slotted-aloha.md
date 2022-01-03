# 纯芦荟和开槽芦荟的区别

> 原文:[https://www . geeksforgeeks . org/pure 和 slot-aloha 之间的差异/](https://www.geeksforgeeks.org/differences-between-pure-and-slotted-aloha/)

先决条件–[计算机网络|多址协议](https://www.geeksforgeeks.org/computer-network-multiple-access-protocols/)
Aloha 是随机接入协议的类型，它有两种类型一种是**纯 Aloha** ，另一种是**时隙 Aloha** 。
在 Pure Aloha 中，只要数据在任意时间可用，站点就会进行传输，碰撞帧会被破坏。在时隙 aloha 中，要求站等待下一个时隙的开始进行传输。与纯阿洛哈相比，脆弱期减半。

现在，我们将看到这些协议之间的区别:

<center>

| S.NO | 纯阿洛哈 | 开槽 Aloha |
| 1. | 在这个 aloha 中，任何站都可以随时传输数据。 | 在这种情况下，任何站都可以在任何时隙的开始发送数据。 |
| 2. | 在这种情况下，时间是连续的，并且不是全局同步的。 | 在这种情况下，时间是离散的，并且是全局同步的。 |
| 3. | 纯阿洛哈的脆弱时间
= 2 x Tt | 时隙 aloha 的易受攻击时间
= Tt |
| 4. | 在纯 Aloha 中，数据包成功传输的概率

```
= G x e-2G
```

 | 在时隙 Aloha 中，数据包成功传输的概率 |

</center>

```
= G x e-G
```

5.在纯阿洛哈，最大效率

```
= 18.4%
```

在时隙 aloha 中，最大效率

```
= 36.8%
```

6.纯 aloha 不会将碰撞次数减少一半。Slotted aloha reduces the number of collisions to half and doubles the efficiency of pure aloha.