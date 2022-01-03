# 代码生成器设计中的问题

> 原文:[https://www . geeksforgeeks . org/issues-in-design-in-a-code-generator/](https://www.geeksforgeeks.org/issues-in-the-design-of-a-code-generator/)

**代码生成器**将源代码的中间表示转换为机器可以轻松执行的形式。代码生成器需要生成正确的代码。代码生成器的设计应该以这样一种方式来完成，以便于实现、测试和维护。

**在代码生成阶段出现以下问题:**

1.  **代码生成器的输入–**
    代码生成器的输入是前端生成的中间代码，以及符号表中的信息，该信息确定了由中间表示中的名称表示的数据对象的运行时地址。中间代码可能主要用四元组、三元组、间接三元组、后缀符号、语法树、DAG 等来表示。代码生成阶段只是在假设输入没有任何语法和状态语义错误的情况下进行，已经进行了必要的类型检查，并且已经在任何需要的地方插入了类型转换运算符。
2.  **目标程序–**
    目标程序是代码生成器的输出。输出可以是绝对机器语言、可重定位机器语言、汇编语言。

*   作为输出的绝对机器语言的优点是，它可以放在固定的内存位置，并且可以立即执行。
*   作为输出的可重定位机器语言允许子程序和子例程分开编译。可重定位的对象模块可以通过链接加载器链接在一起并加载。但是链接和加载会带来额外的开销。
*   汇编语言作为输出使得代码生成更加容易。我们可以生成符号指令，并在生成代码时使用汇编程序的宏工具。代码生成后，我们需要一个额外的组装步骤。

*   **内存管理–**
    将源程序中的名字映射到数据对象的地址是由前端和代码生成器完成的。三个地址语句中的名称是指名称的符号表条目。然后从符号表条目中，可以确定名称的相对地址。*   **Instruction selection –**
    Selecting the best instructions will improve the efficiency of the program. It includes the instructions that should be complete and uniform. Instruction speeds and machine idioms also plays a major role when efficiency is considered. But if we do not care about the efficiency of the target program then instruction selection is straight-forward.

    例如，相应的三地址语句将被翻译成后面的代码序列，如下所示:

    ```
    P:=Q+R
    S:=P+T

    MOV Q, R0
    ADD R, R0
    MOV R0, P
    MOV P, R0
    ADD T, R0
    MOV R0, S

    ```

    这里，第四条语句是多余的，因为 P 的值在刚刚存储在前一条语句中的语句中被再次加载。这会导致低效的代码序列。给定的中间表示可以被翻译成许多代码序列，在不同的实现之间有显著的成本差异。为了设计好的序列，需要事先了解教学成本，但是准确的成本信息很难预测。

    *   **Register allocation issues –**
    Use of registers make the computations faster in comparison to that of memory, so efficient utilization of registers is important. The use of registers are subdivided into two subproblems:
    1.  在**寄存器分配–**期间，我们只选择那些将驻留在程序中每个点的寄存器中的变量集。
    2.  在随后的**寄存器分配**阶段，选择特定的寄存器来访问变量。

    随着变量数量的增加，寄存器到变量的最优分配变得困难。数学上，这个问题变成 NP 完全的。某些机器要求寄存器对由偶数和下一个奇数寄存器组成。例如

    ```
    M a, b

    ```

    这些类型的乘法指令涉及寄存器对，其中被乘数是偶数寄存器，b，乘法器是偶数/奇数寄存器对的奇数寄存器。

    *   **评估顺序–**
    代码生成器决定指令的执行顺序。计算的顺序会影响目标代码的效率。在许多计算顺序中，有些只需要较少的寄存器来保存中间结果。然而，在一般情况下选择最佳顺序是一个困难的 NP 完全问题。*   **代码生成问题的解决方法:**代码生成器必须始终生成正确的代码。这是非常重要的，因为代码生成器可能会面临许多特殊情况。代码生成器的一些设计目标是:
    *   正确的
    *   易于维护
    *   可试验的
    *   高效的