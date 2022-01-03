# 编译器设计中的 BNF 符号

> 原文:[https://www . geesforgeks . org/BNF-编译器中的符号-设计/](https://www.geeksforgeeks.org/bnf-notation-in-compiler-design/)

BNF 代表**巴克斯瑙尔形式**符号。它是描述编程语言语法的一种形式方法，被理解为约翰·巴库斯和彼得·诺尔于 1960 年提出的巴克斯·瑙尔形式。BNF 和 [CFG(上下文无关语法)](https://www.geeksforgeeks.org/classification-of-context-free-grammars/)几乎相同。BNF 可能是主要语言的元语言(一种不能描述另一种语言的语言)。

对于人类来说，一种用于编码语法的适当符号，称为巴克斯瑙尔形式。不同的语言有不同的描述和规则，但是 BNF 的一般结构如下

```
name ::= expansion
```

符号::=表示“可能扩展为”和“可能替换为”在某些文本中，名誉还被称为非终结符号。

*   Every name in Backus-Naur form is surrounded by angle brackets, < >, whether it appears on the left- or right-hand side of the rule. 
*   An expansion is an expression containing terminal symbols and non-terminal symbols, joined together by sequencing and selection. 
*   A terminal symbol may be a literal like (“+” or “function”) or a category of literals (like integer). 
*   Simply juxtaposing expressions indicates sequencing. 
*   A vertical bar | indicates choice. 

    **示例:**

```
<expr> ::= <term> "+" <expr>
        |  <term>

<term> ::= <factor> "*" <term>
        |  <factor>

<factor> ::= "(" <expr> ")"
          |  <const>

<const> ::= integer
```

**制定 BNF 的规则:**
自然，我们将在 BNF–
中定义规则的语法

```
rule → name ::= expansion
name → < identifier >
expansion → expansion expansion
expansion → expansion | expansion
expansion → name
expansion → terminal
```

*   We might define identifiers as using the regular expression [-A-Za-z_0-9]+. 
*   A terminal could be a quoted literal (like “+”, “switch” or ” “<<=”) or the name of a category of literals (like integer). 
*   The name of a category of literals is typically defined by other means, like a daily expression or maybe prose. 

    在语法中寻找类似正则表达式的操作是很常见的。例如，Python 词法规范使用了它们。在这些语法中:

```
postfix * means "repeated 0 or more times"
postfix + means "repeated 1 or more times"
postfix ? means "0 or 1 times"
```

Python 中浮点文字的定义可能是混合几种符号的一个范例——

```
floatnumber   ::=  pointfloat | exponentfloat
pointfloat    ::=  [intpart] fraction | intpart "."
exponentfloat ::=  (intpart | pointfloat) exponent
intpart       ::=  digit+
fraction      ::=  "." digit+
exponent      ::=  ("e" | "E") ["+" | "-"] digit+
```

它没有在名字周围使用尖括号(像许多 EBNF 符号和 ABNF)，但是使用了::=(像 BNF)。它将常规操作(如+表示非空重复)与 EBNF 约定(如[ ]表示选项)混合在一起。整个 Python 语言的语法使用了一种相当不同的(但仍然是规则的)符号。