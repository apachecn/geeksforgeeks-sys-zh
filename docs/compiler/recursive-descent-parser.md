# 递归下降解析器

> 原文:[https://www.geeksforgeeks.org/recursive-descent-parser/](https://www.geeksforgeeks.org/recursive-descent-parser/)

**先决条件–**[构建 LL(1)解析表](https://www.geeksforgeeks.org/compiler-design-construction-of-ll1-parsing-table/)、[自上而下解析器的分类](https://www.geeksforgeeks.org/compiler-design-classification-top-parsers/)
解析是判断起始符号能否派生程序的过程。如果解析成功，则程序是有效的程序，否则程序是无效的。
解析器一般有两种类型:

1.  **自顶向下解析器:**
    *   在这个解析技术中，我们将开始符号扩展到整个程序。
    *   递归下降和 LL 解析器是自顶向下的解析器。
2.  **自下而上解析器:**
    *   在这种解析技术中，我们将整个程序简化为起始符号。
    *   运算符优先解析器、LR(0)解析器、SLR 解析器、LALR 解析器和 CLR 解析器是自底向上的解析器。

**递归下降解析器:**
它是一种自顶向下的解析器。自顶向下的解析器从开始的非终结符开始，从上到下构建解析树。一个*预测解析器*是递归下降解析器的一个特例，不需要回溯。
通过仔细编写一个语法意味着消除左递归和左因式分解，得到的语法将是一个可以被递归下降解析器解析的语法。
**例:**

<figure class="table">

| 在移除左递归之前 | 移除左递归后 |
| --- | --- |
| E–> E+T &#124; T
T–>T * F &#124; F
F–>(E)&#124; id | E–> T E '
E–>+T E ' &#124; E
T–>F T '
T–>* F T ' &#124; E
F–>(E)&#124; id |

* *这里 e 是ε
对于递归下降解析器，我们将为每个变量编写一个程序。

```
Example:
Grammar: E --> i E'
E' --> + i E' | e
```

## C

```
int main()
{
    // E is a start symbol.
    E();

    // if lookahead = $, it represents the end of the string
    // Here l is lookahead.
    if (l == '{content}apos;)
        printf("Parsing Successful");
}

// Definition of E, as per the given production
E()
{
    if (l == 'i') {
        match('i');
        E'();
    }
}

// Definition of E' as per the given production
E'()  
{
    if (l == '+') {
        match('+');
        match('i');
        E'();
    }//The second condition of E'
    else if ( l == 'e' )
    {
      match('e');
    }
        return ();
}

// Match function
match(char t)
{
    if (l == t) {
        l = getchar();
    }
    else
        printf("Error");
}
```

</figure>