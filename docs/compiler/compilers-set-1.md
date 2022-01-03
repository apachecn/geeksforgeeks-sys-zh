# 编译原理|第 1 集

> 原文:[https://www.geeksforgeeks.org/compilers-set-1/](https://www.geeksforgeeks.org/compilers-set-1/)

GATE CS 考试中提出了以下问题。

**1。自顶向下解析器在解析输入字符串时使用以下哪种派生？假设按照从左到右的顺序扫描输入(GATE CS 2000)。**
(a)最左边的派生词
(b)最左边的派生词逆向追溯
(c)最右边的派生词
(d)最右边的派生词逆向追溯

**回答**(一)

**自上而下解析(LL)**
在自上而下解析中，我们只需从开始符号开始，将不同作品的右侧与第一段输入进行比较，看看应该使用哪一个作品。

一个自上而下的解析器被称为 LL 解析器，因为它从右到上解析来自 **L** eft 的输入，并构造句子的 **L** eftmost 派生。

**算法(自上而下解析)**

```
  a) In the current string, choose leftmost nonterminal.
  b) Choose a production for the chosen nonterminal. 
  c) In the string, replace the nonterminal by the right-hand-side 
     of the rule.
  d) Repeat until no more nonterminals. 

```

LL 语法通常按数字分类，如 LL(1)、LL(0)等。括号中的数字告诉我们在语法的任何一点上选择正确的产品时，我们可能不得不看的最大终端数量。

最常见(也是最有用)的 LL 语法是 LL(1)，在这里，您可以在任何给定时间只查看输入上的第一个终端来选择正确的产品。对于 LL(2)，你必须看两个符号，以此类推。对于 k 的任何固定值，存在根本不是 LL(k)语法的语法，可悲的是，它们非常普遍。

让我们看一个自上而下语法分析的例子。让输入字符串为 ax。

```
    S -> Ax
    A -> a
    A -> b

```

LL(1)解析器以 S 开头，并询问“我应该尝试哪种产品？”自然地，它预测 s 的唯一选择。从那里，它试图通过调用方法 A 来匹配 A(在递归下降解析器中)。前瞻 a 预测产量

```
   A -> a

```

解析器匹配 a，返回 S，匹配 x。完成。派生树是:

```
     S
    / \
   A   x
   |
   a

```

**参考文献:**
[【http://www.garshol.priv.no/download/text/bnf.html】](http://www.garshol.priv.no/download/text/bnf.html)
[http://en.wikipedia.org/wiki/Top-down_parsing](http://en.wikipedia.org/wiki/Top-down_parsing)
[http://en.wikipedia.org/wiki/LL_parser](http://en.wikipedia.org/wiki/LL_parser)

 **2。将加载地址分配给程序的各个部分并调整程序中的代码和数据以反映分配的地址的过程称为(GATE CS 2001)**
a)汇编
b)解析
c)重定位
d)符号解析

**回答:(c)**
重定位是在运行程序之前，用内存中实际可用的地址替换符号引用或库名的过程。它通常由链接器在编译期间(在编译时)完成，尽管它可以由重新定位的加载器在运行时完成。编译器或汇编器通常以零作为最低起始地址来生成可执行文件。在执行目标代码之前，应该调整这些地址，以便它们表示正确的运行时地址。

重新定位通常分两步完成:
1。每个目标代码都有不同的部分，如代码、数据、。bss 等。为了将所有对象组合成一个可执行文件，链接器将相似类型的所有部分合并成该类型的单个部分。然后，链接器为每个部分和每个符号分配运行时地址。此时，代码(函数)和数据(全局变量)将具有唯一的运行时地址。
2。每个部分都引用一个或多个符号，这些符号应该被修改以指向正确的运行时地址。

**参考文献:**
[http://en . Wikipedia . org/wiki/reduce _(计算机 _ 科学)](http://en.wikipedia.org/wiki/Relocation_(computer_science))

**3。以下哪个陈述是错误的？(GATE CS 2001)**
a)一个明确的语法有相同的最左边和最右边的派生
b)一个 LL(1)解析器是一个自上而下的解析器
c) LALR 比 SLR 更强大
d)一个模棱两可的语法对于任何 k 永远不可能是 LR(k)

**回答:(a)**
如果一个语法对一个句子形式有不止一个最左边(或最右边)的派生，那么这个语法就是模棱两可的。一个句子形式最左边和最右边的派生词可能不同，即使是在明确的语法中
 **4。以下哪些语法规则违反了运算符语法的要求？p、Q、R 为非端子，R、s、t 为端子(GATE CS 2004)。
(I)P->QR
(ii)P->QsR
(iii)P->ε
(iV)P->QtRr**

a) (i)仅
b) (i)和(iii)仅
c) (ii)和(iii)仅
d) (iii)和(iv)

**答案:(b)**
**解释:**
一个*操作符优先解析器*是一个自下而上的解析器，解释一个操作符优先语法。例如，大多数计算器使用运算符优先解析器将人类可读的带操作顺序的中缀符号格式转换为内部优化的计算机可读格式，如反向波兰符号(RPN)。

一种*运算符优先语法*是一种上下文无关的语法，可以用运算符优先解析器进行解析。它具有这样的性质，即任何产品都没有空的(ε)右手边或在它的右手边有两个相邻的非终端。这些属性允许通过优先关系来描述语法的终端，并且利用该关系的解析器比更通用的解析器(如 LALR 解析器)简单得多。
 **参考文献:**
[http://en.wikipedia.org/wiki/Operator-precedence_grammar](http://en.wikipedia.org/wiki/Operator-precedence_grammar)
[http://en.wikipedia.org/wiki/Operator-precedence_parser](http://en.wikipedia.org/wiki/Operator-precedence_parser)

 **5。考虑以下翻译规则的语法，E 作为开始符号。
E->E1 # T { E . value = E1 . value * T . value }
| T { E . value = T . value }
T->T1&F { T . value = T1 . value+F . value }
| F { T . value = F . value }
F->num { F . value = num . value }**

**计算表达式解析树根的 E . value:2 # 3&5(GATE CS 2004)**

a)200
b)180
c)160
d)40

**答案:(c)**
**解释:**
我们可以通过构建表达式 2 # 3 & 5 # 6 & 4 的解析树来计算值。

或者，我们可以通过考虑以下优先级和结合性规则来计算。
通过确保具有较高优先级运算符的生成规则永远不会生成具有较低优先级运算符的表达式，来强制语法中的优先级。
在给定的语法中，“&”的优先级高于“#”。

语法中运算符*的左关联性是通过确保对于像语法中的 S -> S1 * S2 这样的生成规则，S2 永远不应该生成带有*的表达式来实现的。另一方面，为了确保正确的关联性，S1 永远不应该产生带有*的表达式。
在给定的语法中，' # '和&都是左关联的。

所以表达式 2 # 3 & 5 # 6 &4 将变成
((2 # (3 & 5)) # (6 & 4))
让我们应用翻译规则，我们得到
((2 * (3 + 5)) * (6 + 4)) = 160。