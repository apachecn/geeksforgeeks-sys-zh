# 语法分析中的第一组

> 原文:[https://www.geeksforgeeks.org/first-set-in-syntax-analysis/](https://www.geeksforgeeks.org/first-set-in-syntax-analysis/)

语法符号 X 的第一个(X)是从 X 开始的一组终端

**规则先计算集:**

1.  If x is a terminal, then first (x) = {'x'}
2.  If x-> is a production rule, then add (x) first.
3.  If X->Y1 Y2 Y3……。 Yn is a production,
    1.  第一个(X)=第一个(Y1)
    2.  如果第一个(y1)包含є那么第一(x)= { first(y1)–є} u {第一(y2)}
    3.  If FIRST (Yi) contains 1 to n for all I, then it will be added to first(x).

**例 1:**

```
Production Rules of Grammar
E  -> TE’
E’ -> +T E’|Є
T  -> F T’
T’ -> *F T’ | Є
F  -> (E) | id

FIRST sets
FIRST(E) = FIRST(T) = { ( , id }
FIRST(E’) = { +, Є }
FIRST(T) = FIRST(F) = { ( , id }
FIRST(T’) = { *, Є }
FIRST(F) = { ( , id }
```

**例 2:**

```
Production Rules of Grammar
S -> ACB | Cbb | Ba
A -> da | BC
B -> g | Є
C -> h | Є

FIRST sets
FIRST(S) = FIRST(ACB) U FIRST(Cbb) U FIRST(Ba)
         = { d, g, h, b, a, Є}
FIRST(A) = { d } U FIRST(BC) 
         = { d, g, h, Є }
FIRST(B) = { g , Є }
FIRST(C) = { h , Є }
```

**注意:**

1.  The syntax used above is context-free syntax (CFG). The syntax of most programming languages can be specified by CFG.
2.  The form of CFG is A-> B, where A is a single non-terminator, and B can be a group of syntax symbols (i.e. terminators and non-terminators)

在下一篇文章“编译器设计中的跟随集”中，我们将看到如何计算跟随集。

本文由 [**瓦伊巴夫巴派**](https://disqus.com/by/vaibhav2992/) 编撰。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。