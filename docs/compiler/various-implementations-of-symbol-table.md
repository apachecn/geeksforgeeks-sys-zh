# 符号表

的各种实现

> 原文:[https://www . geesforgeks . org/各种符号表实现/](https://www.geeksforgeeks.org/various-implementations-of-symbol-table/)

[符号表](https://www.geeksforgeeks.org/symbol-table-compiler/)是一种重要的数据结构，由编译器创建和维护，以便跟踪各种实体(如变量名、对象、函数名、接口等)的出现信息。合成阶段使用编译器在分析阶段从符号表中收集的信息来生成目标代码。

符号表不同实现之间的比较:

**1。数组(已排序):**

*   **插入时间–**
    插入元素时，必须进行遍历，以便将元素向右移动。因此，它需要 O(n)个时间。
*   **查找时间–**
    在查找二分搜索法的时候可以用来查找元素。因此，它需要 0(log n)的时间。

**2。链表:**

*   **插入时间–**
    类似于这里的数组，为了搜索插入位置需要元素遍历。因此，它需要 O(n)个时间。
*   **查找时间–**
    获取数据项时，必须完全遍历链表(线性搜索)。因此，这个操作需要 O(n)个时间。

**3。无序列表:**

*   **插入时间–**
    在无序数组中，插入可以在开头进行，而在无序链表中，插入可以在结尾进行。因此，它需要 O(n)个时间。
*   **查找时间–**
    由于这是一个无序列表，必须搜索完整的列表才能找到元素。因此，它需要 O(n)个时间。

在符号表实现中使用数组、链表或未排序列表的缺点:

*   查找时间与表的大小成正比。
*   每个插入操作之前都有查找操作。

**4。自组织列表:**

*   **插入时间–**
    它通常是一个未排序的列表，因此，插入一个元素所花费的时间为 O(1)。
*   **查找时间–**
    在此搜索元素需要搜索一个元素，然后将它移到列表的开头，这样最常用的元素就在列表的开头。一般来说，未排序的列表搜索需要 O(n)个时间。

将自组织列表用于符号表实现的缺点:
这种实现的缺点是，每当搜索不太频繁的元素时，性能就会变差。

**5。搜索树(平衡):**

*   **插入时间–**
    如果树中有 n 个元素，树的顺序为 k，那么树的高度为 logkn。现在，在最坏的情况下，插入将发生在树的高度。因此，所需时间为 0(logkn)。
*   **查找时间–**
    在平衡搜索树中，搜索所需的时间为 O(logkn)。

将搜索树用于符号表实现的缺点:
这种实现的缺点是树必须始终保持平衡。

**6。哈希:**

*   **插入时间–**
    在哈希表中，插入需要恒定的时间，因此插入所需的时间为 0(1)。
*   **查找时间–**
    在哈希表中搜索需要恒定的时间，因此所需时间为 O(1)。

符号表实现使用哈希的缺点:
这种实现的缺点是当冲突太多时，时间复杂度增加到 0(n)。

因此，我们可以看到符号表的每个实现都是唯一的，并且都有自己的缺点。实现者根据其需求可以选择符号表的任何上述实现。