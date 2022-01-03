# 系统可以处理的最大僵尸进程数

> 原文:[https://www . geesforgeks . org/最大数量-僵尸-进程-系统-可处理/](https://www.geeksforgeeks.org/maximum-number-zombie-process-system-can-handle/)

**[【僵尸进程】](https://www.geeksforgeeks.org/zombie-and-orphan-processes-in-c/)** 或**失效进程**是那些通过退出()系统调用完成执行，但在**进程表**中仍有条目的进程。这是一个处于终止状态的进程。

当使用 **fork()** 系统调用在 **UNIX** 中创建子进程时，如果父进程不可用于从进程表中获取子进程，那么就会出现这种情况。基本上，**僵尸进程**既不是完全**死**也不是完全**活**但是它有一些介于两者之间的状态。

因为在**进程表**中，所有**进程**都有一个条目，甚至是**僵尸进程**。很明显，工艺表的尺寸是**有限**。所以，如果僵尸进程被大量创建，那么**进程表**将被填满，程序将停止，而不完成它们的任务。

这里，我们的任务是**找出创建的僵尸进程的最大数量，以便程序不会停止执行**。解决这个问题的方法是在一个循环中创建一个僵尸进程，并对其进行计数，直到程序不停止执行。

以下是上述想法在 **C** 中的实现:

```
// C program to find number of Zombie processes a 
// system can handle.
#include<stdio.h>
#include<unistd.h>

int main()
{
    int count = 0;
    while (fork() > 0)
    {
        count++;
        printf("%d\t", count);
    }
}
```

输出:

在图像中，我们可以看到在 **11834** 之后，计数的增量停止。然而，这不是一个固定的数字，但它会绕过它。
同样，这将取决于系统配置和实力。

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。