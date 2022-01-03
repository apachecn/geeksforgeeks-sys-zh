# 计算机组织|位置和缓存友好代码

> 原文:[https://www . geesforgeks . org/computer-organization-location-and-cache-friendly-code/](https://www.geeksforgeeks.org/computer-organization-locality-and-cache-friendly-code/)

[缓存](https://www.geeksforgeeks.org/cache-memory/)是更快的存储器，用于处理数据读取操作中的处理器-存储器间隙，即中央处理器寄存器中的数据读取操作与主存储器中的数据读取操作之间的时间差。寄存器中的数据读取操作通常比主存储器中的快 100 倍，并且随着我们进入存储器层次结构，它会持续大幅增加。

缓存安装在中央处理器寄存器和主存储器的中间，以弥补数据读取的时间差距。高速缓存充当存储在相对较慢的主存储器中的数据和指令子集的临时暂存区。由于高速缓存的大小很小，所以只有处理器在程序执行期间经常使用的数据才存储在高速缓存中。由中央处理器缓存这些经常使用的数据消除了从较慢的主存储器中一次又一次取出数据的需要，这需要数百个中央处理器周期。

缓存有用数据的想法围绕着计算机程序的一个基本属性，即所谓的**局部性**。具有良好局部性的程序倾向于从内存层次结构的上层(即缓存)一次又一次地访问同一组数据项，因此运行速度更快。

**示例:**执行相同数量算术运算但具有不同局部性程度的不同矩阵乘法内核的运行时间可以相差 20 倍！

**地点类型:**

*   **时间局部性–**
    时间局部性表示在程序执行过程中，相同的数据对象很可能被 CPU 重复使用多次。一旦数据对象在第一次未命中时被写入高速缓存，该对象上的后续命中数是可以预期的。由于高速缓存比下一个较低级别的存储(如主存储器)更快，因此这些后续命中可以比原始未命中快得多。
*   **空间局部性–**
    它表示如果一个数据对象被引用一次，那么它的邻居数据对象在不久的将来也很有可能被引用。内存块通常包含多个数据对象。由于空间局部性，我们可以预期在未命中后复制一个块的成本将通过随后对该块中其他对象的引用来分摊。

**局部性的重要性–**
程序中的局部性对软硬件系统的设计和性能有着巨大的影响。在现代计算系统中，基于局部性的优势不仅局限于体系结构，而且操作系统和应用程序的构建方式可以最大程度地利用局部性。

在操作系统中，局部性原则允许系统使用主内存作为最近引用的虚拟地址空间块的缓存，并且在磁盘文件系统中最近使用的磁盘块的情况下也是如此。

类似地，像网络浏览器这样的应用程序通过在本地磁盘上缓存最近引用的文档来利用时间局部性。大容量 web 服务器将最近请求的文档保存在前端磁盘缓存中，无需服务器干预即可满足对这些文档的请求。

**缓存友好代码–**
局部性好的程序通常运行得更快，因为与局部性差的程序相比，它们的缓存未命中率更低。在良好的编程实践中，在分析程序性能时，缓存性能总是被视为重要因素之一。代码如何对缓存友好的基本方法是:

*   **经常使用的情况需要更快:**程序经常把大部分时间投入到几个核心函数上，而这些函数反过来又与循环关系最大。因此，这些循环应该以一种拥有良好局部性的方式来设计。
*   **多个循环:**如果一个程序由多个循环组成，那么最小化内部循环中的高速缓存未命中，以减轻代码的性能。

**例-1:** 通过以下多维数组代码的简单示例，可以理解上述上下文。考虑 sum_array()函数，该函数按行主顺序对二维数组的元素求和:

```
int sumarrayrows(int a[8][4])
{
 int i, j, sum = 0;
 for (i = 0; i < 8; i++)
    for (j = 0; j < 4; j++)
     sum += a[i][j];
 return sum;
}
```

假设高速缓存具有每个 4 个字的块大小，字大小为 4 字节。它最初是空的，因为 C 以行为主的顺序存储数组，所以引用将导致以下命中和未命中模式，与缓存组织无关。

![](img/741b8553b4902f8faa0a3a95213e7d04.png)

包含 w[0]–w[3]的块从内存加载到缓存中，对 w[0]的引用是未命中，但接下来的三个引用都是命中。对 v[4]的引用会导致另一次未命中，因为新块被加载到缓存中，接下来的三个引用是命中，依此类推。一般来说，四个引用中有三个会命中，这是冷缓存可以做到的最好的情况。因此，命中率为 3/4*100 = 75%

**示例-2:** 现在，sum_array()函数按列主顺序对二维数组的元素求和。

```
int sum_array(int a[8][8])
{
 int i, j, sum = 0;
 for (j = 0; j < 8; j++)
   for (i = 0; i < 8; i++)
   sum += a[i][j];
 return sum;
}
```

程序的缓存布局将如图所示:

![](img/e0dda0d41bd902dba25707a66e8cac68.png)

因为 C 以行主顺序存储数组，但在这种情况下，数组是以列主顺序访问的，所以在这种情况下，局部性会变差。引用将按顺序进行:a[0][0]、a[1][0]、a[2][0]等等。由于缓存大小较小，每个引用都会因程序的不良局部性而丢失。因此，命中率将为 0。低命中率最终会降低程序的性能，并导致执行速度变慢。在编程中，应该避免这些类型的实践。

**结论–**
当谈到现实生活中的应用程序和编程领域时，优化的缓存性能给程序带来了很好的加速，即使程序的运行时复杂度很高。快速排序就是一个很好的例子。虽然它的最坏情况复杂度为 O(n)<sup>2</sup>，但它是最受欢迎的排序算法，其中一个重要因素是比许多其他排序算法具有更好的缓存性能。编写代码的方式应该能够最大限度地利用缓存，以加快执行速度。