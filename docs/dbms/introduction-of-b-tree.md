# b+树介绍

> 原文:[https://www.geeksforgeeks.org/introduction-of-b-tree/](https://www.geeksforgeeks.org/introduction-of-b-tree/)

为了实现动态多级索引，一般采用 [B 树](https://www.geeksforgeeks.org/b-tree-set-1-introduction-2/)和 B+树。然而，用于索引的 B 树的缺点是，它将对应于特定键值的数据指针(指向包含键值的磁盘文件块的指针)与该键值一起存储在 B 树的节点中。这种技术大大减少了可以打包到 B 树节点中的条目数量，从而有助于增加 B 树中的级别数量，因此增加了记录的搜索时间。

B+树通过仅在树的叶节点存储数据指针消除了上述缺点。因此，B+树的叶节点结构与 B 树的内部节点结构有很大不同。这里可以注意到，由于数据指针只出现在叶节点，叶节点必须存储所有键值以及它们对应的指向磁盘文件块的数据指针，以便访问它们。此外，叶节点被链接以提供对记录的有序访问。因此，叶节点形成第一级索引，内部节点形成多级索引的其他级。叶节点的一些键值也出现在内部节点中，只是作为控制记录搜索的媒介。

从上面的讨论可以明显看出，B+树不同于 B-树，它有两个顺序，“a”和“B”，一个用于内部节点，另一个用于外部(或叶)节点。

**顺序为‘a’的 B+树的内部节点结构如下:**

1.  每个内部节点的形式为:
    T24】P<sub>1</sub>，K <sub>1</sub> ，P <sub>2</sub> ，K <sub>2</sub> ，…..，P <sub>c-1</sub> ，K <sub>c-1</sub> ，P <sub>c</sub> >
    其中 c < = a，每个 **P <sub>i</sub> 为树指针(即指向树的另一个节点)**，每个 **K <sub>i</sub> 为键值**(参考图-I)。
2.  每个内部节点都有:K <sub>1</sub> < K <sub>2</sub> < …。< K <sub>c-1</sub>
3.  对于由 P <sub>i</sub> 指向的子树中的每个搜索字段值“X”，以下条件成立:
    K<sub>I-1</sub>T11】X<= K<sub>I</sub>，对于 1 < i < c 和，
    K <sub>i-1</sub> < X，对于 i = c
    (参考图一)
4.  每个内部节点最多有“a”个树指针。
5.  根节点至少有两个树指针，而其他内部节点每个都至少有一个树指针。
6.  如果任何内部节点有“c”指针，c <= a，那么它就有“c–1”键值。

![](img/0eff3c20fb9a50e68cb050572ffcfc03.png)
**示意图-I**

**序为‘B’的 B+树的叶节点结构如下:**

1.  每个叶节点的形式为:
    < < K <sub>1</sub> 、D <sub>1</sub> >、< K <sub>2</sub> 、D <sub>2</sub> >、…..、< K <sub>c-1</sub> 、D <sub>c-1</sub> >、P <sub>下一个</sub> >
    其中 c < = b 并且每个 **D <sub>i</sub> 是数据指针(即指向键值为 K <sub>i</sub> 的磁盘中的实际记录或者指向包含该记录的磁盘文件块)**，以及每个**K【T20**
2.  每个叶节点有:K <sub>1</sub> < K <sub>2</sub> < …。< K <sub>c-1</sub> ，c < = b
3.  每个叶节点至少有\ceil(b/2)个值。
4.  所有叶节点都在同一级别。

![](img/4814274814ca0284345c50875e565651.png)
**示意图-二**

使用 P <sub>下一个</sub>指针遍历所有叶节点是可行的，就像链表一样，从而实现对存储在磁盘中的记录的有序访问。

**b+树示意图–**

![](img/73be5dbd1e6e265749687383f7bf36c1.png)

**优势–**
与具有相同‘l’级的 B-树相比，具有‘l’级的 B+树可以在其内部节点中存储更多条目。这突出了对任何给定关键字的搜索时间的显著改进。具有较低的级别和存在下一个 T4 指针意味着 B+树在从磁盘访问记录时非常快速和有效。