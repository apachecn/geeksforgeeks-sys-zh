# 操作系统|流程管理|问题 6

> 原文:[https://www . geesforgeks . org/operating-systems-process-synchronization-question-2/](https://www.geeksforgeeks.org/operating-systems-process-synchronization-question-2/)

考虑以下代码片段:

```
if (fork() == 0)
{ a = a + 5; printf("%d,%d\n", a, &a); }
else { a = a –5; printf("%d, %d\n", a, &a); } 
```

假设 u，v 是父进程打印的值，x，y 是子进程打印的值。以下哪一项是正确的？

**(A)** u = x + 10 和 v = y
**(B)** u = x + 10 和 v！= y
**(C)** u + 10 = x 和 v = y
**(D)** u + 10 = x 和 v！= y

**答案:****(C)**

**说明:** fork()在子进程中返回 0，在父进程中返回子进程的进程 ID。
在子(x)中，a = a + 5
在父(u)中，a = a–5；
因此 x = u + 10。
父代和子代中“a”的物理地址必须不同。但是我们的程序访问虚拟地址(假设我们运行在使用虚拟内存的操作系统上)。子进程获得父进程的精确副本，并且“a”的虚拟地址在子进程中不会改变。因此，我们在父代和子代中获得相同的地址。参见[本](http://ideone.com/ckhWR)运行举例。

[本题小考](https://www.geeksforgeeks.org/operating-systems-gq/process-synchronization-gq/)