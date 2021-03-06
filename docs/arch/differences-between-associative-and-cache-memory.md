# 关联存储器和高速缓冲存储器的区别

> 原文:[https://www . geesforgeks . org/关联和缓存内存之间的差异/](https://www.geeksforgeeks.org/differences-between-associative-and-cache-memory/)

**1。[联想记忆](https://www.geeksforgeeks.org/associative-memory/) :**
如果存储的数据可以通过数据的内容来识别供自己使用，而不是通过访问来识别，那么找到存储在内存中的对象所需的时间可以大大减少。由材料访问的存储单元称为关联存储器或内容可寻址存储器。这种类型的存储器是基于数据内容而不是特定的地址或位置同时并行访问的。如果一个字被写在关联存储器中，则没有给出地址。内存能够找到空的未使用空间来存储单词或指定单词的一部分。内存检测与指定内容匹配的所有单词，并标记它们以供阅读。

**2。 [Cache Memory](https://www.geeksforgeeks.org/cache-memory-in-computer-organization/) :**
如果能把程序的活动部分和数据保存在快速内存中，总的执行时间就能大大减少。这种存储器被称为高速缓冲存储器，它插在中央处理器和主存储器之间。为了使这种安排有效。高速缓存需要比主存快得多。这种方法比使用快速存储设备来实现整个主存储器更经济。

**关联存储器和高速缓冲存储器的区别:**

<center>

| 没有。 | 相联存储器 | 高速缓冲存储器 |
| --- | --- | --- |
| one | 通过内容访问存储单元称为关联存储器。 | 又快又小的内存称为高速缓存。 |
| Two | 它减少了查找存储在内存中的项目所需的时间。 | 它减少了平均内存访问时间。 |
| three | 这里的数据是通过其内容访问的。 | 在这里，数据是通过其地址来访问的。 |
| four | 它用于搜索时间非常短的地方。 | 当重复访问特定的数据组时使用。 |
| five | 其基本特征是匹配其内容的逻辑电路。 | 它的基本特点是访问速度快。 |

</center>