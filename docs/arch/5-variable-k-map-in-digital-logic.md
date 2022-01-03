# 数字逻辑中的 5 变量 K 图

> 原文:[https://www . geeksforgeeks . org/5-数字逻辑中的变量-k-map/](https://www.geeksforgeeks.org/5-variable-k-map-in-digital-logic/)

先决条件–[K-Map 中的隐含](https://www.geeksforgeeks.org/digital-logic-implicants-k-map/)
**[卡诺图](https://www.geeksforgeeks.org/k-mapkarnaugh-map/)** 或 K-Map 是编写真值表的替代方法，用于布尔表达式的简化。至此我们熟悉了 3 变量 K-Map & 4 变量 K-Map。现在，让我们详细讨论一下 5 变量 K-Map。

任何包含 5 个变量的布尔表达式或函数都可以用 5 变量 K-Map 求解。这样一个 5 变量 K-Map 必须包含 **![$2^{5}$](img/aefd523c0281a946c3d70ce7249a9f4b.png "Rendered by QuickLaTeX.com") = 32 个单元格**。让 5 变量布尔函数表示为:
**f ( P Q R S T)** 其中 P、Q、R、S、T 为变量，P 为最高有效位变量，T 为最低有效位变量。

标准操作程序表达式的这种 K 图的结构如下所示:

![](img/a8a18c2f2299718289be03f99eb50aaf.png)

从这里描述的例子可以理解每个单元对应的单元号:
![](img/3e7aebffd43abd7f29c9edeabb872320.png)

这里对于变量 **P=0，我们有 Q = 0，R = 1，S = 1，T = 1 即(PQRST)=(00111)** 。在十进制形式中，这相当于 **7** 。因此，对于上面显示的单元格，对应的单元格编号= 7。以类似的方式，我们可以写出对应于每个单元格的单元格号，如上图所示。
现在让我们讨论如何使用 5 变量 K-Map 来最小化布尔函数。

<u>***需遵守的规则:***</u>

1.  如果一个函数以紧致规范 SOP(乘积和)的形式给出，那么我们在相应的单元号中写下对应于每个小项(问题中提供)的**“1”**。例如:
    对于![\sum\ m(0, 1, 5, 7, 30, 31)](img/93124f86996a694b4f3e4483cbfba233.png "Rendered by QuickLaTeX.com")，我们将写“1”对应单元号(0，1，5，7，30 和 31)。
2.  如果一个函数是以紧规范 POS(和的乘积)形式给出的，那么我们在相应的单元号中写下**“0”**对应于每个最大项(问题中提供的)。例如:
    对于![\prod\ M(0, 1, 5, 7, 30, 31)](img/f5e1cf8403efa55799fa3d1f7b9a7392.png "Rendered by QuickLaTeX.com")，我们将写“0”对应单元号(0，1，5，7，30 和 31)。

<u>***应遵循的步骤:***</u>

1.  在标准操作程序的情况下，制作尽可能大的子多维数据集，覆盖所有标记为 1 的子多维数据集，或者在位置图的情况下，覆盖所有标记为 0 的子多维数据集。需要注意的是，每个子多维数据集只能包含 2 的幂项。此外，当且仅当在每个单元格的子多维数据集中，我们满足“m”个单元格是“T1”个相邻单元格“T2”时，![$2^{m}$](img/206deef752542b5a842fb449f272b23c.png "Rendered by QuickLaTeX.com")个单元格的子多维数据集中也是可能的。
2.  所有*本质素隐含*必须出现在最小表达式中。

**一、求解 SOP 函数–**
为了清楚理解，我们用下面的表达式求解 5 变量 K-Map 的 SOP 函数最小化的例子:
![\sum\ m(0, 2, 4, 7, 8, 10, 12, 16, 18, 20, 23, 24, 25, 26, 27, 28)](img/8b492ed4ed899e08255329f16bdd250a.png "Rendered by QuickLaTeX.com")

![](img/bd0047f3e25fa6e510cb27aa6091d578.png)

在上面的 K 图中，我们有 4 个子立方体:

*   **<u>子多维数据集 1:</u>** 用红色标记的子多维数据集由单元格(0、4、8、12、16、20、24、28)组成
*   **<u>子代 2:</u>** 蓝色标记的子代由细胞(7，23)组成
*   **<u>子代 3:</u>** 标记为粉红色的子代由细胞(0、2、8、10、16、18、24、26)组成
*   **<u>子代 4:</u>** 黄色标记的子代包括细胞(24、25、26、27)

现在，在编写每个子多维数据集中的最小表达式时，我们将搜索该子多维数据集中所有单元格所共有的文字。

*   **<u>子多维数据集 1</u> :** ![\bar S](img/e6fb637ccf6ad7c67aeebc700fa4687e.png "Rendered by QuickLaTeX.com") ![\bar T](img/7037832cdcdd1bcd93fc31d16e5a53a6.png "Rendered by QuickLaTeX.com")
*   **<u>子多维数据集 2</u> :** ![\bar Q](img/80715fb9c1b50d0daaa9aac5a4498c27.png "Rendered by QuickLaTeX.com") ![R](img/ba4e2d8bd8b5b3f5b8c3d335494a5e65.png "Rendered by QuickLaTeX.com") ![S](img/5f2fc049c461a752012a1cd5851e8d05.png "Rendered by QuickLaTeX.com") ![T](img/a682ee845f0703e8da93b404d1b8820b.png "Rendered by QuickLaTeX.com")
*   **<u>子多维数据集 3</u> :** ![\bar R](img/1b85b45c8e82699feaa37167c78dd270.png "Rendered by QuickLaTeX.com") ![\bar T](img/7037832cdcdd1bcd93fc31d16e5a53a6.png "Rendered by QuickLaTeX.com")
*   **<u>子多维数据集 4</u> :** ![P](img/35fbd389b7039bbdaf3d87058e2c6dbc.png "Rendered by QuickLaTeX.com") ![Q](img/ac6b35cd30d9ce0566e6eefcfcbc240e.png "Rendered by QuickLaTeX.com") ![\bar R](img/1b85b45c8e82699feaa37167c78dd270.png "Rendered by QuickLaTeX.com")

最后给定布尔函数的最小表达式可以表示如下:
![f(P Q R S T) = \bar S](img/299fa457d0720f73c037924718d0ea07.png "Rendered by QuickLaTeX.com")![\bar T](img/7037832cdcdd1bcd93fc31d16e5a53a6.png "Rendered by QuickLaTeX.com")![ + \bar Q](img/25e189363b446abee70d7f96a4c370da.png "Rendered by QuickLaTeX.com")![R](img/ba4e2d8bd8b5b3f5b8c3d335494a5e65.png "Rendered by QuickLaTeX.com")![S](img/5f2fc049c461a752012a1cd5851e8d05.png "Rendered by QuickLaTeX.com")![T](img/a682ee845f0703e8da93b404d1b8820b.png "Rendered by QuickLaTeX.com")![ + \bar R](img/c3f3adeea833c0651fdc2da465c596a3.png "Rendered by QuickLaTeX.com")![\bar T](img/7037832cdcdd1bcd93fc31d16e5a53a6.png "Rendered by QuickLaTeX.com")![ + P](img/753ac3e66b5514038d50a91969772176.png "Rendered by QuickLaTeX.com")![Q](img/ac6b35cd30d9ce0566e6eefcfcbc240e.png "Rendered by QuickLaTeX.com")![\bar R](img/1b85b45c8e82699feaa37167c78dd270.png "Rendered by QuickLaTeX.com")

**二。求解 POS 函数–**
现在，让我们使用以下表达式求解 5 变量 K-Map 的 POS 函数最小化示例:
![\prod\ M(0, 2, 4, 7, 8, 10, 12, 16, 18, 20, 23, 24, 25, 26, 27, 28)](img/2366f2d1dda0174adf4f886ae76e1ca5.png "Rendered by QuickLaTeX.com")

![](img/e0a664e9bf3dcc1164d87db51fbfb7e1.png)

在上面的 K 图中，我们有 4 个子立方体:

*   **<u>子多维数据集 1:</u>** 用红色标记的子多维数据集由单元格(0、4、8、12、16、20、24、28)组成
*   **<u>子代 2:</u>** 蓝色标记的子代由细胞(7，23)组成
*   **<u>子代 3:</u>** 标记为粉红色的子代由细胞(0、2、8、10、16、18、24、26)组成
*   **<u>子代 4:</u>** 黄色标记的子代包括细胞(24、25、26、27)

现在，在编写每个子多维数据集中的最小表达式时，我们将搜索该子多维数据集中所有单元格所共有的文字。

*   **<u>子多维数据集 1</u>:**T4】
*   **<u>子多维数据集 2</u> :** ![Q + \bar R](img/0130dd57608ef4c1b0f9ed4192113072.png "Rendered by QuickLaTeX.com") ![+ \bar S](img/191bc2c54208ba5617a59b9f6c0bb602.png "Rendered by QuickLaTeX.com") ![+ \bar T](img/a9394f8b8a05331009a68bafdf9ed53d.png "Rendered by QuickLaTeX.com")
*   **<u>子多维数据集 3</u>:**T4】
*   **<u>子多维数据集 4</u> :** ![\bar P + \bar Q](img/c30a9a8375ea32d8c4a0c8a9cc9455dd.png "Rendered by QuickLaTeX.com") ![+ R](img/f1abeb9267b5450ecf5a49ddbf1c3a33.png "Rendered by QuickLaTeX.com")

最后，给定布尔函数的最小表达式可以表示如下:
![f(P Q R S T) =  (S + T)(Q + \bar R + \bar S + \bar T)( R + T)(\bar P + \bar Q  + R)](img/31d2cacd7eb471a2428d5d19975f1f5c.png "Rendered by QuickLaTeX.com")

**<u>注</u> :**

1.  对于 5 变量 K-Map，单元格编号的范围将从 0 到![$2^{5}$](img/aefd523c0281a946c3d70ce7249a9f4b.png "Rendered by QuickLaTeX.com") -1，即 0 到 31。
2.  上述术语*“相邻细胞”*是指“仅在一个变量上不同的任何两个细胞”。