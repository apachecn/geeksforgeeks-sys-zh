# 编译器和解释器的区别

> 原文:[https://www . geesforgeks . org/编译器和解释器之间的区别/](https://www.geeksforgeeks.org/difference-between-compiler-and-interpreter/)

**1。** [**编译器**](https://www.geeksforgeeks.org/introduction-of-compiler-design/) **:**
它是一个翻译器，接受输入即高级语言，并产生低级语言即机器或汇编语言的输出。

*   编译器比汇编器更聪明，它检查各种限制、范围、错误等。
*   但其程序运行时间较多，占用内存较大。它的速度很慢，因为编译器会遍历整个程序，然后将整个程序翻译成机器码。

![](img/b9cfc942cad644745d5796fd23421ea8.png)

**图–**编译器-进程

**2。** [**解释器**](https://www.geeksforgeeks.org/compiler-vs-interpreter-2/) **:**
解释器是将编程语言翻译成可理解语言的程序。–

*   它一次只翻译程序的一条语句。
*   解释器通常比编译器小。

![](img/1ee2f66cefef4b64a2acf0181c790dc2.png)

**图–**解释器-流程

让我们看看编译器和解释器的区别:

<figure class="table">

| 没有。 | 编译程序 | 解释者 |
| --- | --- | --- |
| 1. | 编译器一次扫描整个程序。 | 一次翻译一条程序语句。 |
| 2. | 当它一次扫描代码时，错误(如果有的话)一起显示在最后。 | 考虑到它一次扫描一行代码，错误会一行一行地显示出来。 |
| 3. | 编译器的主要优点是它的执行时间。 | 由于解释器在执行目标代码时速度较慢，所以不太喜欢。 |
| 4. | 它将源代码转换成目标代码。 | 它不会将源代码转换为目标代码，而是逐行扫描 |
| five | 它不需要源代码供以后执行。 | 它需要源代码供以后执行。 |
| 例如。 | C，C++，C#等。 | Python、Ruby、Perl、势利、MATLAB 等。 |

</figure>