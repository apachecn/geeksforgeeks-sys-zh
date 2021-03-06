# 前向数据流问题的迭代算法

> 原文:[https://www . geeksforgeeks . org/前向数据流问题迭代算法/](https://www.geeksforgeeks.org/iterative-algorithm-for-a-forward-data-flow-problem/)

**概述:**
这篇文章的目的是告诉你一个前向数据流问题的迭代算法。在开始之前，您应该了解一些与数据流分析相关的术语。

**迭代算法的术语:**
这里，我们将讨论迭代算法的术语如下。

1.  **数据流分析–**
    它被定义为一种技术，在该技术中，在计算机程序中的不同点计算一组值来收集信息。

2.  **控制流图(CFG)–**
    它用于确定分配给变量的特定值可能传播到的程序部分。

3.  **朴素方法(基尔达尔方法)–**
    对程序进行数据流分析最简单的方法是为控制流图的每个节点建立数据流方程，在这种方法中，直到整个系统稳定下来，从而达到一个固定点，因此，通过在每个节点本地重复计算输入的输出来求解它们。

4.  **迭代算法–**
    迭代算法是求解数据流分析方程最常用的方法。在这个算法中，我们特别有两种状态，一种是在状态，另一种是在状态。该算法首先近似每个块的状态，然后通过对状态应用传递函数来计算。通过应用连接操作来更新状态。后两个步骤重复进行，直到我们到达固定点:状态不变的情况。

5.  **上述算法的效率–**
    该算法求解数据流方程的效率受访问本地节点的顺序影响，还取决于数据流方程是用于控制流图上的前向数据流分析还是后向数据流分析。

**求解数据流方程的迭代顺序:**
下面讨论几个求解数据流方程的迭代顺序。

1.  **随机顺序–**
    在这个迭代中，顺序并不知道数据流方程是解决向前还是向后的数据流问题。因此，与专门的迭代顺序相比，性能相对较差。

2.  **后置顺序–**
    这个逆向数据流问题的迭代顺序。一个节点在其所有后继节点都被访问之后被访问，并使用深度优先策略实现。

3.  **反向发布顺序–**
    这是转发数据流问题的迭代顺序。该节点在其任何后继节点被访问之前被访问，除非后边缘到达后继节点。

4.  **前向数据分析–**
    考虑任意点‘p’在前向分析中，我们对事实进行推理，直到‘p’，只考虑‘p’处节点的前辈。在逆向分析中，我们从“p”开始推理事实，只考虑后继者。

**示例–**

```
 line 1: if b==4 then
 line 2:     a = 5;
 line 3: else 
 line 4:    a = 3;
 line 5: endif
 line 6:
 line 7: if  a < 4 then
         ...// rest of the code
```

**示例描述:**
从上面的示例中，我们可以观察到第 7 行变量的到达定义是第 2 行赋值 a = 5 和第 4 行赋值 a = 3 的集合。