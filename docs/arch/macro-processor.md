# 宏处理器

> 原文:[https://www.geeksforgeeks.org/macro-processor/](https://www.geeksforgeeks.org/macro-processor/)

宏指令对程序员来说是一种显著的便利。对于宏的每次出现，整个宏体或宏语句块都会在主源代码中展开。因此宏指令使得编写代码更加方便。

**宏处理器的显著特征:**

*   **宏**代表源编程语言中一组常用的语句。
*   宏处理器用相应的一组源语言语句替换每个宏指令。这被称为宏的扩展。
*   使用宏指令，程序员可以将机械细节留给宏处理器处理。
*   宏处理器的设计与其运行的计算机体系结构没有直接关系。
*   宏处理器包括定义、调用和扩展。

**宏观定义和扩展:**

```
 Line                 Label                 Opcode                 Operand  
5                    COPY                  START                  0
10                   RDBUFF                MACRO                  &INDEV, &BUFADR
15                   
.
.
90
95                                         MEND

```

*   **第 10 行:**
    标签部分的 RDBUFF(读取缓冲区)是宏的名称或宏的定义。& INDEV 和&buadr 是操作数部分的参数。每个参数都以字符&开头。
*   **15 号线-90 号线:**
    从 15 号线到 90 号线有宏观体。宏指令是构成宏定义主体的语句。
*   **第 95 行:**
    MEND 是汇编指令，表示宏定义结束。

**宏调用:**

```
 Line                 Label                 Opcode                 Operand  
180                  FIRST                 STL                    RETADR
190                  CLOOP                 RDBUFF                 F1, BUFFER
15                   
.
.
255                                         END                    FIRST

```

**第 190 行:**
RDBUFF 是给出被调用宏指令名称的宏调用或宏调用，F1、BUFFER 是用于扩展宏的参数。每次调用宏时，都会生成构成宏扩展的语句。