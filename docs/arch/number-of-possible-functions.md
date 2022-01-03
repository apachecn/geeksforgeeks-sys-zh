# 可能的功能数量

> 原文:[https://www.geeksforgeeks.org/number-of-possible-functions/](https://www.geeksforgeeks.org/number-of-possible-functions/)

在下面的文章中，我们将从给定的两组元素中计算可能的函数数量。

**语句:**
假设有两个集合‘A’和‘B’分别包含‘n’和‘m’个数的元素，即集合，

```
'A' = {1, 2, 3, 4, ............, n},
'B' = {1, 2, 3, 4, ............, m} 
```

那么当功能从设置‘A’计数到‘B’时，可能的功能数量将是![m^n](img/40ad2ba454b9aea9faf4c789013b5082.png "Rendered by QuickLaTeX.com")，当功能从设置‘B’计数到‘A’时，可能的功能数量将是![n^m](img/37e1736316db03ba94e2aa83be77ed10.png "Rendered by QuickLaTeX.com")。

**说明:**
在下图中，我们可以看到集合‘A’包含‘n’个元素，集合‘B’包含‘m’个元素。集合“A”的每个元素使集合“B”的每个元素具有“m”个功能，因此可能的功能总数为![m^n](img/40ad2ba454b9aea9faf4c789013b5082.png "Rendered by QuickLaTeX.com")。

![](img/68edb777d200e4b03ad5066ff2b35a97.png)

**示例:**

1.  如果集合“A”包含“3”个元素，集合“B”包含“2”个元素，那么可能的函数总数将是![2^3 = 8](img/aedcdee40a25d6f91f3c698298b8e576.png "Rendered by QuickLaTeX.com")。
2.  如果集合“A”包含“5”个元素，集合“B”包含“2”个元素，那么可能的函数总数将是![2^5 = 32](img/1d631cbc098d51f8b785d00962872a33.png "Rendered by QuickLaTeX.com")。

但是当函数从集合“B”计数到“A”时，公式将是![n^m](img/37e1736316db03ba94e2aa83be77ed10.png "Rendered by QuickLaTeX.com")，其中 n、m 分别是集合“A”和“B”中存在的元素数量，那么例子如下:

1.  如果集合“A”包含“3”个元素，集合“B”包含“2”个元素，那么可能的函数总数将是![3^2 = 9](img/b102bb60cd521c8b451ad16d80d9c563.png "Rendered by QuickLaTeX.com")。
2.  如果集合“A”包含“5”个元素，集合“B”包含“2”个元素，那么可能的函数总数将是![5^2 = 25](img/02ca86152a7a7147457e2ceb99ac3a99.png "Rendered by QuickLaTeX.com")。

类似地，当两组增加到 3 组时，

```
'A' = {1, 2, 3, 4, ............, n},   
'B' = {1, 2, 3, 4, ............, m} 
'C' = {1, 2, 3, 4, ............, p}  
```

那么当函数从集合‘A’计数到‘B’然后计数到‘C’时，可能的函数的数量将是![p^{(m^n)}](img/c6cf8a4e0fffb2b386b7187e1be4586d.png "Rendered by QuickLaTeX.com")，以此类推任意数量的集合。