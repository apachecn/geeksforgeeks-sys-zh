# 数据分析中的多级算法

> 原文:[https://www . geesforgeks . org/数据分析中的多级算法/](https://www.geeksforgeeks.org/the-multistage-algorithm-in-data-analytics/)

在本文中，我们将详细讨论数据分析中的多级算法。我们还将介绍多级算法的工作原理。

**多级算法:**
多级算法是 PCY 算法的改进版本，它使用某些连续的哈希表来进一步减少候选对的数量。这两种算法的矛盾之处在于多阶段需要两个以上的过程来发现频繁对。

**多级算法工作:**

*   **一传:**
    多段一传与 PCY 一传相同。在这一遍之后，频繁的桶被识别并封装在位图中，同样与 PCY 相同。相反，多级的第二遍不计算候选对。相反，它使用另一个哈希表的可访问主内存，使用另一个哈希函数。毕竟，从第一个散列表中获得的位图占据了可访问主存储器的 1/32，而第二个散列表的存储桶或多或少与第一个散列表一样多。

*   **Second Pass :**
    At the point of second pass of multistage, we again go through the folder of baskets. There is no want to count the items again. The multistage algorithm uses supplementary hash tables to lessen the number of candidate pairs.

    然而，我们必须掌握哪些项目频繁的信息，因为我们在第二次和第三次通过时都需要它。在第二遍中，我们将毫无疑问的项目对散列到第二个散列表的桶中。

    在第二遍中，您将看到，只有当一对在 PCY 的第二遍中被计数时，它才会被散列，当且仅当 I 和 j 经常一起出现时，它才会散列{i，j}，然后在第一遍中将该对散列到一个频繁的桶中。

    结果是，第二个哈希表中的计数总和应该明显小于第一遍的总和。结果是，即使第二个哈希表的桶数只有第一个哈希表的 31/32，我们预计第二个哈希表中的频繁桶会比第一个哈希表中的少得多。

    *   **Final Pass :**
    After the second pass, the second hash table is also encapsulated as a bitmap, and that bitmap is stored in main memory. The two bitmaps together take up slightly less than 1/16th of the accessible main memory, so there is still a lot of space to count the candidate pairs on the third pass.

    一对{i，j}在 C2 当且仅当–

    1.  I 和 j 都出现在频繁项列表中。
    2.  对{i，j}进行哈希处理，并传输到创建的第一个哈希表的频繁存储桶中。
    3.  对{i，j}进行哈希处理，并传输到创建的第二个哈希表的频繁存储桶中。*   **第三个约束是多级和 PCY 之间的分歧:**
    很明显，在多级算法中，第一次和最后一次之间可以包含任意数量的路径。有一个限制因素，即每一遍都必须保留前面每一遍的位图。在适当的时候，主内存中没有足够的空间来进行计数。这并不影响我们应用多少遍，坦率频繁的对每次都会散列一个频繁的桶，所以没有办法绕过对它们的计数。