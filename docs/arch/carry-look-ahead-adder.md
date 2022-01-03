# 进位前瞻加法器

> 原文:[https://www.geeksforgeeks.org/carry-look-ahead-adder/](https://www.geeksforgeeks.org/carry-look-ahead-adder/)

**超前进位加法器背后的动机:**
在波纹进位加法器中，对于每个加法器块，要相加的两位立即可用。然而，每个加法器块等待进位从它的前一个块到达。因此，在输入进位已知之前，不可能产生任何块的和与进位。![i^{th}  ](img/6c2072c717999afbfc304ed61f455daa.png "Rendered by QuickLaTeX.com")区块等待![i-1^{th}  ](img/f52c4d16e6cfbbd6cc8fb8f11edd09d4.png "Rendered by QuickLaTeX.com")区块产生进位。因此会有相当大的时间延迟，即载波传播延迟。

![](img/f1c93b45114fce8847433342692542d2.png)

考虑上述 4 位纹波进位加法器。一旦输入信号加到相应的全加器上，该和![S_{3}  ](img/8e125970a9365377e28d69832ad644b2.png "Rendered by QuickLaTeX.com")就由全加器产生。但是进位输入![C_{4}  ](img/798738058973776a434131d10d90b5e0.png "Rendered by QuickLaTeX.com")在其最终稳态值上不可用，直到进位![C_{3}  ](img/f56b8cd02b17d8980b5d30bf02bc8e9f.png "Rendered by QuickLaTeX.com")在其稳态值上可用。同样![C_{3}  ](img/f56b8cd02b17d8980b5d30bf02bc8e9f.png "Rendered by QuickLaTeX.com")取决于![C_{2}  ](img/2fdad1f918b29b715b26fe723421ab9b.png "Rendered by QuickLaTeX.com")![C_{2}  ](img/2fdad1f918b29b715b26fe723421ab9b.png "Rendered by QuickLaTeX.com")取决于![C_{1}  ](img/f873b72cf75bbed030e35114eba6ca36.png "Rendered by QuickLaTeX.com")。因此，尽管进位必须传播到所有级，以便输出![S_{3}  ](img/8e125970a9365377e28d69832ad644b2.png "Rendered by QuickLaTeX.com")和进位![C_{4}  ](img/798738058973776a434131d10d90b5e0.png "Rendered by QuickLaTeX.com")确定它们的最终稳态值。

传播时间等于每个加法器块的传播延迟乘以电路中加法器块的数量。例如，如果每个全加器级具有 20 纳秒的传播延迟，那么![S_{3}  ](img/8e125970a9365377e28d69832ad644b2.png "Rendered by QuickLaTeX.com")将在 60 (20 × 3)纳秒后达到其最终正确值。如果我们扩展级数以增加位数，情况会变得更糟。

**超前进位加法器:**
超前进位加法器通过引入更复杂的硬件来减少传播延迟。在该设计中，波纹进位设计被适当地变换，使得加法器的固定比特组上的进位逻辑被简化为两级逻辑。让我们详细讨论一下设计。

![](img/bc5c77a27b6dc5015910fc626d9eb031.png)

![](img/51070af54259dec1a7a3df86924201ca.png)

考虑上面所示的全加器电路和相应的真值表。我们将两个变量定义为**【进位生成】** ![G_{i}  ](img/ab215945f6d6ed439e19f5a190524fbf.png "Rendered by QuickLaTeX.com")和**【进位传播】** ![P_{i}  ](img/9a88b5de31d5c52c9077550d8018d488.png "Rendered by QuickLaTeX.com")然后，
![P_{i} = A_{i} \oplus B_{i} \newline G_{i} = A_{i} B_{i}  ](img/ebf359b4895a34a6ab9b9e5c0ae0bd77.png "Rendered by QuickLaTeX.com")

求和输出和进位输出可以用进位生成![G_{i}  ](img/ab215945f6d6ed439e19f5a190524fbf.png "Rendered by QuickLaTeX.com")和进位传播![P_{i}  ](img/9a88b5de31d5c52c9077550d8018d488.png "Rendered by QuickLaTeX.com")来表示，如下所示

![S_{i} = P_{i} \oplus C_{i} \newline C_{i+1} = G_{i} + P_{i} C_{i}  ](img/e1ac5ff9d7a8617c8fe17f278e22ebff.png "Rendered by QuickLaTeX.com")
其中![G_{i}  ](img/ab215945f6d6ed439e19f5a190524fbf.png "Rendered by QuickLaTeX.com")在![A_{i}  ](img/8102e36d1cc43e288e192d192559e3a8.png "Rendered by QuickLaTeX.com")、![B_{i}  ](img/7425dbbda2fd161015a966a4317d1e81.png "Rendered by QuickLaTeX.com")均为 1 时产生进位，与输入进位无关。![P_{i}  ](img/9a88b5de31d5c52c9077550d8018d488.png "Rendered by QuickLaTeX.com")与进位从![C_{i}  ](img/fa9c254780d5c7cc4b761273c6c28b92.png "Rendered by QuickLaTeX.com")到![C_{i + 1}  ](img/d4145738f42ba5c803418d75454dbb92.png "Rendered by QuickLaTeX.com")的传播有关。

4 级超前进位加法器中每一级的进位输出布尔函数可以表示为

![C_{1} = G_{0} + P_{0} C_{in} \newline C_{2} = G_{1} + P_{1} C_{1} = G_{1} + P_{1} G_{0} + P_{1} P_{0} C_{in} \newline C_{3} = G_{2} + P_{2} C_{2} = G_{2} + P_{2} G_{1} + P_{2} P_{1} G_{0} + P_{2} P_{1} P_{0} C_{in} \newline C_{4} = G_{3} + P_{3} C_{3} = G_{3} + P_{3} G_{2} + P_{3} P_{2} G_{1} + P_{3} P_{2} P_{1} G_{0} + P_{3} P_{2} P_{1} P_{0} C_{in} \newline  ](img/0b97e993cc73304e8c123d5ae01aba79.png "Rendered by QuickLaTeX.com")

从上面的布尔方程我们可以观察到![C_{4}  ](img/798738058973776a434131d10d90b5e0.png "Rendered by QuickLaTeX.com")不需要等待![C_{3}  ](img/f56b8cd02b17d8980b5d30bf02bc8e9f.png "Rendered by QuickLaTeX.com")和![C_{2}  ](img/2fdad1f918b29b715b26fe723421ab9b.png "Rendered by QuickLaTeX.com")传播，实际上![C_{4}  ](img/798738058973776a434131d10d90b5e0.png "Rendered by QuickLaTeX.com")是与![C_{3}  ](img/f56b8cd02b17d8980b5d30bf02bc8e9f.png "Rendered by QuickLaTeX.com")和![C_{2}  ](img/2fdad1f918b29b715b26fe723421ab9b.png "Rendered by QuickLaTeX.com")同时传播的。由于每个进位输出的布尔表达式都是乘积之和，因此可以用一级与门后跟一个或门来实现。

下图显示了超前进位发生器的每个进位输出(![C_{2}  ](img/2fdad1f918b29b715b26fe723421ab9b.png "Rendered by QuickLaTeX.com")、![C_{3}  ](img/f56b8cd02b17d8980b5d30bf02bc8e9f.png "Rendered by QuickLaTeX.com")和![C_{4}  ](img/798738058973776a434131d10d90b5e0.png "Rendered by QuickLaTeX.com"))的三个布尔函数的实现。

![](img/f03a26edea4a2959fc4b307f9bdccc6f.png)

**时间复杂度分析:**
我们可以把超前进位加法器想象成由两个“部分”
组成

1.  计算每个位的进位的部分。
2.  将输入位和每个位位置的进位相加的部分。

![log(n)  ](img/96aa98ced862430611459e59c24fe923.png "Rendered by QuickLaTeX.com")复杂性来自产生进位的部分，而不是增加位的电路。
现在，为了生成![n^{th}  ](img/2a0f6754367cb82827f9b31fedae0c11.png "Rendered by QuickLaTeX.com")进位位，我们需要在(n+1)个输入之间执行“与”运算。加法器的复杂性归结于我们如何执行这个“与”运算。如果我们有与门，每个与门的扇入(接受的输入数)为 k，那么我们可以在![log_{k}(n+1)  ](img/f0879a725a71b961d04068d3ebe958e0.png "Rendered by QuickLaTeX.com")时间内找到所有位的与门。这用渐近符号表示为![\Theta(log n)  ](img/9c9e57b2e78171526fd75ae7b2e95278.png "Rendered by QuickLaTeX.com")。

**超前进位加法器的优缺点:**
**优点–**

*   传播延迟减少。
*   它提供了最快的加法逻辑。

**劣势–**

*   随着变量数量的增加，超前进位加法器电路变得复杂。
*   该电路成本更高，因为它涉及更多的硬件。

**GATE CS 角题**

练习下列问题将帮助你测试你的知识。所有的问题在前几年的 GATE 考试或 GATE 模拟考试中都被问过。强烈建议你练习一下。

1.  [GATE CS 2016(第 1 集)，第 43 题](https://www.geeksforgeeks.org/gate-gate-cs-2016-set-1-question-43/)
2.  [GATE CS 2004，第 90 题](https://www.geeksforgeeks.org/gate-gate-cs-2004-question-62/)
3.  [GATE CS 2007，问题 85](https://www.geeksforgeeks.org/gate-gate-cs-2007-question-35/)
4.  [GATE CS 2006，问题 85](https://www.geeksforgeeks.org/gate-gate-cs-2006-question-36/)
5.  [GATE CS 1997，问题 15](https://www.geeksforgeeks.org/gate-gate-cs-1997-question-15/)

**参考资料–**
[虚拟实验室](http://cse10-iitkgp.virtual-labs.ac.in/cla_design.html)
[超前进位加法器–维基百科](https://en.wikipedia.org/wiki/Carry-lookahead_adder)