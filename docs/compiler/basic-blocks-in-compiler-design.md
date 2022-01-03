# 编译器设计中的基本块

> 原文:[https://www . geesforgeks . org/basic-blocks-in-compiler-design/](https://www.geeksforgeeks.org/basic-blocks-in-compiler-design/)

**基本块**是一个直线码序列，除了入口和末端分别没有分支进分支和分支出分支。基本块是一组语句，总是按顺序一个接一个地执行。

第一个任务是将[三地址码](https://www.geeksforgeeks.org/three-address-code-compiler/)的序列划分为基本块。新的基本块从第一条指令开始，添加指令，直到满足跳转或标签。在没有跳转的情况下，控制从一条指令到另一条指令的进一步连续移动。这个想法在下面的算法中被标准化:

**算法:**
将三地址码划分为基本块。

**输入:**三个地址指令的序列。

**过程:**确定中间代码的指令，这些指令是领导者。以下是用于查找领导者的规则:

1.  中间代码的第一个三地址指令是 leader。
2.  作为无条件或有条件跳转/转到语句目标的指令是前导。
3.  紧随无条件或有条件跳转/转到语句之后的指令被视为前导。

对于每个这样确定的领导者，它的基本块包含它自己和所有的指令，直到排除下一个领导者。

**示例:**
将 10*10 矩阵设置为单位矩阵的中间代码:

```
1)  i=1        //Leader 1 (First statement)
2)  j=1             //Leader 2 (Target of 11th statement)
3)  t1 = 10 * i     //Leader 3 (Target of 9th statement) 
4)  t2 = t1 + j
5)  t3 = 8 * t2
6)  t4 = t3 - 88
7)  a[t4] = 0.0
8)  j = j + 1
9)  if j <= goto (3)       
10) i = i + 1                    //Leader 4 (Immediately following Conditional goto statement)
11) if i <= 10 goto (2)
12) i = 1                        //Leader 5 (Immediately following Conditional goto statement)
13) t5 = i - 1                   //Leader 6 (Target of 17th statement) 
14) t6 = 88 * t5
15) a[t6] = 1.0
16) i = i + 1
17) if i <= 10 goto (13) 
```

给定的算法用于将矩阵转换为单位矩阵，即所有对角元素为 0，所有其他元素为 1 的矩阵。步骤(3)-(6)用于制作元素 0，步骤(14)用于制作元素 1。goto 语句递归使用这些步骤。

以上代码共有 **6 个基本块**:
B1)报表 1
B2)报表 2
B3)报表 3-9
B4)报表 10-11
B5)报表 12
B6)报表 13-17