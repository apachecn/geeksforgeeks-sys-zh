# 实现计算器并识别有效算术表达式的 YACC 程序

> 原文:[https://www . geesforgeks . org/yacc-程序实现计算器并识别有效算术表达式/](https://www.geeksforgeeks.org/yacc-program-to-implement-a-calculator-and-recognize-a-valid-arithmetic-expression/)

**问题:**实现计算器并识别有效算术表达式的 YACC 程序。

**解释:**
Yacc(为“又一个编译器编译器。”)是 Unix 操作系统的标准解析器生成器。yacc 是一个开源程序，用 C 编程语言为解析器生成代码。首字母缩略词通常以小写形式呈现，但偶尔会被视为 YACC 或 Yacc。

**示例:**

```
Input: 4+5 
Output: Result=9
Entered arithmetic expression is Valid

Input: 10-5
Output: Result=5
Entered arithmetic expression is Valid

Input: 10+5-
Output: 
Entered arithmetic expression is Invalid

Input: 10/5
Output: Result=2
Entered arithmetic expression is Valid

Input: (2+5)*3
Output: Result=21
Entered arithmetic expression is Valid

Input: (2*4)+
Output: 
Entered arithmetic expression is Invalid

Input: 2%5
Output: Result=2
Entered arithmetic expression is Valid 
```

**词法分析器源代码:**

```
%{
   /* Definition section */
  #include<stdio.h>
  #include "y.tab.h"
  extern int yylval;
%}

/* Rule Section */
%%
[0-9]+ {
          yylval=atoi(yytext);
          return NUMBER;

       }
[\t] ;

[\n] return 0;

. return yytext[0];

%%

int yywrap()
{
 return 1;
}
```

**解析器源代码:**

```
%{
   /* Definition section */
  #include<stdio.h>
  int flag=0;
%}

%token NUMBER

%left '+' '-'

%left '*' '/' '%'

%left '(' ')'

/* Rule Section */
%%

ArithmeticExpression: E{

         printf("\nResult=%d\n", $);

         return 0;

        };
 E:E'+'E {$=$1+$3;}

 |E'-'E {$=$1-$3;}

 |E'*'E {$=$1*$3;}

 |E'/'E {$=$1/$3;}

 |E'%'E {$=$1%$3;}

 |'('E')' {$=$2;}

 | NUMBER {$=$1;}

 ;

%%

//driver code
void main()
{
   printf("\nEnter Any Arithmetic Expression which 
                   can have operations Addition, 
                   Subtraction, Multiplication, Division, 
                          Modulus and Round brackets:\n");

   yyparse();
   if(flag==0)
   printf("\nEntered arithmetic expression is Valid\n\n");
}

void yyerror()
{
   printf("\nEntered arithmetic expression is Invalid\n\n");
   flag=1;
}
```

**输出:**

![](img/2452367380d972d7cb9d2ef0416d390a.png)