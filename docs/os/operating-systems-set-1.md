# 操作系统|第 1 套

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-1/](https://www.geeksforgeeks.org/operating-systems-set-1/)

GATE CS 考试中提出了以下问题。

**1。以下哪一项不是有效的死锁预防方案？(GATE CS 2000)**
(a)在请求新资源之前释放所有资源
(b)对资源进行唯一编号，并且从不请求比上次请求的编号更低的资源。
(c)释放任何资源后不要请求资源
(d)执行前请求并分配所有需要的资源。

**回答:** (c)
**参考文献:**
[http://www.cs.jhu.edu/~yairamir/cs418/os4/sld013.htm](http://www.cs.jhu.edu/~yairamir/cs418/os4/sld013.htm)
[http://en.wikipedia.org/wiki/Deadlock](http://en.wikipedia.org/wiki/Deadlock)

 **2。设 m[0]…m[4]为互斥体(二进制信号量)和 P[0] …。流程。
假设每个进程 P[i]执行以下操作:**

```
  wait (m[i]); wait(m[(i+1) mode 4]);

  ------

  release (m[i]); release (m[(i+1)mod 4]);

```

**这可能会导致(GATE CS 2000)**
(a)痛击
(b)死锁
(c)饥饿，但不会死锁
(d)以上都不会

**回答:** (b) **解释:**
你很容易在以下情况下看到僵局..
P[0]已获取 m[0]并等待 m[1]
P[1]已获取 m[1]并等待 m[2]
P[2]已获取 m[2]并等待 m[3]
P[3]已获取 m[3]并等待 m[0]

 **3。显卡的板载内存为 1 MB。
卡不支持以下哪种模式？(GATE CS 2000)**
(a)17 英寸显示器上 256 色的 1600 x 400 分辨率
(b)14 英寸显示器上 1600 x 400 分辨率 1600 万色
(c)17 英寸显示器上 1600 万色的 800 x 400 分辨率
(d)14 英寸显示器上 256 色的 800 x 800 分辨率
 **答案:【T11 因此，我们可以很容易地推断出答案应该是(b)，因为这具有最高的内存要求。让我们验证一下。
存储 16M 颜色像素所需的位数= ceil(log2(16 * 1000000))= 24
1600 x 400 分辨率和 16M 颜色所需的字节数= (1600 * 400 * 24)/8，即 192000000(大于 1MB)。**

 **4 考虑采用 FIFO 页面替换策略的虚拟内存系统。对于任意的页面访问模式，增加主存储器中的页面帧的数量将(GATE CS 2001)**
a)总是减少页面错误的数量
b)总是增加页面错误的数量
c)有时增加页面错误的数量
d)从不影响页面错误的数量

**答案:** (c)
**解释:**
增加页面帧数并不总是能减少页面错误(贝拉迪异常)。详见[http://en.wikipedia.org/wiki/Belady%27s_anomaly](http://en.wikipedia.org/wiki/Belady%27s_anomaly)

 **5。以下哪一项需要设备驱动程序？(GATE CS 2001)**T3)a)寄存器
b)缓存
c)主存
d)磁盘

**回答:** (d)