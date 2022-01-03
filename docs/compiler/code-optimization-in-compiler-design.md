# 编译器设计中的代码优化

> 原文:[https://www . geesforgeks . org/code-optimization-in-compiler-design/](https://www.geeksforgeeks.org/code-optimization-in-compiler-design/)

合成阶段的代码优化是一种程序转换技术，它试图通过使中间代码消耗更少的资源(即中央处理器、内存)来改进中间代码，从而产生运行更快的机器代码。编译器优化过程应满足以下目标:

*   优化必须是正确的，它绝不能以任何方式改变程序的意义。
*   优化应该提高程序的速度和性能。
*   编译时间必须保持合理。
*   优化过程不应延迟整个编译过程。

**何时优化？**
代码优化通常在开发阶段结束时执行，因为它降低了可读性，并增加了用于提高性能的代码。

**为什么要优化？**
优化算法超出了代码优化阶段的范围。所以程序优化了。它可能包括减少代码的大小。因此，优化有助于:

*   减少占用的空间，提高编译速度。
*   手动分析数据集需要大量时间。因此，我们使用像 Tableau 这样的软件进行数据分析。类似地，手动执行优化也很乏味，最好使用代码优化器来完成。
*   优化的代码通常会促进重用。

**代码优化的类型–**优化过程可以大致分为两种类型:

1.  **机器独立优化–**此代码优化阶段尝试改进**中间代码**，以获得更好的目标代码作为输出。这里转换的中间代码部分不涉及任何中央处理器寄存器或绝对内存位置。
2.  **机器相关优化–**机器相关优化在**目标代码**生成后，根据目标机器架构转换代码时进行。它涉及到 CPU 寄存器，可能有绝对内存引用，而不是相对引用。依赖于机器的优化器努力最大限度地利用内存层次的**。**

**代码优化以下列不同方式完成:**

1.  **编译时间评估:

    ```
    (i)  A = 2*(22.0/7.0)*r 
         Perform 2*(22.0/7.0)*r at compile time.
    (ii)  x = 12.4
          y = x/2.3 
          Evaluate x/2.3 as 12.4/2.3 at compile time.
    ```** 
2.  **Variable Propagation :

    ```
    //Before Optimization 
    c = a * b                                               
    x = a                                                  
    till                                                           
    d = x * b + 4 

    //After Optimization 
    c = a * b  
    x = a
    till
    d = a * b + 4
    ```

    因此，在变量传播之后，a*b 和 x*b 将被识别为公共子表达式。** 
3.  **死代码消除:变量传播往往导致赋值语句变成死代码

    ```
    c = a * b                                                
    x = a                                                
    till                                                          
    d = a * b + 4   

    //After elimination :
    c = a * b
    till
    d = a * b + 4
    ```** 
4.  **代码动作:
    ·降低表达式的求值频率。
    将循环不变语句带出循环。

    ```
    a = 200;
     while(a>0)
     {
         b = x + y;
         if (a % b == 0}
         printf(“%d”, a);
       }

    //This code can be further optimized as
    a = 200;
    b = x + y;
    while(a>0)
     {
         if (a % b == 0}
         printf(“%d”, a);
       }
    ```** 
5.  **感应变量和强度缩减:
    :感应变量用于以下类型的赋值 i = i +常量的循环中。
    ·强度降低意味着用低强度代替高强度操作。

    ```
    i = 1;                                                                      
    while (i<10)                                                          
    {                                                                             
        y = i * 4; 
    }

    //After Reduction
    i = 1
    t = 4
    { 
       while( t<40) 
       y = t; 
       t = t + 4;
    }
    ```** 

****在哪里应用优化？**
现在我们已经了解了优化的必要性和它的两种类型，现在让我们看看在哪里应用这些优化。**

*   ****源程序**
    优化源程序包括对算法进行修改或改变循环结构。用户是这里的行动者。**
*   ****中间代码**
    优化中间代码涉及改变地址计算和转换涉及的过程调用。这里编译器就是演员。**
*   ****目标代码**
    优化目标代码由编译器完成。寄存器、选择和移动指令的使用是目标代码优化的一部分。**

****Phases of Optimization**
There are generally two phases of optimization:**

*   ****全局优化:**
    变换应用于包含函数、过程和循环的大型程序段。***   ****Local Optimization:**
    Transformations are applied to small blocks of statements.The local optimization is done prior to global optimization.

    **参考–**https://en.wikipedia.org/wiki/Optimizing_compiler

    本文由 **Priyamvada Singh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**