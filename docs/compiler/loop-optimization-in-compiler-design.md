# 编译器设计中的循环优化

> 原文:[https://www . geesforgeks . org/loop-编译器中的优化-设计/](https://www.geeksforgeeks.org/loop-optimization-in-compiler-design/)

**循环优化**是提高执行速度和减少与循环相关的开销的过程。它在提高缓存性能和有效利用并行处理能力方面发挥着重要作用。科学程序的大部分执行时间都花在循环上。

> 循环优化是独立于机器的优化。

减少内部循环中的指令数量可以提高程序的运行时间，即使该循环之外的代码量增加了。

**循环优化技术:**

1.  **Frequency Reduction (Code Motion):**
    In frequency reduction, the amount of code in loop is decreased. A statement or expression, which can be moved outside the loop body without affecting the semantics of the program, is moved outside the loop.

    **示例:**

    ```
    Initial code:

    while(i<100)
    {
     a = Sin(x)/Cos(x) + i;
     i++;
    }

    Optimized code:

    t = Sin(x)/Cos(x);
    while(i<100)
    {
     a = t + i;
     i++;
    } 
    ```

2.  **Loop Unrolling:**
    Loop unrolling is a loop transformation technique that helps to optimize the execution time of a program. We basically remove or reduce iterations. Loop unrolling increases the program’s speed by eliminating loop control instruction and loop test instructions.

    **示例:**

    ```
    Initial code:

    for (int i=0; i<5; i++)
        printf("Pankaj\n");

    Optimized code:

    printf("Pankaj\n");
    printf("Pankaj\n");
    printf("Pankaj\n");
    printf("Pankaj\n");
    printf("Pankaj\n"); 
    ```

3.  **Loop Jamming:**
    Loop jamming is the combining the two or more loops in a single loop. It reduces the time taken to compile the many number of loops.

    **示例:**

    ```
    Initial Code:

    for(int i=0; i<5; i++)
        a = i + 5;
    for(int i=0; i<5; i++)
        b = i + 10;

    Optimized code:
    for(int i=0; i<5; i++)
    {
     a = i + 5;
     b = i + 10;
    } 
    ```