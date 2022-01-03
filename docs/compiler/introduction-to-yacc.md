# YACC 简介

> 原文:[https://www.geeksforgeeks.org/introduction-to-yacc/](https://www.geeksforgeeks.org/introduction-to-yacc/)

解析器生成器是一个程序，它接受语法规范作为输入，并产生识别该语言的过程作为输出。历史上，它们也被称为编译器。
YACC(又一个编译器-编译器)是一个 [LALR(1)](https://www.geeksforgeeks.org/parsing-set-3-slr-clr-and-lalr-parsers/) (前瞻，从左到右，最右边的派生生成器，带有 1 个前瞻标记)解析器生成器。YACC 最初是为被莱克斯补充而设计的。
**输入文件:**
YACC 输入文件分为三部分。

```
/* definitions */
 ....

%% 
/* rules */ 
....
%% 

/* auxiliary routines */
.... 
```

**输入文件:定义部分:**

*   定义部分包括语法定义中使用的标记信息:

```
%token NUMBER 
%token ID 
```

*   Yacc 自动为代币分配号码，但可以被
    覆盖

```
%token NUMBER 621 
```

*   Yacc 还将单个字符识别为标记。因此，分配的令牌号不应与 ASCII 码重叠。

*   定义部分可以包括解析器定义外部的 C 代码和变量声明，在第一列的 **%{** 和 **%}** 内。

*   也可以包括语法中起始符号的说明:

```
%start nonterminal 
```

**输入文件:规则部分:**

*   规则部分包含修改后的 BNF 格式的语法定义。

*   Actions 是{ }中的 C 代码，可以嵌入其中(翻译方案)。

**输入文件:辅助例程部分:**

*   辅助例程部分只有 C 代码。

*   它包括规则部分所需的每个函数的函数定义。

*   如果解析器将作为程序运行，它还可以包含 main()函数定义。

*   main()函数必须调用函数 yyparse()。

**输入文件:**

*   如果辅助例程部分没有定义 yylex()，那么应该包括:

```
#include "lex.yy.c"  
```

*   YACC 输入文件一般以:
    结束

```
 .y 
```

**输出文件:**

*   YACC 的输出是一个名为**y . tab . c**T2 的文件
*   如果包含 **main()** 定义，则必须编译为可执行。

*   否则，代码可以是函数 **int yyparse()**
    的外部函数定义
*   如果在命令行中使用**–d**选项调用，Yacc 会生成一个头文件 **y.tab.h** 及其所有特定定义(尤其重要的是要包含在例如 Lex 输入文件中的标记定义)。

*   如果使用**–v**选项调用，Yacc 会生成一个文件 **y.output** 作为输出，其中包含解析器使用的 LALR(1)解析表的文本描述。这对于跟踪解析器如何解决冲突非常有用。

**例:**
**Yacc 文件(。y)**

## C

```
%{
   #include <ctype.h>
   #include <stdio.h>
   #define YYSTYPE double /* double type for yacc stack */
%}

%%
 Lines :  Lines S '\n' { printf("OK \n"); }
       |  S '\n’
       |  error '\n' {yyerror("Error: reenter last line:");
                        yyerrok; };
 S     :  '(' S ')’
       |  '[' S ']’
       |   /* empty */    ;
%%

#include "lex.yy.c"

void yyerror(char * s)
/* yacc error handler */
{  
 fprintf (stderr, "%s\n", s);
}

int main(void)
 {
 return yyparse();
 } 
```

**Lex File(.l)**

## C

```
%{
%}

%%
[ \t]     { /* skip blanks and tabs */ }
\n|.      { return yytext[0]; }
%%
```

**用于编制 YACC 计划:**

1.  把 lex 程序写在一个文件中，把 yacc 写在一个文件中
2.  打开终端，导航到保存文件的目录。

3.  lex file . l〔t0〕型式
4.  yacc 文件类型. y

5.  cc 型 lex.yy.c 和. tab.h -ll

6.  打字。/a.out