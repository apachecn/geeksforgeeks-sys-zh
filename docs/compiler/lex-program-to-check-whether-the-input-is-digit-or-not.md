# Lex 程序检查输入是否为数字

> 原文:[https://www . geesforgeks . org/lex-program-to-check-input 是数字还是非数字/](https://www.geeksforgeeks.org/lex-program-to-check-whether-the-input-is-digit-or-not/)

Lex 是一个生成词法分析器的计算机程序。Lex 读取指定词法分析器的输入流，并输出用 C 编程语言实现 lexer 的源代码。

**先决条件** : [Flex(快速词法分析器生成器)](https://www.geeksforgeeks.org/flex-fast-lexical-analyzer-generator/)。

给定一个输入，任务是检查输入是否是数字。

**示例:**

```
Input:  28
Output: digit

Input: a
Output: not a digit. 

Input: 21ab
Output: not a digit. 

```

下面是实现:

```
/* Lex program to check whether input is digit or not. */
%{
#include<stdio.h>
#include<stdlib.h>
%}
/* Rule Section */
%%
^[0-9]*  printf("digit");
^[^0-9]|[0-9]*[a-zA-Z]  printf("not a digit");
. ;
%%
int main()
{
        // The function that starts the analysis
    yylex();
        return 0;
}
```

**输出:**
![](img/7fe01f724eb2e5d0da1c7e8be3ecfe0f.png)