# 操作系统|第 5 集

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-5/](https://www.geeksforgeeks.org/operating-systems-set-5/)

GATE 2012 考试中提出了以下问题。

**1。一个进程执行代码**

```
  fork ();
  fork ();
  fork ();

```

**创建的子进程总数为**
(A)3
(B)4
(C)7
(D)8

答案(三)

让我们为这三行输入一些标签名

```
  fork ();    // Line 1
  fork ();   // Line 2
  fork ();   // Line 3

       L1       // There will be 1 child process created by line 1
    /     \
  L2      L2    // There will be 2 child processes created by line 2
 /  \    /  \
L3  L3  L3  L3  // There will be 4 child processes created by line 3

```

我们还可以使用直接公式来获得子进程的数量。对于 n 个 fork 语句，总是有 2^n-1 个子进程。详见[本](https://www.geeksforgeeks.org/fork-and-binary-tree/)帖。

**2。考虑表**中显示的 3 个流程，P1、P2 和 P3

```
Process     Arrival time    Time unit required
  P1                0                    5
  P2                1                    7
  P3                3                    4

```

**FCFS 和 RRS(CPU 量子为 2 个时间单位的循环调度)策略下 3 个进程的完成顺序为**
(A) **FCFS** : P1、P2、P3 **RR2** : P1、P2、P3
(B) **FCFS** : P1、P3、P2 **RR2** : P1、P3、P2
(C) **FCFS** : P1、P2、T13

答案(C)

**3。考虑虚拟页面引用字符串
1，2，3，2，4，1，3，2，4，1
在运行于计算机系统上的按需分页虚拟内存系统上，该系统的主内存大小为 3 页帧，最初为空。让 LRU、先进先出和最优表示相应页面替换策略下的页面错误数量。然后**
(A)最优< LRU <先进先出(B)最优<先进先出< LRU (C)最优= LRU (D)最优=先进先出答案(B)最优将是 5，先进先出 6 和 LRU 9。

**4。300 千兆字节的文件系统使用具有 8 个直接块地址的文件描述符。1 个间接块地址和 1 个双重间接块地址。每个磁盘块的大小为 128 字节，每个磁盘块地址的大小为 8 字节。该文件系统中最大可能的文件大小为**
(A)3kb
(B)35kb
(C)280 字节
(D)取决于磁盘的大小

答案(二)

磁盘块中存储的可能地址总数= 128/8 = 16

由直接地址块引起的可寻址字节的最大数量= 8*128
由一个单间接地址块引起的可寻址字节的最大数量= 16*128
由一个双间接地址块引起的可寻址字节的最大数量= 16*16*128

最大可能文件大小= 8*128 + 16*128 + 16*16*128 = 35KB

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。