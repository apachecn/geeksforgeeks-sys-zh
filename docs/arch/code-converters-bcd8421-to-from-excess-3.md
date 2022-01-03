# 代码转换器–BCD(8421)至/自超额-3

> 原文:[https://www . geesforgeks . org/code-converters-BCD 8421-转自超额-3/](https://www.geeksforgeeks.org/code-converters-bcd8421-to-from-excess-3/)

**先决条件–**[数字系统和基数转换](https://www.geeksforgeeks.org/number-system-and-base-conversions/)

超额-3 二进制码是**未加权自补** BCD 码。
自补性质是指一个超额 3 数的 1 的补码是相应十进制数的 9 的补码的超额 3 码。这个属性很有用，因为十进制数可以像二进制数可以被 1 补一样容易地被 9 补(用于减法)；只需反转所有位。
比如 3(0011)的超额-3 码是 0110，要找到 3 补码的超额-3 码，我们只需要找到 0110 - > 1001 的 1 补码，这也是 3 的 9 补码的超额-3 码- > (9-3) = 6。

### 将 BCD(8421)转换为超额-3-

正如名字所表明的，一个 BCD 数字可以通过简单地加 3 转换成它对应的超额-3 代码。
设![A,\:B,\:C,\:and\:D](img/ee24029f58c5c7bc83e49cef4ff77456.png "Rendered by QuickLaTeX.com")为代表二进制数的位，其中![D](img/4bf58c30470f92164b71a158e9fd8b22.png "Rendered by QuickLaTeX.com")为 LSB，![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")为 MSB，
设![w,\:x,\:y,\:and\:z](img/e451f912b5426268b2308c2b0e4b188c.png "Rendered by QuickLaTeX.com")为代表二进制数格雷码的位，其中![z](img/bfd03be88bf95b51b8145f4395cca36b.png "Rendered by QuickLaTeX.com")为 LSB，![w](img/b27d57e3f417abb002a05eaa8a1ff42e.png "Rendered by QuickLaTeX.com")为 MSB。
转换真值表如下。X 标记不在乎条件。
![ \begin{tabular}{||c|c|c|c||c|c|c|c||} \hline  \multicolumn{4}{||c||}{BCD(8421)} & \multicolumn{4}{|c||}{Excess-3}\\ \hline  A & B & C & D & w & x & y & z \\ \hline \hline  0 & 0 & 0 & 0 & 0 & 0 & 1 & 1 \\  \hline  0 & 0 & 0 & 1 & 0 & 1 & 0 & 0 \\  \hline  0 & 0 & 1 & 0 & 0 & 1 & 0 & 1 \\  \hline  0 & 0 & 1 & 1 & 0 & 1 & 1 & 0 \\  \hline \hline  0 & 1 & 0 & 0 & 0 & 1 & 1 & 1 \\  \hline  0 & 1 & 0 & 1 & 1 & 0 & 0 & 0 \\  \hline  0 & 1 & 1 & 0 & 1 & 0 & 0 & 1 \\  \hline  0 & 1 & 1 & 1 & 1 & 0 & 1 & 0 \\  \hline \hline  1 & 0 & 0 & 0 & 1 & 0 & 1 & 1 \\  \hline  1 & 0 & 0 & 1 & 1 & 1 & 0 & 0 \\  \hline  1 & 0 & 1 & 0 & X & X & X & X \\  \hline  1 & 0 & 1 & 1 & X & X & X & X \\  \hline \hline  1 & 1 & 0 & 0 & X & X & X & X \\  \hline  1 & 1 & 0 & 1 & X & X & X & X \\  \hline  1 & 1 & 1 & 0 & X & X & X & X \\ \hline  1 & 1 & 1 & 1 & X & X & X & X \\ \hline \hline \end{tabular} ](img/dcd7200cd26a857b859ee0807785f18b.png "Rendered by QuickLaTeX.com")
为了找到相应的数字电路，我们将使用 K-Map 技术，将每个超额 3 码位作为输出，将 BCD 号的所有位作为输入。

![35777](img/3ad512ff5e7cbb563aeea15c2c029e36.png)

对应的最小化布尔表达式为超额-3 位代码–
![ w = A+BC+BD\\ x = B^\prime C + B^\prime D +BC^\prime D^\prime\\ y = CD + C^\prime D^\prime \\ z = D^\prime ](img/5ecf20efc4acdef67cd03c2128bad10c.png "Rendered by QuickLaTeX.com")
对应的数字电路-
![](img/9326507da36744bbc9059a8127d40f9e.png)

### 将超额-3 转换为 BCD(8421)–

多余的-3 代码可以以同样的方式转换回 BCD。
设![A,\:B,\:C,\:and\:D](img/ee24029f58c5c7bc83e49cef4ff77456.png "Rendered by QuickLaTeX.com")为代表二进制数的位，其中![D](img/4bf58c30470f92164b71a158e9fd8b22.png "Rendered by QuickLaTeX.com")为 LSB，![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")为 MSB，
设![w,\:x,\:y,\:and\:z](img/e451f912b5426268b2308c2b0e4b188c.png "Rendered by QuickLaTeX.com")为代表二进制数格雷码的位，其中![z](img/bfd03be88bf95b51b8145f4395cca36b.png "Rendered by QuickLaTeX.com")为 LSB，![w](img/b27d57e3f417abb002a05eaa8a1ff42e.png "Rendered by QuickLaTeX.com")为 MSB。
转换真值表如下。X 标记不在乎条件。
![ \begin{tabular}{||c|c|c|c||c|c|c|c||} \hline  \multicolumn{4}{||c||}{Excess-3} & \multicolumn{4}{|c||}{BCD}\\ \hline  w & x & y & z & A & B & C & D \\ \hline \hline  0 & 0 & 0 & 0 & X & X & X & X \\  \hline  0 & 0 & 0 & 1 & X & X & X & X \\  \hline  0 & 0 & 1 & 0 & X & X & X & X \\  \hline  0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 \\  \hline \hline  0 & 1 & 0 & 0 & 0 & 0 & 0 & 1 \\  \hline  0 & 1 & 0 & 1 & 0 & 0 & 1 & 0 \\  \hline  0 & 1 & 1 & 0 & 0 & 0 & 1 & 1 \\  \hline  0 & 1 & 1 & 1 & 0 & 1 & 0 & 0 \\  \hline \hline  1 & 0 & 0 & 0 & 0 & 1 & 0 & 1 \\  \hline  1 & 0 & 0 & 1 & 0 & 1 & 1 & 0 \\  \hline  1 & 0 & 1 & 0 & 0 & 1 & 1 & 1 \\  \hline  1 & 0 & 1 & 1 & 1 & 0 & 0 & 0 \\  \hline \hline  1 & 1 & 0 & 0 & 1 & 0 & 0 & 1 \\  \hline  1 & 1 & 0 & 1 & X & X & X & X \\  \hline  1 & 1 & 1 & 0 & X & X & X & X \\ \hline  1 & 1 & 1 & 1 & X & X & X & X \\ \hline \hline \end{tabular} ](img/60a9c7c1e73e388e0cbc1aa0f93dec9c.png "Rendered by QuickLaTeX.com")
K-Map 为 D-
![](img/62312616373a831dd794a9edd1b6608e.png)
K-Map 为 C-
![](img/d3a9810fc3f8f11b32cf5f5b99412b1c.png)
K-Map 为 B-
![](img/88fd59c6e546fadc9f401ce187e4f2e8.png)
K-Map 为 A-
<img src =![](img/838a5c1615ffb51e58dd5a8f24065b95.png)
对应的最小化布尔表达式为超额-3 位代码–
![ A = wx+wyz\\ B = x^\prime y^\prime + x^\prime z^\prime +xyz\\ C = y^\prime z+ yz^\prime \\ D = z^\prime ](img/52a2a8afd178eceda32da0e8ca47c244.png "Rendered by QuickLaTeX.com")
对应的数字电路–
这里![E_3,\:E_2,\:E_1,\:and\:E_0](img/647fbb69775d1552af91d88e51baa4ff.png "Rendered by QuickLaTeX.com")对应的是![w,\:x,\:y,\:and\:z](img/e451f912b5426268b2308c2b0e4b188c.png "Rendered by QuickLaTeX.com")和【T39】

![Excess-3 to BCD](img/783f5b0f3275928e6f3a0d47b262f82e.png)

**参考文献-**

数字设计，第五版，由莫里斯·马诺和迈克尔·西莱蒂编辑
[overseas-3–维基百科](https://en.wikipedia.org/wiki/Excess-3)

本文由**奇拉·曼瓦尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。