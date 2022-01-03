# 缓存未命中的类型

> 原文:[https://www.geeksforgeeks.org/types-of-cache-misses/](https://www.geeksforgeeks.org/types-of-cache-misses/)

当数据在[高速缓冲存储器](https://www.geeksforgeeks.org/cache-memory-in-computer-organization/)中不可用时，发生**高速缓冲存储器未命中**。当中央处理器检测到未命中时，它通过从主存储器获取请求的数据来处理未命中。

**缓存未命中的类型:**
以下是各种类型的缓存未命中。

1.  **Compulsory Miss –**
    It is also known as cold start misses or first references misses. These misses occur when the first access to a block happens. Block must be brought into the cache.

2.  **Capacity Miss –**
    These misses occur when the program working set is much larger than the cache capacity. Since Cache can not contain all blocks needed for program execution, so cache discards these blocks.
3.  **Conflict Miss –**
    It is also known as collision misses or interference misses. These misses occur when several blocks are mapped to the same set or block frame.These misses occur in the set associative or direct mapped block placement strategies.
4.  **连贯缺失–**
    也叫失效。当其他外部处理器(即输入/输出)更新内存时，就会发生这些未命中。

**这些缓存未命中的属性:**
这些是相同数据集和不同类型缓存的缓存未命中的各种属性:

*   强制未命中在所有类型的直接映射、集合关联和关联缓存中都同样发生。
*   在所有类型的直接映射、集合关联和关联缓存中，一致性未命中的情况都是一样的。
*   冲突未命中在直接映射缓存中发生率高，在集合关联缓存中发生率中等，在关联映射缓存中发生率为零。
*   容量未命中在直接映射高速缓存中发生率较低，在集合关联高速缓存中发生率中等，在关联映射高速缓存中发生率较高。

一般来说，我们使用随机块替换、 [LRU](https://www.geeksforgeeks.org/lru-cache-implementation/) 或[先进先出页面替换](https://www.geeksforgeeks.org/program-page-replacement-algorithms-set-2-fifo/)技术来从主存储器带来高速缓存中的未命中页面。