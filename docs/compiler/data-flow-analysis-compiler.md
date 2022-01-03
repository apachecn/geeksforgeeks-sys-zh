# 编译器中的数据流分析

> 原文:[https://www.geeksforgeeks.org/data-flow-analysis-compiler/](https://www.geeksforgeeks.org/data-flow-analysis-compiler/)

它是对控制流图中数据流的分析，即决定程序中数据定义和使用信息的分析。借助这种分析，可以进行优化。通常，使用数据流分析计算值的过程。数据流属性表示可用于优化的信息。

**基本术语–**

*   **定义点:**程序中包含某种定义的点。
*   **引用点:**程序中包含对数据项引用的点。
*   **求值点:**程序中包含表达式求值的点。

![](img/c811a85c58ffabd286fd792428b225d7.png)

**数据流属性–**

*   **Available Expression –** A expression is said to be available at a program point x iff along paths its reaching to x. A Expression is available at its evaluation point.
    An expression a+b is said to be available if none of the operands gets modified before their use.

    **示例–**
    ![](img/fce72909a8dc834ec853f73b9c0abf79.png)

    **Advantage–**
    用于排除常见的子表达式。

*   **Reaching Definition –** A definition D is reaches a point x if there is path from D to x in which D is not killed, i.e., not redefined.

    **示例–**
    ![](img/3a933107fb3736c215072b84bf365666.png)

    **优势–**
    用于常量和变量传播。

*   **Live variable –** A variable is said to be live at some point p if from p to end the variable is used before it is redefined else it becomes dead.

    **示例–**
    ![](img/5caa8349f97d89b7030b61941c27f2ad.png)

    **优势–**

    1.  这对寄存器分配很有用。
    2.  它用于死代码消除。
*   **Busy Expression –** An expression is busy along a path if its evaluation exists along that path and none of its operand definition exists before its evaluation along the path.

    **优势–**
    用于执行代码移动优化。