# MCQ 关于内存分配和编译的流程

> 原文:[https://www . geesforgeks . org/mcq-内存-分配-编译-进程/](https://www.geeksforgeeks.org/mcq-memory-allocation-compilation-process/)

**1。**下面的代码会输出什么？

## C

```
#include <stdio.h>
#include <stdlib.h>

int main()
{
    union test {
        int i;
        float f;
        char c;
    };
    union test* t;
    t = (union test*)malloc(sizeof(union test));
    t->f = 20.60f;
    printf("%f", t->f);
    return 0;
}
```

(a)垃圾值
(b) 20.600000
(c)语法错误
(d) 20.60
**解释:**
联合提供了使用相同内存位置的有效方式。联盟的所有成员都使用具有最大空间的相同内存位置。
此处，使用的浮体 f 具有

```
f = 20.60f = 20.600000
```

。所以，选项(b)是正确的。
**2。**编译过程的正确顺序是什么？
(a)汇编程序→编译程序→预处理器→链接
(b)编译程序→汇编程序→预处理器→链接
(c)预处理器→编译程序→汇编程序→链接
(d)汇编程序→编译程序→链接→预处理器
**说明:**
选项(c)正确。
**3。**预处理过程中，代码#include 被文件 stdio.h 的内容替换，哪个是真的？
(a)链接代码#include 替换为 stdio.h
(b)是
(c)执行代码#include 替换为 stdio.h
(d)编辑代码#include 替换为 stdio.h
**解释:**
预处理通过用文件 stdio . h
选项(b)的内容替换预处理指令#include 来扩展和提升 C 编程语言。
**4。**为什么要使用 fflush()库函数？
(a)刷新所有流和指定流
(b)仅刷新指定流
(c)刷新输入/输出缓冲区
(d)无效库函数
**解释:**
如定义[在 C](https://www.geeksforgeeks.org/use-fflushstdin-c/) 中使用 fflush(stdin):fflush()通常仅用于输出流。其目的是清除(或刷新)输出缓冲区，并将缓冲的数据移动到控制台(如果是 stdout)或磁盘(如果是文件输出流)。
选项(a)正确。
**5。**指出错误- >

## C

```
#include
#include
#include
int main()
{
    char* ptr;
    *ptr = (int*)malloc(30);
    strcpy(ptr, "RAM");
    printf("%s", ptr);
    free(ptr);
    return 0;
}
```

(a)错误:在 strcpy()语句中。
(b)错误:in * ptr =(int *)malloc(30)；
(c)错误:免费(ptr)；
(d)无错误
**解释:**
赋值从没有强制转换的指针生成整数。选项(b)为真。

**6。**胼胝体()功能为什么用于？
(a)分配指定数量的字节
(b)分配指定数量的字节并将其初始化为零
(c)增加或减少指定内存块的大小，并在需要时重新分配
(d)调用指定内存块执行。
**说明:**

*   malloc():分配指定的字节数。
*   realloc():增加或减少指定内存块的大小。如果需要，重新分配。
*   calloc():分配指定数量的字节并将它们初始化为零。
*   free():将指定的内存块释放回系统。

所以，选项(b)是正确的。
本文由**尼基塔·蒂瓦里**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。