# DBMS 中函数依赖的阿姆斯特朗公理

> 原文:[https://www . geesforgeks . org/Armstrong GS-公理-函数中的公理-依赖于数据库管理系统/](https://www.geeksforgeeks.org/armstrongs-axioms-in-functional-dependency-in-dbms/)

**先决条件–**[功能依赖关系](https://www.geeksforgeeks.org/database-normalization-introduction/)

阿姆斯特朗公理一词是指由威廉·w·阿姆斯特朗引入的一套完整的推理规则或公理，用于测试**函数依赖**的逻辑蕴涵。如果 F 是一组函数依赖，那么 F 的闭包，表示为![F^+    ](img/cf79c53d35d1e8716204a7256e2b6403.png "Rendered by QuickLaTeX.com")，是由 F .阿姆斯壮的公理在逻辑上隐含的所有函数依赖的集合，是一组规则，当重复应用时，生成函数依赖的闭包。

### 公理–

1.  **反身性公理–**
    如果![{\displaystyle A}    ](img/97fe8a5ffce5bc6838186bba16ea881e.png "Rendered by QuickLaTeX.com")是一组属性，![{\displaystyle B}    ](img/2327b2258a9e15dd3baf0bc92420972e.png "Rendered by QuickLaTeX.com")是![{\displaystyle A}    ](img/97fe8a5ffce5bc6838186bba16ea881e.png "Rendered by QuickLaTeX.com")的子集，那么![{\displaystyle A}    ](img/97fe8a5ffce5bc6838186bba16ea881e.png "Rendered by QuickLaTeX.com")成立![{\displaystyle B}    ](img/2327b2258a9e15dd3baf0bc92420972e.png "Rendered by QuickLaTeX.com")。如果![{\displaystyle B\subseteq A}    ](img/6f0f014a5bde5810d6458c30a0fc9f09.png "Rendered by QuickLaTeX.com")那么![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")这个属性就是微不足道的属性。
2.  **扩增公理–**
    如果![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")成立，![{\displaystyle Y}    ](img/9766ea1b8edcc177339bb917d4532285.png "Rendered by QuickLaTeX.com")为属性集，那么![{\displaystyle AY\to BY}    ](img/ee8a69f189da669e5dabd5bc37fd7f3b.png "Rendered by QuickLaTeX.com")也成立。即在依赖项中添加属性，不会改变基本的依赖项。如果![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")，则![{\displaystyle AC\to BC}    ](img/e69b99a669d80fb1f1143c58c935b3fb.png "Rendered by QuickLaTeX.com")为任意![{\displaystyle C}    ](img/d1d9d15e327a7eec7bf3d87e51235211.png "Rendered by QuickLaTeX.com")。
3.  **及物性公理–**
    同代数中的及物性规则，如果![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")成立，![{\displaystyle B\to C}    ](img/ca28625378d62954fe1d9574b73541c2.png "Rendered by QuickLaTeX.com")成立，那么![{\displaystyle A\to C}    ](img/3a46d80aa6a9b77d346785e0b3923b5b.png "Rendered by QuickLaTeX.com")也成立。![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")在功能上被称为![{\displaystyle A}    ](img/97fe8a5ffce5bc6838186bba16ea881e.png "Rendered by QuickLaTeX.com")，决定![{\displaystyle B}    ](img/2327b2258a9e15dd3baf0bc92420972e.png "Rendered by QuickLaTeX.com")。如果![{\displaystyle X\to Y}    ](img/f9ca8203dd4b8fcf06839112d4d7c4ff.png "Rendered by QuickLaTeX.com")和![{\displaystyle Y\to Z}    ](img/d9b1095651d887d99aea30bf7ae9a806.png "Rendered by QuickLaTeX.com")，那么![{\displaystyle X\to Z}](img/866f7a5df5863c0f3c4e10174eb80636.png "Rendered by QuickLaTeX.com")

### 次要规则–

这些规则可以从上述公理中推导出来。

1.  **联合–**
    如果![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")成立![{\displaystyle A\to C}    ](img/3a46d80aa6a9b77d346785e0b3923b5b.png "Rendered by QuickLaTeX.com")成立，那么![{\displaystyle A\to BC}    ](img/36edd397ede5a135062916c2c12e6d0f.png "Rendered by QuickLaTeX.com")成立。如果![{\displaystyle X\to Y}    ](img/f9ca8203dd4b8fcf06839112d4d7c4ff.png "Rendered by QuickLaTeX.com")和![{\displaystyle X\to Z}    ](img/2726c0afc6b3c17e1e8cda615ca212e9.png "Rendered by QuickLaTeX.com")然后![{\displaystyle X\to YZ} ](img/a784c5dd5e54e35b1af70523efe88739.png "Rendered by QuickLaTeX.com")
2.  **成分–**
    如果![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")![{\displaystyle X\to Y}    ](img/f9ca8203dd4b8fcf06839112d4d7c4ff.png "Rendered by QuickLaTeX.com")成立，那么![{\displaystyle AX\to BY}    ](img/b0c472500665a95c8ae0ee60508c26c1.png "Rendered by QuickLaTeX.com")成立。
3.  **分解–**
    如果![{\displaystyle A\to BC}    ](img/36edd397ede5a135062916c2c12e6d0f.png "Rendered by QuickLaTeX.com")成立，那么![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")和![{\displaystyle A\to C}    ](img/3a46d80aa6a9b77d346785e0b3923b5b.png "Rendered by QuickLaTeX.com")成立。如果![{\displaystyle X\to YZ}    ](img/d2dd6343080160e6b6562970a87ba088.png "Rendered by QuickLaTeX.com")然后![{\displaystyle X\to Y}    ](img/f9ca8203dd4b8fcf06839112d4d7c4ff.png "Rendered by QuickLaTeX.com")和![{\displaystyle X\to Z} ](img/be3b7c2c1bdfbdbf9653c0edf25eb247.png "Rendered by QuickLaTeX.com")
4.  **伪及物性–**
    如果![{\displaystyle A\to B}    ](img/e072c89576d1f421ad47b64c7b9db27a.png "Rendered by QuickLaTeX.com")成立，![{\displaystyle BC\to D}    ](img/26044604830b0a10890338100e09bb20.png "Rendered by QuickLaTeX.com")成立，那么![{\displaystyle AC\to D}    ](img/6dd48a52e06146afabb843a9035af1e3.png "Rendered by QuickLaTeX.com")成立。如果![{\displaystyle X\to Y}    ](img/f9ca8203dd4b8fcf06839112d4d7c4ff.png "Rendered by QuickLaTeX.com")和![{\displaystyle YZ\to W}    ](img/178b8b4e2fe8895ad65276fb1c06bb2f.png "Rendered by QuickLaTeX.com")然后![{\displaystyle XZ\to W}    ](img/d7674ddcbef9a826e7efd0a1a315cf62.png "Rendered by QuickLaTeX.com")。

**为什么阿姆斯特朗公理指的是声音和完整？**
通过声音，我们意味着给定一组在关系模式 R 上指定的函数依赖 F，我们可以通过使用阿姆斯特朗公理的主要规则从 F 中推断出的任何依赖在满足 F 中的依赖的 R 的每个关系状态 R 中都成立。
通过完成，我们意味着重复使用阿姆斯特朗公理的主要规则来推断依赖，直到不能推断出更多的依赖，导致可以从 F 中推断出的所有可能依赖的完整集合

**参考文献–**

*   书籍–[数据库系统基础](https://amzn.to/3j834dt)
*   [http://tinman.cs.gsu.edu](http://tinman.cs.gsu.edu/~raj/4710/sp08/fd-theory.pdf)

本文由 **Samit Mandal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。