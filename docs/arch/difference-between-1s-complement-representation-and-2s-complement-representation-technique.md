# 1 补码表示和 2 补码表示技术的区别

> 原文:[https://www . geesforgeks . org/difference-1s-补语-表象-和-2s-补语-表象-技术/](https://www.geeksforgeeks.org/difference-between-1s-complement-representation-and-2s-complement-representation-technique/)

先决条件–[负二进制数的表示](https://www.geeksforgeeks.org/representation-of-negative-binary-numbers/)

**一个二进制数的 1 的补码**是另一个二进制数，通过切换其中的所有位获得，即将 0 位转换为 1，将 1 位转换为 0。

示例:

```
Let numbers be stored using 4 bits

1's complement of 7 (0111) is 8 (1000)
1's complement of 12 (1100) is 3 (0011)

```

**二进制数的 2 补码**是将 1 加到二进制数的 1 补码上。
例子:

```
Let numbers be stored using 4 bits

2's complement of 7 (0111) is 9 (1001)
2's complement of 12 (1100) is 4 (0100)

```

这些表示用于带符号的数字。

**1 的补码和 2 的补码的主要区别**在于 1 的补码有 0(零)–00000000 的两种表示形式，分别为正零(+0)和负零(-0)的 11111111；而在 2 的补码中，零只有一种表示形式–000000000 (+0)，因为如果我们将 1 与 111111111(-1)相加，我们会得到 00000000(+0)，它与正零相同。这就是为什么通常使用 2 的补码的原因。

另一个不同之处是，在用 1 的补码加数时，我们首先进行二进制加法，然后加入一个循环进位值。但是，2 的补码只有一个零值，并且不需要进位值。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论