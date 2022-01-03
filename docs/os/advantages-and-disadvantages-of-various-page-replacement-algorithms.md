# 各种页面替换算法的优缺点

> 原文:[https://www . geesforgeks . org/各种页面替换算法的优缺点/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-various-page-replacement-algorithms/)

[页面调度](https://www.geeksforgeeks.org/page-replacement-algorithms-in-operating-systems/)，涉及很多不同的算法，各有利弊。

**1。[先进先出(FIFO)](https://www.geeksforgeeks.org/program-page-replacement-algorithms-set-2-fifo/) :**

*   Advantages-
    1.  Easy to understand & implement.
*   Disadvantages–

1.  过程有效性低。
2.  当我们在使用先进先出的同时增加帧数时，我们给了进程更多的内存。所以，页面错误应该会减少，但这里的页面错误会增加。这个问题被称为[贝拉蒂异常](https://www.geeksforgeeks.org/beladys-anomaly-in-page-replacement-algorithms/)。
3.  每一帧都需要考虑。

**2。[最近最少使用(LRU)](https://www.geeksforgeeks.org/program-for-least-recently-used-lru-page-replacement-algorithm/) :**

*   Advantages-
    1.  Open and comprehensive analysis.
    2.  In this case, we replace the least recently used pages, thus getting rid of the exception of Baylatry.
    3.  Select pages that are prone to failure and have not been used for a long time.
*   Disadvantages–
    1.  Additional data structures need to be implemented.
    2.  Hardware assist high.

**3。[最优页面替换(OPR)](https://www.geeksforgeeks.org/optimal-page-replacement-algorithm/) :**

*   Advantages-
    1.  Lower complexity and easy implementation.
    2.  Little assistance is needed, that is, the data structure used is simple and light.
*   Disadvantages–
    1.  OPR is perfect, but it is practically impossible, because the operating system cannot know the future requests.
    2.  Handling mistakes is tricky.

虽然先进先出和 LRU 各有优缺点，但 OPR 被用作衡量其他算法性能的基准。因此根据情况使用适当的算法。