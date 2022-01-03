# 遵循语法分析中的设置

> 原文:[https://www . geesforgeks . org/follow-set-in-syntax-analysis/](https://www.geeksforgeeks.org/follow-set-in-syntax-analysis/)

我们已经讨论了以下关于语法分析的主题。

[语法分析入门](https://www.geeksforgeeks.org/introduction-to-syntax-analysis-in-compiler-design/)
[为什么先有后有？](https://www.geeksforgeeks.org/why-first-and-follow-in-compiler-design/)
[语法分析第一集](https://www.geeksforgeeks.org/first-set-in-syntax-analysis/)

在这篇文章中，跟随集被讨论。

**跟在(X)** 后面，成为在某种句子形式中，可以立即出现在非 X 端右边的一组终端。
例:

```
S ->Aa | Ac
A ->b  

      S                  S  
     /  \              /   \
    A    a            A     C  
    |                 |
    b                 b   

Here, FOLLOW (A) = {a, c}

```

**<u>计算跟随集的规则:</u>**

```
1) FOLLOW(S) = { $ }   // where S is the starting Non-Terminal

2) If A -> pBq is a production, where p, B and q are any grammar symbols,
   then everything in FIRST(q)  except Є is in FOLLOW(B).

3) If A->pB is a production, then everything in FOLLOW(A) is in FOLLOW(B).

4) If A->pBq is a production and FIRST(q) contains Є, 
   then FOLLOW(B) contains { FIRST(q) – Є } U FOLLOW(A) 

```

**例 1:**

```
Production Rules:
E -> TE’
E’ -> +T E’|Є
T -> F T’
T’ -> *F T’ | Є
F -> (E) | id

FIRST set
FIRST(E) = FIRST(T) = { ( , id }
FIRST(E’) = { +, Є }
FIRST(T) = FIRST(F) = { ( , id }
FIRST(T’) = { *, Є }
FIRST(F) = { ( , id }

FOLLOW Set
FOLLOW(E)  = { $ , ) }  // Note  ')' is there because of 5th rule
FOLLOW(E’) = FOLLOW(E) = {  $, ) }  // See 1st production rule
FOLLOW(T)  = { FIRST(E’) – Є } U FOLLOW(E’) U FOLLOW(E) = { + , $ , ) }
FOLLOW(T’) = FOLLOW(T) =      { + , $ , ) }
FOLLOW(F)  = { FIRST(T’) –  Є } U FOLLOW(T’) U FOLLOW(T) = { *, +, $, ) }

```

**例 2:**

```
Production Rules:
S -> aBDh
B -> cC
C -> bC | 
D -> EF
E -> g | Є
F -> f | Є

FIRST set
FIRST(S) = { a }
FIRST(B) = { c }
FIRST(C) = { b , Є }
FIRST(D) = FIRST(E) U FIRST(F) = { g, f, Є }
FIRST(E) = { g , Є }
FIRST(F) = { f , Є }

FOLLOW Set
FOLLOW(S) = { $ } 
FOLLOW(B) = { FIRST(D) – Є } U FIRST(h) = { g , f , h }
FOLLOW(C) = FOLLOW(B) = { g , f , h }
FOLLOW(D) = FIRST(h) = { h }
FOLLOW(E) = { FIRST(F) – Є } U FOLLOW(D) = { f , h }
FOLLOW(F) = FOLLOW(D) = { h } 

```

**例 3:**

```
Production Rules:
S -> ACB|Cbb|Ba
A -> da|BC
B-> g|Є
C-> h| Є

FIRST set
FIRST(S) = FIRST(A) U FIRST(B) U FIRST(C) = { d, g, h, Є, b, a}
FIRST(A) = { d } U {FIRST(B)-Є} U FIRST(C) = { d, g, h, Є }
FIRST(B) = { g, Є }
FIRST(C) = { h, Є }

FOLLOW Set
FOLLOW(S) = { $ }
FOLLOW(A)  = { h, g, $ }
FOLLOW(B) = { a, $, h, g }
FOLLOW(C) = { b, g, $, h }

```

**注:**

1.  є作为追随者并不意味着什么(є是一根空弦)。
2.  $被称为 end-marker，它表示输入字符串的结尾，因此在解析时用来指示输入字符串已经被完全处理。
3.  上面使用的语法是上下文无关语法。编程语言的语法可以使用 CFG 来指定。
4.  CFG 的形式是 A -> B，其中 A 是单个非终结符，B 可以是一组语法符号(即终结符和非终结符)