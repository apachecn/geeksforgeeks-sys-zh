# 关系查询评估|集合 2

> 原文:[https://www . geesforgeks . org/relational-query-evaluation-set-2/](https://www.geeksforgeeks.org/relational-query-evaluation-set-2/)

先决条件–[关系查询评估|集合 1](https://www.geeksforgeeks.org/relational-query-evaluation-set-1/)
数据存储在磁盘中。然后使用读写方法操作磁盘。操作数量越多，失败的磁盘数量就越少。为了克服这一点并延长磁盘寿命，我们希望通过确保尽可能减少使用磁盘的读写操作来优化磁盘使用。

1.  **[Projection Operation](https://www.geeksforgeeks.org/project-operation-in-relational-algebra/) –**
    This operation involves selection of attributes from record. This operation is costly one. For carrying out projection operation, every record in file needs to be scanned to formulate resulting record. Duplicate records in resulting record need to be eliminated using sort or hash-based functions. It is essential to do entire file scan in case of using projection operation. A cost-friendly method would involve using projection operations only after selection operations. This is because there would be fewer records after selection is done and then, projection operation can occur involving lesser cost, lesser read and write operations and more life of disks.
2.  **排序–**
    排序是非常常用的操作。它用于删除重复元素、记录分组、连接等。外部排序涉及磁盘上存在的巨大文件。我们可以按照记录的升序或降序排列文件。我们对这些操作使用合并排序。[合并排序](https://www.geeksforgeeks.org/merge-sort/)涉及 2 个阶段，即排序阶段和合并阶段。使用排序阶段是在创建子文件，其中排序是普遍的。这些排序的子文件也称为运行。合并阶段已知用于合并子文件以最终创建一个已排序的文件。

**假设:**
假设数据非常巨大，存储在 n 个块中，内存(m 个块)比数据小得多。接下来要做的是读取 m 个块，在内存中排序，然后作为一个名为 run 的文件写入磁盘。
重复这些步骤–

```
(n / m) number of times 
```

只要值不是整数，就取上限值。

**复杂度:**

```
(2*n) times block access
```

我们可以说已经创建了“r”个子文件，每个子文件都被排序了。缓冲区空间只有 m 个块，我们一次只能对 m 个块进行操作。然后，将操作部分移到内存中，并对下一个块进行操作(每次最多 m 个块)。