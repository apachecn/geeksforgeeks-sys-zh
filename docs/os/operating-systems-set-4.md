# 操作系统|第 4 集

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-4/](https://www.geeksforgeeks.org/operating-systems-set-4/)

GATE CS 考试中提出了以下问题。

**1。在固定块大小的文件系统中使用更大的块大小会导致(GATE CS 2003)**
a)更好的磁盘吞吐量，但磁盘空间利用率较差
b)更好的磁盘吞吐量和更好的磁盘空间利用率
c)更差的磁盘吞吐量，但磁盘空间利用率较好
d)更差的磁盘吞吐量和更差的磁盘空间利用率

回答(a)
如果块大小较大，则寻道时间较少(寻道的块较少)，磁盘性能提高，但请记住，较大的块大小也会造成磁盘空间的浪费。

**2。考虑以下关于用户级线程和内核支持线程的陈述
一、内核支持线程的上下文切换更快
二。对于用户级线程，一次系统调用就可以阻塞整个进程
iii。内核支持的线程可以独立调度
四。用户级线程对内核透明**

以上陈述哪一项是正确的？(GATE CS 2004)
a) (ii)、(iii)和(iv)仅
b) (ii)和(iii)仅
c) (i)和(iii)仅
d) (i)和(ii)

回答(a)

[http://en.wikipedia.org/wiki/Thread_%28computer_science%29](http://en.wikipedia.org/wiki/Thread_%28computer_science%29)

 **3。虚拟内存环境中必须分配给正在运行的进程的最小页面帧数由(GATE CS 2004)**
a)指令集体系结构
b)页面大小
c)物理内存大小
d)内存中的进程数决定

回答(a)
基于指令集架构，每个进程需要的页面数量最少。示例 IBM 370: 6 页处理 MVC(存储到存储移动)指令
指令为 6 字节，可能跨越 2 页。
2 页待处理。
2 页处理到。

**4。在具有 32 位虚拟地址和 1 KB 页面大小的系统中，使用一级页表进行虚拟到物理地址转换是不实际的，因为(GATE CS 2003)**
a)大量的内部碎片
b)大量的外部碎片
c)维护页表的大量内存开销
d)转换过程中的大量计算开销

回答(c)
由于页面尺寸太小，会使页表的尺寸变大。

```
Size of page table =
  (total number of page table entries) *(size of a page table entry)

```

让我们看看页表中有多少条目

```
Number of entries in page table =
                    (virtual address space size)/(page size)
                    = (2^32)/(2^10) 
                    = 2^22

```

现在，让我们看看每个条目有多大。

如果物理内存的大小是 512 兆字节，那么寻址 512 兆字节所需的位数是 29。因此，物理内存中将有(512MB)/(1KB) = (2^29)/(2^10)页帧。要寻址一个页面帧，需要 19 位。因此，页表中的每个条目需要有 19 位。

```
Note that page table entry also holds auxiliary information about the page such 
as a present bit, a dirty or modified bit, address space or process ID information, 
amongst others. So size of page table 
    > (total number of page table entries) *(size of a page table entry)
    > (2^22 *19) bytes
    > 9.5 MB

```

每个进程都需要这么多内存，因为每个进程都维护自己的页表。此外，对于超过 512MB 的物理内存，页表的大小会更大。因此，对于此类场景，建议使用多级页表。

参考文献:
[http://Barbara . statenfield . org/ta/cs162/section-notes/sec8 . txt](http://barbara.stattenfield.org/ta/cs162/section-notes/sec8.txt)
T4】http://en.wikipedia.org/wiki/Page_table

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见 [GATE Corner](http://geeksquiz.com/gate-corner-2/) 。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。