# 计算给定语法的第一组和第二组的程序

> 原文:[https://www . geesforgeks . org/program-calculate-first-follow-set-given-grammar/](https://www.geeksforgeeks.org/program-calculate-first-follow-sets-given-grammar/)

在继续之前，强烈建议您熟悉语法分析、LL(1)解析的基础知识，以及计算语法的第一和第二集合的规则。

1.  [语法分析入门](https://www.geeksforgeeks.org/introduction-to-syntax-analysis-in-compiler-design/)
2.  [为什么先有后有？](https://www.geeksforgeeks.org/why-first-and-follow-in-compiler-design/)
3.  [语法分析中的第一组](https://www.geeksforgeeks.org/first-set-in-syntax-analysis/)
4.  [遵循语法分析中的设置](https://www.geeksforgeeks.org/compiler-design-follow-set-in-syntax-analysis/)

假设读者熟悉上面讨论的基础知识，让我们开始讨论如何实现 C 程序来计算给定语法的第一个和第二个。

**示例:**

```
Input :
E  -> TR
R  -> +T R| #
T  -> F Y
Y  -> *F Y | #
F  -> (E) | i

Output :
First(E)= { (, i, }
First(R)= { +, #, }
First(T)= { (, i, }
First(Y)= { *, #, }
First(F)= { (, i, }

-----------------------------------------------

Follow(E) = { $, ),  }
Follow(R) = { $, ),  }
Follow(T) = { +, $, ),  }
Follow(Y) = { +, $, ),  }
Follow(F) = { *, +, $, ),  }
```

函数 follow 和 followfirst 都涉及给定非终端的 Follow 集的计算。开始符号的以下集合将始终包含“{content}”。现在，Follow 的计算分为三大类:

*   如果任何产品的记录上的非终端紧接着一个终端，那么它可以立即被包括在该非终端的跟随集合中。
*   如果任何产品的 R.H.S .上的一个非终端紧接着一个非终端，那么新的非终端的第一个集合将包含在我们原始非终端的下一个集合中。如果遇到ε，即“#”，则转到产品中的下一个符号。
    **注意:**“#”从不包含在任何非终端的跟随集合中。
*   如果在计算跟随时到达生产的末尾，则该非终端的跟随集将包括该生产的生产线上的非终端的跟随集。这很容易通过递归实现。

**假设:**

1.  ε用“#”表示。
2.  产品的形式是 A=B，其中“A”是单个非终端，“B”可以是终端和非终端的任意组合。
3.  第一个生产规则的 L.H.S .是开始符号。
4.  语法不是递归的。
5.  每一个非终端产品都在不同的生产线上输入。
6.  只有大写字母是非终结符，其他都是终结符。
7.  不要使用“！”或“{ content }”；因为它们被保留用于特殊目的。

**解释:**
将语法存储在 2D 字符数组**产品**上。 **findfirst** 功能用于计算任意非终端的第一个。**的计算首先**属于两大类情况:

*   如果生产记录中的第一个符号是终端，那么它可以直接包含在第一个集合中。
*   如果产品记录中的第一个符号是非终端，那么在该非终端上再次调用 findfirst 函数。像递归这样处理这些情况是最好的解决方案。这里，如果第一个新的非终端包含一个ε，那么我们必须移动到原始产品的下一个符号，它也可以是终端或非终端。

**注意:**对于第二种情况，即使代码看起来很完美，也很容易成为 INFINITE LOOP 的牺牲品。因此，始终跟踪所有函数调用并且永远不要再次调用同一个函数是很重要的。

下面是实现:

## C

```
// C program to calculate the First and
// Follow sets of a given grammar
#include<stdio.h>
#include<ctype.h>
#include<string.h>

// Functions to calculate Follow
void followfirst(char, int, int);
void follow(char c);

// Function to calculate First
void findfirst(char, int, int);

int count, n = 0;

// Stores the final result
// of the First Sets
char calc_first[10][100];

// Stores the final result
// of the Follow Sets
char calc_follow[10][100];
int m = 0;

// Stores the production rules
char production[10][10];
char f[10], first[10];
int k;
char ck;
int e;

int main(int argc, char **argv)
{
    int jm = 0;
    int km = 0;
    int i, choice;
    char c, ch;
    count = 8;

    // The Input grammar
    strcpy(production[0], "E=TR");
    strcpy(production[1], "R=+TR");
    strcpy(production[2], "R=#");
    strcpy(production[3], "T=FY");
    strcpy(production[4], "Y=*FY");
    strcpy(production[5], "Y=#");
    strcpy(production[6], "F=(E)");
    strcpy(production[7], "F=i");

    int kay;
    char done[count];
    int ptr = -1;

    // Initializing the calc_first array
    for(k = 0; k < count; k++) {
        for(kay = 0; kay < 100; kay++) {
            calc_first[k][kay] = '!';
        }
    }
    int point1 = 0, point2, xxx;

    for(k = 0; k < count; k++)
    {
        c = production[k][0];
        point2 = 0;
        xxx = 0;

        // Checking if First of c has
        // already been calculated
        for(kay = 0; kay <= ptr; kay++)
            if(c == done[kay])
                xxx = 1;

        if (xxx == 1)
            continue;

        // Function call   
        findfirst(c, 0, 0);
        ptr += 1;

        // Adding c to the calculated list
        done[ptr] = c;
        printf("\n First(%c) = { ", c);
        calc_first[point1][point2++] = c;

        // Printing the First Sets of the grammar
        for(i = 0 + jm; i < n; i++) {
            int lark = 0, chk = 0;

            for(lark = 0; lark < point2; lark++) {

                if (first[i] == calc_first[point1][lark])
                {
                    chk = 1;
                    break;
                }
            }
            if(chk == 0)
            {
                printf("%c, ", first[i]);
                calc_first[point1][point2++] = first[i];
            }
        }
        printf("}\n");
        jm = n;
        point1++;
    }
    printf("\n");
    printf("-----------------------------------------------\n\n");
    char donee[count];
    ptr = -1;

    // Initializing the calc_follow array
    for(k = 0; k < count; k++) {
        for(kay = 0; kay < 100; kay++) {
            calc_follow[k][kay] = '!';
        }
    }
    point1 = 0;
    int land = 0;
    for(e = 0; e < count; e++)
    {
        ck = production[e][0];
        point2 = 0;
        xxx = 0;

        // Checking if Follow of ck
        // has already been calculated
        for(kay = 0; kay <= ptr; kay++)
            if(ck == donee[kay])
                xxx = 1;

        if (xxx == 1)
            continue;
        land += 1;

        // Function call
        follow(ck);
        ptr += 1;

        // Adding ck to the calculated list
        donee[ptr] = ck;
        printf(" Follow(%c) = { ", ck);
        calc_follow[point1][point2++] = ck;

        // Printing the Follow Sets of the grammar
        for(i = 0 + km; i < m; i++) {
            int lark = 0, chk = 0;
            for(lark = 0; lark < point2; lark++)
            {
                if (f[i] == calc_follow[point1][lark])
                {
                    chk = 1;
                    break;
                }
            }
            if(chk == 0)
            {
                printf("%c, ", f[i]);
                calc_follow[point1][point2++] = f[i];
            }
        }
        printf(" }\n\n");
        km = m;
        point1++;
    }
}

void follow(char c)
{
    int i, j;

    // Adding "{content}quot; to the follow
    // set of the start symbol
    if(production[0][0] == c) {
        f[m++] = '{content}apos;;
    }
    for(i = 0; i < 10; i++)
    {
        for(j = 2;j < 10; j++)
        {
            if(production[i][j] == c)
            {
                if(production[i][j+1] != '\0')
                {
                    // Calculate the first of the next
                    // Non-Terminal in the production
                    followfirst(production[i][j+1], i, (j+2));
                }

                if(production[i][j+1]=='\0' && c!=production[i][0])
                {
                    // Calculate the follow of the Non-Terminal
                    // in the L.H.S. of the production
                    follow(production[i][0]);
                }
            }
        }
    }
}

void findfirst(char c, int q1, int q2)
{
    int j;

    // The case where we
    // encounter a Terminal
    if(!(isupper(c))) {
        first[n++] = c;
    }
    for(j = 0; j < count; j++)
    {
        if(production[j][0] == c)
        {
            if(production[j][2] == '#')
            {
                if(production[q1][q2] == '\0')
                    first[n++] = '#';
                else if(production[q1][q2] != '\0'
                          && (q1 != 0 || q2 != 0))
                {
                    // Recursion to calculate First of New
                    // Non-Terminal we encounter after epsilon
                    findfirst(production[q1][q2], q1, (q2+1));
                }
                else
                    first[n++] = '#';
            }
            else if(!isupper(production[j][2]))
            {
                first[n++] = production[j][2];
            }
            else
            {
                // Recursion to calculate First of
                // New Non-Terminal we encounter
                // at the beginning
                findfirst(production[j][2], j, 3);
            }
        }
    }
}

void followfirst(char c, int c1, int c2)
{
    int k;

    // The case where we encounter
    // a Terminal
    if(!(isupper(c)))
        f[m++] = c;
    else
    {
        int i = 0, j = 1;
        for(i = 0; i < count; i++)
        {
            if(calc_first[i][0] == c)
                break;
        }

        //Including the First set of the
        // Non-Terminal in the Follow of
        // the original query
        while(calc_first[i][j] != '!')
        {
            if(calc_first[i][j] != '#')
            {
                f[m++] = calc_first[i][j];
            }
            else
            {
                if(production[c1][c2] == '\0')
                {
                    // Case where we reach the
                    // end of a production
                    follow(production[c1][0]);
                }
                else
                {
                    // Recursion to the next symbol
                    // in case we encounter a "#"
                    followfirst(production[c1][c2], c1, c2+1);
                }
            }
            j++;
        }
    }
}
```

**输出:**

```
 First(E)= { (, i, }
 First(R)= { +, #, }
 First(T)= { (, i, }
 First(Y)= { *, #, }
 First(F)= { (, i, }

-----------------------------------------------

 Follow(E) = { $, ),  }
 Follow(R) = { $, ),  }
 Follow(T) = { +, $, ),  }
 Follow(Y) = { +, $, ),  }
 Follow(F) = { *, +, $, ),  }
```