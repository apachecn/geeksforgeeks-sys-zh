# 直接映射、关联映射&集合关联映射

的区别

> 原文:[https://www . geesforgeks . org/difference-direct-mapping-associated-mapping-set-associated-mapping/](https://www.geeksforgeeks.org/difference-between-direct-mapping-associative-mapping-set-associative-mapping/)

**先决条件–**[缓存映射类型–直接映射、关联映射&集合-关联映射](https://www.geeksforgeeks.org/cache-memory-in-computer-organization/)

**Cache:**
SRAM 内存的小部分，加在主内存和处理器(CPU)之间，加快执行的进程，被称为 cache memory。它包括少量的静态随机存取存储器&和更多的动态随机存取存储器。这是一个高速&昂贵的内存。

***缓存命中率** :* 它衡量缓存如何有效地满足获取内容的请求。

```
Cache hit ratio = No of cache hits/ (No of cache hits + No. of cache Miss)
```

如果在缓存中找到了数据，则是缓存命中或缓存未命中。

**缓存映射:**
将主内存块的数据带入缓存块的过程/技术称为缓存映射。
制图技术可分为:

1.  直接映射
2.  联合的
3.  集合关联

**1。直接映射:**
在这种技术中，主内存中的每个块在缓存组织中只有一个可能的位置。
例如:主存储器的每个块 I 可以使用以下公式映射到高速缓存的块 j:

```
j = i modulo m
Where : i = main memory block number
       j = cache block number
       m = number of blocks in the cache
```

这里的地址分为 3 个字段:标签、块和单词。

**将内存地址映射到缓存***—*
地址的 BLOCK 字段用于访问缓存的 BLOCK。然后，将地址中的标签位与块的标签进行比较。对于匹配，当在高速缓存中找到所需的字时，发生高速缓存命中。否则，会发生高速缓存未命中，并且需要的字必须从主存储器带入高速缓存。该单词现在与新标签一起存储在缓存中(旧标签被替换)。

***示例–***
如果我们有一个 8 KB 大小的全关联映射缓存，块大小= 128 字节，假设主内存的大小= 64 KB。(假设字长= 1 字节)然后:

物理地址的位数= 16 位(作为内存大小= 64kb = 2<sup>6</sup>×2<sup>10</sup>= 2<sup>16)</sup>×T6】WORD 的位数= 7 位(作为块大小= 128 字节= 2 <sup>7</sup> )
索引位数= 13 位(作为缓存大小= 8kb = 2<sup>3</sup>×2<sup>10</sup>= 2【T14
块位数=索引位数-字位数= 13–7 = 6 位

OR
(缓存块数=缓存大小/块大小= 8 KB / 128 字节= 8×1024 字节/ 128 字节= 2 <sup>6</sup> 块→6 位)
标签位数=物理地址的位数—索引中的位数= 16-13 = 3 位

**2。关联映射:**
这里主内存块的映射可以用任何一个缓存块来完成。内存地址这里只有 2 个字段:word &标签。这种技术称为全关联缓存映射。

***示例–***
如果我们有一个 8 KB 大小的全关联映射缓存，块大小= 128 字节，假设主内存的大小= 64 KB。那么:
物理地址的位数= 16 位(如内存大小= 64kb = 2<sup>6</sup>×2<sup>10</sup>= 2<sup>16)</sup>
块偏移的位数= 7 位(如块大小= 128 字节= 2 <sup>7</sup>
标记位数=物理地址位数–块偏移量中的位数= 16-7 = 9 位
缓存块数=缓存大小/块大小= 8 KB / 128 字节= 8×1024 字节/ 128 字节= 2 <sup>6</sup> 块。

**3。集合–关联映射:**
它是直接&关联映射两者优点的结合。
这里，缓存由多个集合组成，每个集合由多个块组成。这些关系是:

```
n = w * L
i = j modulo w
where
i : cache set number
j : main memory block number
n : number of blocks in the cache
w : number of sets
L : number of lines in each set
```

这被称为 L 路集合关联映射。使用这个映射，块 Bj 可以被转换成集合 j 中的任何块。

**要将内存地址映射到缓存–**
使用内存地址中的 set 字段，我们访问缓存的特定集合。然后，将地址中的标签位与该组中所有 L 个块的标签进行比较。对于匹配，当在高速缓存中找到所需的字时，发生高速缓存命中。否则，会发生高速缓存未命中，并且需要的字必须从主存储器带入高速缓存。根据使用的替换策略，如果缓存已满，则进行替换。

例如:如果我们有一个 8 KB 大小的全关联映射缓存，块大小= 128 字节，假设主内存的大小= 64 KB，我们有*“2 路”*集合关联映射(假设每个字有 8 位)。然后:

物理地址的位数= 16 位(因为内存大小= 64kb = 2<sup>6</sup>* 2<sup>10</sup>= 2<sup>16)</sup>
缓存块数=缓存大小/块大小= 8 KB / 128 字节= 8×1024 字节/ 128 字节= 2 <sup>6</sup> 缓存块。
主存块数= MM 大小/块大小= 64 KB / 128 字节= 64×1024 字节/ 128 字节= 2 <sup>9</sup> MM 块。
大小为 2 的集数=缓存块数/ L = 2 <sup>6</sup> /2 = 2 <sup>5</sup> 缓存集。(L = 2，因为它是双向集合关联映射)

**直接映射、关联映射的区别&集合关联映射:**

<figure class="table">

|   | **直接映射** | **关联映射** | **集合关联映射** |
| 1. | 只需要一次比较，因为使用直接公式来获得有效的缓存地址。 | 需要与所有标记位进行比较，即高速缓存控制逻辑必须同时检查每个块的标记是否匹配，以便确定块是否在高速缓存中。 | 需要与每个集合的块数相等的比较，因为集合可以包含 1 个以上的块。 |
| 2. | 主存地址分为 3 个字段:标签、**区块** &字。块&单词一起构成一个索引。最低有效标记位标识主存储器块内的唯一字，块位指定其中一个块，标记位是最高有效位。 | 主存地址分为 1 个字段:标签和单词。 | 主存地址分为 3 个字段:标签、**设置** &字。 |
| 3. | 对于主内存中的每个块，缓存组织中都有一个可能的位置，因为我们有一个固定的公式。 | 主存储器块的映射可以用任何高速缓存块来完成。 | 主存储器块的映射可以用任何直接映射高速缓存的特定高速缓存块来完成。 |
| 4. | 如果处理器需要频繁地从两个不同的主存页面访问相同的内存位置，缓存命中率就会降低。 | 如果处理器需要经常从两个不同的主存页面访问相同的内存位置，缓存命中率没有影响。 | 如果频繁访问主存储器的两个不同页面，缓存命中率会降低。 |
| 5. | 这里的搜索时间更少，因为在高速缓存组织中，主存储器中的每个块都有一个可能的位置。 | 当高速缓存控制逻辑检查每个块的标签是否匹配时，搜索时间更长。 | 搜索时间随着每组的块数而增加。 |

</figure>