# 检查循环

语法的程序

> 原文:[https://www . geesforgeks . org/c-程序检查循环语法/](https://www.geeksforgeeks.org/c-program-to-check-syntax-of-for-loop/)

按照 C 标准的定义，循环的[语法是:](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)

```
for (initialisation; condition; increment/decrement)
        ... 
```

在语法上，应该有两个分号，一个左括号，一个右括号，以及“for”的正确拼写。因此，要只检查 for 循环的**语法**，编译器要做的是检查以下条件:

*   只写“for”，而不写“For”、“FOR”、“foR”或其任何变体。
*   Total 语句包含两个分号“；”在右括号“)”结束之前。
*   语句结尾有左括号“(”在“for”关键字之后，有右括号“)”。

**示例:**

```
Input : for (i = 10; i < 20 i++) 
Output : Semicolon Error

Input : for(i = 10; i < 20; i++
Output : Closing parenthesis absent at end 
```

**代码–**

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

//array to copy first three characters of string str
char arr[3]; 

void isCorrect(char *str)
{

    //semicolon, bracket1, bracket2 are used 
        //to count frequencies of
    //';', '(', and ')' respectively
    //flag is set to 1 when an error is found, else no error
    int semicolon = 0, bracket1 = 0, bracket2 = 0, flag = 0;

    int i;
    for (i = 0; i < 3; i++)
        arr[i] = str[i];

    //first 3 characters of the for loop statement is copied
    if(strcmp(arr, "for") != 0)
    {
        printf("Error in for keyword usage");
        return;
    }

    //Proper usage of "for" keyword checked
    while(i != strlen(str))
    {
        char ch = str[i++];
        if(ch == '(')
        {
            //opening parenthesis count
            bracket1 ++;
        }
        else if(ch == ')')
        {
            //closing parenthesis count
            bracket2 ++;

        }
        else if(ch == ';')
        {
            //semicolon count
            semicolon ++;
        }
        else continue;

    }

    //check number of semicolons
    if(semicolon != 2)
    { 
        printf("\nSemicolon Error");
        flag++;
    }

    //check closing Parenthesis
    else if(str[strlen(str) - 1] != ')')
    { 
        printf("\nClosing parenthesis absent at end");
        flag++;
    }

    //check opening parenthesis
    else if(str[3] == ' ' && str[4] != '(' )
    { 
        printf("\nOpening parenthesis absent after for keyword");
        flag++;
    }

    //check parentheses count
    else if(bracket1 != 1 || bracket2 != 1 || bracket1 != bracket2)
    { 
        printf("\nParentheses Count Error");
        flag++;
    }

    //no error 
    if(flag == 0)
        printf("\nNo error");

}

int main(void) {

    char str1[100] = "for (i = 10; i < 20; i++)";
    isCorrect(str1);

    char str2[100] = "for i = 10; i < 20; i++)";
    isCorrect(str2);

    return 0;
}
```

**输出:**

```
No error
Opening parenthesis absent after for keyword 
```