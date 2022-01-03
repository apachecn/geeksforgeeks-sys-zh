# 编译器设计中的窥视孔优化

> 原文:[https://www . geeksforgeeks . org/peep hole-编译器中的优化-设计/](https://www.geeksforgeeks.org/peephole-optimization-in-compiler-design/)

窥视孔优化是对一小部分代码执行的一种[代码优化](https://www.geeksforgeeks.org/compiler-design-code-optimization/)。它是在一段代码中的非常小的指令集上执行的。

> 执行窥视孔优化的小指令集或小部分代码被称为**窥视孔**或**窗口**。

它基本上是根据替换理论工作的，在替换理论中，一部分代码被更短更快的代码替换，而输出没有变化。

窥视孔是机器相关的优化。

**窥视孔优化目标:**

窥视孔优化的目标是:

1.  提高性能
2.  为了减少内存占用
3.  减少代码大小

**窥视孔优化技术:**

1.  **冗余加载和存储消除:**
    在该技术中，冗余被消除。

    ```
    Initial code:
    y = x + 5;
    i = y;
    z = i;
    w = z * 3;

    Optimized code:
    y = x + 5;
    i = y;
    w = y * 3; 
    ```

2.  **恒折:**
    用户自己可以简化的代码，就简化了。

    ```
    Initial code:
    x = 2 * 3;

    Optimized code:
    x = 6; 
    ```

3.  **强度降低:**
    执行时间消耗较高的操作符被执行时间消耗较少的操作符替换。

    ```
    Initial code:
    y = x * 2;

    Optimized code:
    y = x + x;    or     y = x << 1;

    Initial code:
    y = x / 2;

    Optimized code:
    y = x >> 1; 
    ```

4.  **空序列:**
    无用操作删除。
5.  **组合运算:**
    几个运算被一个等价的单个运算代替。