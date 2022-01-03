# 布尔函数的表示

> 原文:[https://www . geesforgeks . org/布尔函数的表示/](https://www.geeksforgeeks.org/representation-of-boolean-functions/)

一个**布尔函数**由一个代数表达式描述，该表达式由二进制变量、常数 0 和 1 以及逻辑运算符号![+,\:.\:,\:^\prime](img/846527a49fa3f53186956028d08e3a5d.png "Rendered by QuickLaTeX.com")
组成。对于所涉及的二进制变量的一组给定值，布尔函数可以有 0 或 1 的值。例如，布尔函数![F= x^\prime y + z](img/1e7aa5498e5ddc59a71642a9a3c73e1d.png "Rendered by QuickLaTeX.com")是根据三个二进制变量![x,\:y,\:z](img/2b98e5e42df0135b0820115530f4f9c3.png "Rendered by QuickLaTeX.com")定义的。如果同时![x=0](img/e29cb1d1886d591b16cb88638df4c1cf.png "Rendered by QuickLaTeX.com")和![y=1](img/416e80f0393b37a6068f72117afb8c1e.png "Rendered by QuickLaTeX.com")或![z=1](img/45d73fe55c334bf014ce27d8048610ce.png "Rendered by QuickLaTeX.com")，功能等于 1。
每一个布尔函数都可以用一个代数表达式来表示，比如上面提到的，或者用真值表来表示。一个函数可以通过几个代数表达式来表示，因为它们在逻辑上是等价的，但是每个函数只有一个唯一的真值表。
布尔函数可以从代数表达式转换成由以特定结构连接的逻辑门组成的电路图。![F](img/cb98b8c78f7cc837d4fc2416bdc5861b.png "Rendered by QuickLaTeX.com")电路图–

![](img/5f9af17fdcac2f68a503467dae2064ea.png)

**规范和标准形式–**
任何二元变量都可以采用两种形式之一，![x](img/54a2a70f5ead0a1cc327fc74b8d5495e.png "Rendered by QuickLaTeX.com")或![x^\prime](img/685197e4067a3a4fc5bb01ae20944dc0.png "Rendered by QuickLaTeX.com")。布尔函数可以用![n](img/42ce0a847b20a2f8a781c8a50bdab975.png "Rendered by QuickLaTeX.com")二进制变量来表示。如果所有的二进制变量使用“与”运算组合在一起，那么总共有![2^n](img/364792ee2e3d46fcd847e7915a7e50b5.png "Rendered by QuickLaTeX.com")种组合，因为每个变量可以采取两种形式。
每一种组合称为**小项**或**标准品**。一个小项由![m_i](img/412254ec06233c394f9edebd8084a519.png "Rendered by QuickLaTeX.com")表示，其中![i](img/2c0fdcc58b35808b7d0c28592907fe1a.png "Rendered by QuickLaTeX.com")是指定小项的二进制数的十进制等价物。
**重要提示–**在一个小项中，如果变量为 1，二进制变量是未加引号的，如果变量为 0，即如果小项为![xy^\prime](img/f4a0555bb0c68eb3008267e0fd6b1a37.png "Rendered by QuickLaTeX.com")，那么这意味着![x=1](img/dacebe5816a671095f30795714c024a7.png "Rendered by QuickLaTeX.com")和![y=0](img/68f88b2d4b58a96bf909200ea1985ce5.png "Rendered by QuickLaTeX.com")。
例如，对于两个变量中的布尔函数，最小项是–
![m_0=x^\prime y^\prime,\:m_1=x^\prime y,\:m_2=x y^\prime,\:m_3=x y](img/4f2106c3a80e595e72c19820c18d0409.png "Rendered by QuickLaTeX.com")

类似地，如果变量通过或运算组合在一起，那么得到的项称为**最大项**或**标准和**。最大项由![M_i](img/99111618a7c8e5d6d3465d0479c5421f.png "Rendered by QuickLaTeX.com")表示，其中![i](img/2c0fdcc58b35808b7d0c28592907fe1a.png "Rendered by QuickLaTeX.com")是最大项指定的二进制数的十进制等价物。

**重要提示–**在最大项中，如果变量为 0，则二进制变量未被填充，如果变量为 1，则二进制变量被填充，即如果最大项为![x^\prime+y](img/0fe5283009e39377b2675e79a90f6196.png "Rendered by QuickLaTeX.com")，则意味着![x^\prime=1](img/7ab2aa0825fa0fd878a538ebb2e782b8.png "Rendered by QuickLaTeX.com")和![y=0](img/68f88b2d4b58a96bf909200ea1985ce5.png "Rendered by QuickLaTeX.com")。
例如，对于两个变量的布尔函数，最大项是–
![M_0=x+y,\:M_1=x+y^\prime,\:M_2=x^\prime + y,\:M_3=x^\prime + y^\prime](img/2ecca95709f7ddf5a3fefc3f19cd66c9.png "Rendered by QuickLaTeX.com")

三变量函数的最小项和最大项–

![](img/f113c921e70baaac3e0716d26c8e7155.png)

**最小项和最大项的关系–**每个最小项都是其对应的最大项的补码。
例如，对于双变量布尔函数–

```

In general  or 

```

**构造布尔函数–**现在我们知道了什么是 minterms 和 maxterms，可以用它们来构造布尔表达式。

“一个布尔函数可以用代数方法从给定的真值表中表达出来，方法是为每个变量组合形成一个小项，在函数中产生一个 1，然后取所有这些项的或。”

例如，考虑两个函数![f_1](img/ea5909d7b0a42b32e115d9b4b16e571c.png "Rendered by QuickLaTeX.com")和![f_2](img/0530f61ef82a6b31df8a7d68684eb5a7.png "Rendered by QuickLaTeX.com")，真值表如下–
![ \begin{tabular}{||c||c||c||c||c||} \hline x&y&z&f_1&f_2\\ \hline \hline  0&0&0&0&0\\ \hline  0&0&1&1&0\\ \hline  0&1&0&0&0\\ \hline  0&1&1&0&1\\ \hline  1&0&0&1&0\\ \hline  1&0&1&0&1\\ \hline  1&1&0&0&1\\ \hline  1&1&1&1&1\\ \hline  \end{tabular} ](img/866aa6a8863bd7a0b91baf6abc9aa575.png "Rendered by QuickLaTeX.com")
函数![f_1](img/ea5909d7b0a42b32e115d9b4b16e571c.png "Rendered by QuickLaTeX.com")对于以下![x,\:y,\:z](img/2b98e5e42df0135b0820115530f4f9c3.png "Rendered by QuickLaTeX.com")–001，100，111
的组合为 1，对应的最小项为- ![x^\prime y^\prime z](img/4d29569f691855d4f3f7405116ea852e.png "Rendered by QuickLaTeX.com")、![x y^\prime z^\prime](img/6cdbfd5d082a029068f8e2cb9c056be2.png "Rendered by QuickLaTeX.com")、![xyz](img/42771a2e6a03a41f34c5cad7dcbfc60b.png "Rendered by QuickLaTeX.com")。
因此![f_1](img/ea5909d7b0a42b32e115d9b4b16e571c.png "Rendered by QuickLaTeX.com")的代数表达式是-
![f_1(x,y,z) = x^\prime y^\prime z + x y^\prime z^\prime + xyz](img/5a1da5cd9960ecb67cb6bddfdeae58ad.png "Rendered by QuickLaTeX.com")
![f_1(x,y,z) = m_1 + m_4 +m_7](img/b7ee52ff27d33ea309562359a4b19e97.png "Rendered by QuickLaTeX.com")
类似地，![f_2](img/0530f61ef82a6b31df8a7d68684eb5a7.png "Rendered by QuickLaTeX.com")的代数表达式是-
![f_2(x,y,z) = m_3 + m_5 + m_6 + m_7](img/1e85d413c6780babcef3fa04772c68f6.png "Rendered by QuickLaTeX.com")
如果我们在![f_1](img/ea5909d7b0a42b32e115d9b4b16e571c.png "Rendered by QuickLaTeX.com")和![f_2](img/0530f61ef82a6b31df8a7d68684eb5a7.png "Rendered by QuickLaTeX.com")上使用德摩根定律，所有 1 都变成 0，所有 0 都变成 1。因此我们得到-
![f_1(x,y,z)^\prime = m_0 + m_2 +m_3 + m_5 + m_6](img/69b13a9fb725ba2e62aef8543802613c.png "Rendered by QuickLaTeX.com")
![f_2(x,y,z)^\prime = m_0 + m_1 + m_2 + m_4](img/17b147281c9e034e9a5aa2be53d11de5.png "Rendered by QuickLaTeX.com")
关于再次使用德摩根定律-
![f_1(x,y,z) = (m_0 + m_2 +m_3 + m_5 + m_6)^\prime](img/099e7d3f8b18c36433242865d2657b14.png "Rendered by QuickLaTeX.com")
![f_1(x,y,z) = m_0^\prime . m_2^\prime . m_3^\prime . m_5^\prime . m_6^\prime](img/cb99d38216c7cc72a3a653b73e9d6553.png "Rendered by QuickLaTeX.com")
![f_1(x,y,z) = M_0 . M_2 . M_3 . M_5 . M_6](img/80871be2ef1642bc0e43efad08b50d38.png "Rendered by QuickLaTeX.com")
和
![f_2(x,y,z) = (m_0 + m_1 + m_2 + m_4)^\prime](img/887ec3d4b7150f88b2a6d903ef6bfd48.png "Rendered by QuickLaTeX.com")
![f_2(x,y,z) = m_0^\prime . m_1^\prime . m_2^\prime . m_4^\prime](img/8746c7d7eddeb4fb1f63684849083c0f.png "Rendered by QuickLaTeX.com")
![f_2(x,y,z) = M_0 . M_1 . M_2 . M_4](img/5b7287e1133437aeb1017d1f49eb5bea.png "Rendered by QuickLaTeX.com")
我们可以从上面得出结论，布尔函数可以表示为一个**的 minterms 之和**或者一个**max terms 的乘积**。

表示为最小项之和或最大项之积的布尔函数被称为**规范形式**。

*   **例 1–**用 SOP 和 POS 形式表达以下布尔表达式-
    ![F=x+y^\prime z](img/788f2b26500d27d1cba309d156ef452b.png "Rendered by QuickLaTeX.com")
*   **解–**表达式可以通过乘以![k+k^\prime = 1](img/8c7a2efe00812beaf2f807c7437516ba.png "Rendered by QuickLaTeX.com")将每个项中的缺失变量相加转化为 SOP 形式，其中![k](img/2fcea10a7642f4b02083e03a8c617aa9.png "Rendered by QuickLaTeX.com")为缺失变量。
    这是从–![1.x = x.1 = x](img/1eb8ce34bb13a5b3d3d98d59aa1354c0.png "Rendered by QuickLaTeX.com")
    ![ F=x(y+y^\prime)+y^\prime z\\ F=xy+xy^\prime+y^\prime z\\ F=xy(z+z^\prime)+xy^\prime(z+z^\prime)+(x+x^\prime)y^\prime z\\ F=xyz + xyz^\prime + xy^\prime z + xy^\prime z^\prime + xy^\prime z + x^\prime y^\prime z ](img/b3e8f339e58566deeca40647b5441d1f.png "Rendered by QuickLaTeX.com")
    按照升序重新排列最小项
    ![ F=x^\prime y^\prime z + xy^\prime z^\prime + xy^\prime z + xyz^\prime + xyz\\ F=m_1 + m_4 + m_5 + m_6 + m_7 ](img/c400544da4ea1397676a6d7952e8f992.png "Rendered by QuickLaTeX.com")
    如果我们想要 POS 表单，我们可以如上所述对 SOP 表单进行双重否定，从而得到-
    ![ F=M_0.M_2.M_3 ](img/2d7cc673b88810779e6db292765a8410.png "Rendered by QuickLaTeX.com")
    SOP 和 POS 表单有一个简短的表示符号-
    ![ F(x,y,z) = \sum(1,4,5,6,7)\\ F(x,y,z) = \prod(0,2,3)\\ ](img/67265d767b6ff972b36a52036b37fa5f.png "Rendered by QuickLaTeX.com")

**标准形式–**
规范形式是从函数真值表中得到的基本形式。这些形式通常不用于表示函数，因为它们编写起来很麻烦，最好用尽可能少的文字来表示函数。
有两种标准表格–

1.  **乘积之和(SOP)—**一种布尔表达式，包含带有一个或多个字面值的“与”项，或合在一起。
2.  **Product of Sums(POS)** A boolean expression involving OR terms with one or more literals each, AND’ed together, e.g.

    ```
    SOP- 
    POS- 

    ```

    **注–**以上表达式不等价，只是举例。

**GATE CS 角题**

练习下列问题将帮助你测试你的知识。所有的问题在前几年的 GATE 考试或 GATE 模拟考试中都被问过。强烈建议你练习一下。

1. [GATE CS 2010，问题 6](https://www.geeksforgeeks.org/gate-gate-cs-2010-question-6/)
2。 [GATE CS 2008，问题 7](https://www.geeksforgeeks.org/gate-gate-cs-2008-question-7/)
3。 [GATE CS 2014 第 1 集，第 17 题](https://www.geeksforgeeks.org/gate-gate-cs-2014-set-1-question-17/)

**参考文献-**

数字设计第五版，由莫里斯马诺和迈克尔西莱蒂

本文由**奇拉·曼瓦尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。