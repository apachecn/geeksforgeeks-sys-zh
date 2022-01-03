# LEX 代码中的 DFA，接受以 11 结尾的字符串

> 原文:[https://www . geesforgeks . org/DFA-in-lex-code-哪些接受字符串-以-11 结尾/](https://www.geeksforgeeks.org/dfa-in-lex-code-which-accepts-strings-ending-with-11/)

先决条件:[设计有限自动机](https://www.geeksforgeeks.org/designing-finite-automata-from-regular-expression/)
**问题:**设计一个 LEX 代码来构造一个接受该语言的 DFA:所有以“11”结尾的字符串都在输入“0”和“1”上。

**示例:**

```
Input: 100011 
Output: Accepted

Input: 100101
Output: Not Accepted

Input: asdf
Output: Invalid 
```

**方法:**
LEX 默认为我们提供一个 INITIAL 状态。所以为了制作一个 DFA，用这个作为 DFA 的初始状态。现在，我们定义了另外三种状态 A、B 和 DEAD，如果遇到错误或无效输入，将使用 DEAD 状态。当用户输入无效字符时，移动到“死亡”状态并打印消息“无效”，如果输入字符串在状态 B 结束，则显示消息“已接受”。如果输入字符串结束于初始状态，然后显示一条消息“不接受”。

![](img/f7d0cb29fac5e234cfa515aad5d5d7da.png)

**注:**
要编译 LEX 程序，用户需要一个 UNIX 系统和 flex，可以使用 sudo apt-get install flex 进行安装。使用上述所有规范，打开 UNIX 终端并执行以下操作:

1.  使用 lex 程序将规范文件更改为 C 语言程序。生成的程序在 lex.yy.c 文件中。
2.  使用带有-ll 标志的 cc 命令来编译程序，并将程序与 lex 子程序库链接起来。生成的可执行程序在 a.out 文件中。

```
lex lextest
cc lex.yy.c -lfl 
```

**LEX Code:**

```
%{
%}

%s A B DEAD

%%
<INITIAL>1 BEGIN A;
<INITIAL>0 BEGIN INITIAL;
<INITIAL>[^01\n] BEGIN DEAD;
<INITIAL>\n BEGIN INITIAL; {printf("Not Accepted\n");}

<A>1 BEGIN B;
<A>0 BEGIN INITIAL;
<A>[^01\n] BEGIN DEAD;
<A>\n BEGIN INITIAL; {printf("Not Accepted\n");}

<B>1 BEGIN B;
<B>0 BEGIN INITIAL;
<B>[^01\n] BEGIN DEAD;
<B>\n BEGIN INITIAL; {printf("Accepted\n");} 

<DEAD>[^\n] BEGIN DEAD;
<DEAD>\n BEGIN INITIAL; {printf("Invalid\n");} 

%%

int main()
{
    printf("Enter String\n");
    yylex();
return 0;
}
```

**输出:**

![](img/6c6aa511aad88f25058293e7d93e6da1.png)