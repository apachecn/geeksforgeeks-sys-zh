# 数据危害及其处理方法

> 原文:[https://www . geeksforgeeks . org/data-危害及其处理方法/](https://www.geeksforgeeks.org/data-hazards-and-its-handling-methods/)

**当一条指令依赖于前一条指令的结果，并且该指令的结果尚未计算出来时，数据危险**发生。每当两条不同的指令使用相同的存储器时。该位置必须看起来好像是按顺序执行的。

有四种类型的数据依赖关系:写后读(RAW)、读后写(WAR)、写后写(WAW)和读后读(RAR)。这些解释如下。

*   **写后读(RAW) :**
    又称为真依赖或流依赖。当一条指令产生的值被后续指令需要时，就会发生这种情况。例如，

```
ADD R1, --, --;
SUB --, R1, --;
```

需要货摊来处理这些危险。

*   **读后写(WAR) :**
    又叫反依赖症。当一条指令的输出寄存器在被前一条指令读取后立即使用时，就会出现这些危险。例如，

```
ADD --, R1, --;
SUB R1, --, --;
```

*   **写后写(WAW) :**
    也叫输出依赖。当一条指令的输出寄存器在被前一条指令写入后被用于写入时，会出现这些危险。例如，

```
ADD R1, --, --;
SUB R1, --, --;
```

*   **读后读(RAR) :**
    当指令都从同一个寄存器中读取时发生。例如，

```
ADD --, R1, --;
SUB --, R1, --;
```

由于读取寄存器值不会改变寄存器值，因此这些读取后读取(RAR)危险不会对处理器造成问题。

**处理数据危险:**
这些是我们用来处理危险的各种方法:转发、代码记录和失速插入。

这些解释如下。

1.  **转发:**
    它给管道增加了特殊的电路。这种方法之所以有效，是因为所需值通过导线所需的时间比管道段计算结果所需的时间少。
2.  **代码重新排序:**
    我们需要一种特殊类型的软件来重新排序代码。我们称这种软件为依赖硬件的编译器。
3.  **Stall Insertion :** 
    it inserts one or more installs (no-op instructions) into the pipeline, which delays the execution of the current instruction until the required operand is written to the register file, but this method decreases pipeline efficiency and throughput.