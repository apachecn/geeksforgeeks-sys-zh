# 编译原理|第二集

> 原文:[https://www.geeksforgeeks.org/compilers-set-2/](https://www.geeksforgeeks.org/compilers-set-2/)

GATE CS 考试中提出了以下问题。

**1。给定以下表达式语法:
E->E * F | F+E | F
F->F-F | id
下列哪一项是正确的？(GATE CS 2000)** (a) *的优先级高于+
(b)–的优先级高于*
(c) +和-的优先级相同
(d) +的优先级高于*

回答(b)

语法中的优先级是通过确保具有较高优先级运算符的生成规则永远不会生成具有较低优先级运算符的表达式来实现的。
在给定的语法中，“-”的优先级高于“*”

 **2。考虑一个程序 P，它由包含在两个不同文件中的两个源模块 M1 和 M2 组成。如果 M1 包含对在 M2 定义的函数的引用，该引用将在(GATE CS 2004)**
a)编辑时间
b)编译时间
c)链接时间
d)加载时间解析

答案(c)
编译器将源代码转换为目标语言。目标语言通常是二进制形式，称为目标代码。通常，一个对象文件可以包含三种符号:

*已定义的符号，允许它被其他模块调用，
*未定义的符号，调用定义这些符号的其他模块，
*本地符号，在对象文件内部使用，以便于重新定位。

当一个程序包含多个目标文件时，链接器将这些文件组合成一个统一的可执行程序，并在执行过程中解析这些符号。
[http://en.wikipedia.org/wiki/Compiler](http://en.wikipedia.org/wiki/Compiler)T3[http://en.wikipedia.org/wiki/Linker_%28computing%29](http://en.wikipedia.org/wiki/Linker_%28computing%29)

 **3。以下哪一项足以将任意的 CFG 转换为 LL(1)语法？(GATE CS 2003)**
(a)仅去除左递归
(b)仅分解语法
(c)去除左递归并分解语法
(d)以上都不是

答案(d)
移除左递归并分解语法不足以将任意 CFG 转换为 LL(1)语法。
[http://pages.cpsc.ucalgary.ca/~robin/class/411/LL1.3.html](http://pages.cpsc.ucalgary.ca/~robin/class/411/LL1.3.html)

**4。假设语法 G 的 SLR 解析器有 n1 个状态，G 的 LALR 解析器有 n2 个状态。n1 和 n2 的关系是(GATE CS 2003)**
(a) n1 必然小于 n2
(b) n1 必然等于 n2
(c) n1 必然大于 n2
(d)以上都不是

回答(b)

[http://parasol . tamu . edu/people/rwerger/Courses/434/LEC 10 . pdf](http://parasol.tamu.edu/people/rwerger/Courses/434/lec10.pdf)
[http://dragon book . Stanford . edu/讲座笔记/Stanford-CS143/11-LALR-parsing . pdf](http://dragonbook.stanford.edu/lecture-notes/Stanford-CS143/11-LALR-Parsing.pdf)

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。