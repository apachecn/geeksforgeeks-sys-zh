# 删除语法中的直接和间接左递归

> 原文:[https://www . geesforgeks . org/remove-直接和间接-左递归语法/](https://www.geeksforgeeks.org/removing-direct-and-indirect-left-recursion-in-a-grammar/)

先决条件–[上下文无关语法的分类](https://www.geeksforgeeks.org/classification-of-context-free-grammars/)、[歧义和解析器](https://www.geeksforgeeks.org/parsing-set-1-introduction-ambiguity-and-parsers/)、
T5】左递归:
形式的语法，

```
S --> S / a / b 
```

这叫做左递归，其中 S 是任意非终端，a 和 b 是任意一组终端。

**左递归的问题:**
如果在任何语法中都存在左递归，那么在编译的语法分析部分的解析过程中，语法有可能会产生无限循环。这是因为在每一次产生语法 S 的时候都会产生另一个 S 而不检查任何条件。

**去除左递归的算法举例:**
假设我们有一个包含左递归的语法:

```
S-->S a / S b / c / d 
```

1.  检查给定的语法是否包含左递归，如果存在，则分离产品并开始处理它。
    在我们的示例中，

    ```
    S-->S a/ S b /c / d   
    ```

2.  引入一个新的非终结符，写在每个终结符的最后。我们生产一个新的非终端‘S’，并将新的产品写成，

    ```
    S-->cS' / dS' 
    ```

3.  Write newly produced nonterminal in LHS and in RHS it can either produce or it can produce new production in which the terminals or non terminals which followed the previous LHS will be replaced by new nonterminal at last.

    ```
    S'-->? / aS' / bS' 
    ```

    因此，转换后，新的等效产量为

    ```
    S-->cS' / dS'
    S'-->? / aS' / bS'   
    ```

**间接左递归:**
如果从语法的任何符号开始，有可能导出一个以该符号为头的字符串，则称该语法具有间接左递归。

例如，

```
A --> Br 
B --> Cd
C --> At 
```

其中 A、B、C 为非端子，r、d、t 为端子。
在这里，从 A 开始，我们可以通过将 C 代入 B and B，再代入 A，再次推导出 A

**借助示例消除间接递归的算法:**

```
A1 --> A2  A3
A2 --> A3  A1 / b
A3 --> A1  A1 / a 
```

其中 A1、A2、A3 为非端子，a、b 为端子。

1.  确定可能导致间接左递归的产品。在我们的情况下，

    ```
    A3--&gt A1 A1 / a 
    ```

2.  在任何其他生产替代品 A1–> A2 A3 生产 A3 时，在终端出现的地方替代其生产。A3–> A2 A3 A1。
    现在在本产品中，替换 A2–>A3 A1/b，然后替换为，

    ```
    A3 --> A3  A1 A3 A1 / b A3 A1 
    ```

3.  Now the new production is converted in form of direct left recursion, solve this by direct left recursion method.
    Eliminating direct left recursion in the above,

    ```
    A3 --> a | b A3 A1 | aA' | b A3 A1A' 
    A' --> A1 A3 A1 | A1 A3 A1A' 
    ```

    生成的语法是:

    ```
    A1 -->  A2 A3
    A2 --> A3 A1 | b
    A3 --> a | b A3 A1 | aA' | b A3 A1A' 
    A' --> A1 A3 A1 | A1 A3 A1A' 
    ```