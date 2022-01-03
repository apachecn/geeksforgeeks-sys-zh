# 左右线性正则文法

> 原文:[https://www . geesforgeks . org/right-and-left-linear-regular-grammars/](https://www.geeksforgeeks.org/right-and-left-linear-regular-grammars/)

[常规语法](https://www.geeksforgeeks.org/chomsky-hierarchy-in-theory-of-computation/)是描述常规  语言的一种语法。  规则语法是一个数学对象，g，它由四个部分组成，G = (N，E *、* P，s)，其中

*   **n:** A non-empty and limited set of non-terminal symbols,
*   **E:** A limited set of terminal symbols, or alphabet, symbols,
*   **P:** A set of grammar rules, each of which has a form [here ∑= empty string, a, B ∈ N, A∈∈.

*   **s** ∈ n is the starting symbol.

该语法可以有两种形式:

1.  Right regular grammar
2.  Left regular grammar

#### 右线性正则语法

在这种常规语法中，所有右边的非终结符都存在于最右边的地方，即；右端。

**示例:**

```
A ⇢ a, A ⇢ aB, A ⇢ ∈
where,
A and B are non-terminals,
a is terminal, and
∈ is empty string
```

```
S ⇢ 00B | 11S
B ⇢ 0B | 1B | 0 | 1
where,
S and B are non-terminals, and
0 and 1 are terminals
```

#### 左线性正则语法

在这种常规语法中，所有右边的非终结符都存在于最左边的地方，即；左端。

#### 示例:

```
A ⇢ a, A ⇢ Ba, A ⇢ ∈
where,
A and B are non-terminals,
a is terminal, and
∈ is empty string
```

```
S ⇢ B00 | S11
B ⇢ B0 | B1 | 0 | 1
where
S and B are non-terminals, and
0 and 1 are terminals
```

#### 左线性到右线性正则语法

在这种类型的转换中，我们必须将所有左手非终端向右移动，如下例所示:

```
               Left linear                       Right linear 

                 A -> Ba                           A -> abaB     
                 B -> ab                           B -> epsilon   
                                        OR
                                            A -> abB
                                            B -> a

```

所以，这样做可以给出多个答案。上面解释的例子有多个答案，而不是给定的一次。

#### 右线性到左线性正则语法

在这种类型的转换中，我们必须将所有右手非终端向左移动，如下例所示:

```
               Right linear                      Left linear

                 A -> aB                             A -> Baba  
                 B -> ab                             B -> epsilon  
                                                 OR
                                                     A -> Bab
                                                     B -> a
```

所以，这样做可以给出多个答案。上面解释的例子有多个答案，而不是给定的一次。