# 二级寻呼的性能

> 原文:[https://www . geesforgeks . org/performance-of-2-level-paging/](https://www.geeksforgeeks.org/performance-of-2-level-paging/)

在本文中，我们将讨论 2 级分页的性能，并且还将讨论如何评估一个表达式来评估 2 级分页的性能。我们一个一个来讨论。

**先决条件:** [操作系统中的分页](https://www.geeksforgeeks.org/paging-in-operating-system/) | [二级分页和多级分页](https://www.geeksforgeeks.org/two-level-paging-and-multi-level-paging-in-os/)

**二级** [**分页**](https://www.geeksforgeeks.org/paging-in-operating-system/) **性能:**

让我们考虑主存储器访问时间为 m。页表存储在主存储器中，然后计算有效存储器访问时间的公式。

```
Effective Memory Access Time(E.M.A.T) = 3M

```

**功能:**

*   TLB is added to improve paging performance.
*   TLB contains frequently mentioned page numbers and corresponding frame numbers.

**评估二级分页** **性能的表达式:**

让我们考虑 TLB 访问时间为 c，TLB 命中率为 x，然后 E.M.A.T 的公式如下。

```
E.M.A.T = x(C+M) + (1 - x)(C+3M)
                           |
                           |
                        N-level Paging
E.M.A.T = x(C+M) + (1 - x)(C+ (N+1)M)

```

**二级分页性能要点:**

1.  Multi-level paging when paging is applied to the page table. The last page table we get is called the first-level page table.
2.  In multi-level paging, when multiple paging is applied to the page table, the first-level page table entry contains the base address of the second-level page table, the second-level page table entry contains the base address of the third-level page table, and so on.
3.  In multi-level paging, when paging is applied to page tables, all page tables (pages of page tables) will be stored in main memory regardless of the level of paging.
4.  In multi-level paging, when paging is applied to page tables, all page table entries contain frame numbers regardless of the paging level.
5.  If the page size is not mentioned in the question, the page size is usually the same everywhere (level).