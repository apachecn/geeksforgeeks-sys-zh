# 数字逻辑中的功能完备性

> 原文:[https://www . geesforgeks . org/functional-completion-in-digital-logic/](https://www.geeksforgeeks.org/functional-completeness-in-digital-logic/)

当且仅当**的每一个**切换功能都可以通过其中的操作来表达时，一组**操作**被称为功能完备或通用。一组布尔函数在功能上是完整的，如果所有其他布尔函数都可以从这个集合中构造，并且提供了一组输入变量，例如

*   集合 A = {+，*，'(OR，AND，complete 在功能上是完备的。
*   集合 B = {+，' }在功能上是完整的
*   集合 C = {*，' }在功能上是完整的

**波斯特的函数完备性定理–**函数的重要闭类:

1.  t<sub>0</sub>–所有保 0 函数的类，如 f(0，0，…，0) = 0。
2.  t<sub>1</sub>–所有保 1 函数的类，如 f(1，1，…，1) = 1。
3.  s–一类自对偶函数，如 f(x <sub>1</sub> ，…，x <sub>n</sub> ) = f( x <sub>1</sub> ，…，x <sub>n</sub> 。
4.  m–单调函数类，例如:{x <sub>1</sub> ，…，x <sub>n</sub> } ≤ {x <sub>1</sub> ，…，x <sub>n</sub> }，if x<sub>I</sub>≤y<sub>I</sub>
    if { x<sub>1</sub>，…，x <sub>n</sub> } ≤ {x <sub>1</sub> ，…，x <sub>n</sub>
5.  l–线性函数类，可表示为:f(x <sub>1</sub> ，…，x<sub>n</sub>)= a<sub>0</sub>+a<sub>1</sub>x<sub>1</sub>+…+a<sub>n</sub>x<sub>n</sub>；a <sub>i</sub> {0，1}。

**定理–**对于五个定义的类 T <sub>0</sub> 、T <sub>1</sub> 、S、M、L 中的每一个，当且仅当 F 中有一个成员不属于该类时，布尔函数系统在功能上是完备的。

这些是最小的功能完备的操作集–

**一个元素–**
{﹍}、{﹍}。

**两个元素–**
![{\displaystyle \{\vee ,\neg \}}, {\displaystyle \{\wedge ,\neg \}}, ](img/a8086f430e6c3badc0e602b2eb60397d.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\to ,\neg \}}, {\displaystyle \{\gets ,\neg \}},](img/53340b4a3f00caef098579ead0952b18.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\to ,\bot \}}, {\displaystyle \{\gets ,\bot \}},](img/bbe879e16d4d8b19af7989df6cfe706b.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\to ,\nleftrightarrow \}}, {\displaystyle \{\gets ,\nleftrightarrow \}},](img/1fba8846962efef8ccf0cfd34dd2546b.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\to ,\nrightarrow \}}, {\displaystyle \{\to ,\nleftarrow \}}, ](img/a5210a11eba553e40403431cedb59304.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\gets ,\nrightarrow \}}, {\displaystyle \{\gets ,\nleftarrow \}}, ](img/7b5b7f16cfa333bc95454dc4a0183af2.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\nrightarrow ,\neg \}}, {\displaystyle \{\nleftarrow ,\neg \}}, ](img/208ebc3e90625cfab3dcec0f8b8347f8.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\nrightarrow ,\top \}}, {\displaystyle \{\nleftarrow ,\top \}}, ](img/d4dca7af23f68d19121d8ac0b78efeb6.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\nrightarrow ,\leftrightarrow \}}, {\displaystyle \{\nleftarrow ,\leftrightarrow \}}.](img/9b041456105dc3bafbb22c68dcfa2029.png "Rendered by QuickLaTeX.com")

**三要素–**
![{\displaystyle \{\lor ,\leftrightarrow ,\bot \}}, ](img/bcaa0e3617eb49f178d89775a1e04000.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\lor ,\leftrightarrow ,\nleftrightarrow \}}, ](img/e12f5ee524da8aceba7f564e743a3952.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\lor ,\nleftrightarrow ,\top \}}, ](img/7e973873bbae764f6949940296204545.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\land ,\leftrightarrow ,\bot \}}, ](img/1a81a19f7372bf4967bb0354914104d1.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\land ,\leftrightarrow ,\nleftrightarrow \}}, ](img/8dd48739bda39d1acd9de233b24f00c6.png "Rendered by QuickLaTeX.com")![{\displaystyle \{\land ,\nleftrightarrow ,\top \}}.](img/e28f8f0e406aca6470ff314cfa3e755e.png "Rendered by QuickLaTeX.com")

**功能完整性示例–**

*   **检查函数 F(A，B，C) = A'+BC '是否功能完备？**
*   **解释–**让我们从把所有变量都设为‘A’开始，这样它就变成了
    F(A，A，A)= ' A '+A . A ' = A '—(I)
    F(B，B，B)= ' B '+B . B ' = B '—(ii)
    现在用 F(A，A，A)代替变量‘A’，用 F(B，B，B)代替变量‘C’
    F(A，A，A)，B，F
*   **检查函数 F(A，B) = A'+B 是否功能完备？**
*   **解释–**让我们从把所有变量都设为‘A’开始，这样它就变成了
    F(A，A)= ' A '+A = 1—-(I)
    F(B，B)= ' B '+B = 1—(ii)
    F(A，0) = A'+0 = A'—(iv)
    现在用 F(A，0)代替变量‘A’
    F(F(A，0)，B)=(A ')’+B = A+B—(T0)
*   **检查函数 F(A，B) = A'B 是否功能完备？**
*   **Explanation –** Let us start by putting all variables as ‘A’ so it becomes
    F(A,A) = A’.A’ = 0—-(i)
    F(A,0) = A’.0 = 0—(ii)
    F(A,1) = A’.1 = A’—(iv)
    Now substitute F(A,1) in place of variable ‘A’
    F(F(A,1),B) = (A’)’*B = A*B—(iii)
    from (iv) complement is derived and from (iii) operator ‘*’ is derived so this function is functionally complete as from above if function contains {*,’} is **partially functionally complete** .

    **注意–**如果通过替换‘0’或‘1’功能变得完整，则称其为部分功能完整。

*   **检查函数 F(A，B) = A'B+AB' (EX-OR)是否功能完备？**
*   **解释–**让我们从把所有变量都作为‘A’开始，这样它就变成了
    F(A，1)= A . . 1+A . 0 = A’——(I)
    F(A’，B)= AB+A‘B’–(ii)
    F(A’，B’= AB’+A‘B–(iii)
    F(A，B’= A‘B’+AB—(iv)
    所以没有办法得到{+，*，’}根据所以 **EX-OR 不是功能完整的**。
*   **考虑运算
    f(X，Y，Z) = X'YZ + XY' + Y'Z '和 g(X '，Y，Z)= X ' YZ+X ' YZ '+XY
    以下哪一项是正确的？**
    (A)两个{f}和{g}都是功能完备的
    (B)只有{f}是功能完备的
    (C)只有{g}是功能完备的
    (D)无论是{f}还是{g}都不是功能完备的
*   **说明–**见 [GATE CS 2015(第 1 集)|问题 65](https://www.geeksforgeeks.org/gate-gate-cs-2015-set-1-question-49/)

**参考文献–**
[波斯特的功能完备性定理](https://cs.hse.ru/data/2015/05/28/1096847873/Lecture%2013.1.pdf)
[功能完备性–维基百科](https://en.wikipedia.org/wiki/Functional_completeness)

本文由**瓦伊沙里·巴蒂亚**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

发现有不正确的地方请写评论

>