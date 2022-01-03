# 数据压缩介绍

> 原文:[https://www . geesforgeks . org/数据压缩入门/](https://www.geeksforgeeks.org/introduction-to-data-compression/)

在本文中，我们将讨论数据压缩的概述，并讨论其方法说明，还将涵盖概述部分熵。我们一个一个来讨论。

**概述:**
一个重要的研究领域是[数据压缩](https://www.geeksforgeeks.org/process-of-jpeg-data-compression/)。它涉及以紧凑形式存储信息的艺术和科学。人们会注意到许多压缩包被用来压缩文件。压缩降低了存储成本，提高了算法速度，降低了传输成本。压缩是通过消除冗余来实现的，冗余就是重复不必要的数据。编码冗余是指由于次优编码技术导致的冗余数据。

**方法说明:**

*   为了说明这种方法，让我们假设有六个符号，并且使用二进制代码为每个符号分配一个唯一的地址，如下表所示
*   二进制代码需要至少三位来编码六个符号。还可以观察到，根本没有使用二进制码 110 和 111。这清楚地表明，二进制代码效率不高，因此需要有效的代码来分配唯一的地址。

<figure class="table">

| 标志 | W1 | W2 | W3 | W4 | W5 | W6 |
| --- | --- | --- | --- | --- | --- | --- |
| 可能性 | Zero point three | Zero point three | Zero point one | Zero point one | Zero point zero eight | Zero point zero two |
| 二进制码 | 000 | 001 | 010 | 011 | One hundred | One hundred and one |

</figure>

*   高效的代码是用最少的位数来表示任何信息的代码。二进制码的缺点是它是固定码；霍夫曼码更好，因为它是可变码。
*   编码技术与熵和信息量的概念有关，它们是作为一门叫做信息论的学科来研究的。信息论也处理信息中存在的不确定性，这种不确定性被称为信息内容。信息内容如下

```
                       log<sub>2 (1/pi) or -log2 pi .</sub> 
```

**熵:**

*   熵被定义为信息中有序性的度量。给出如下:

```
                                    H= - ∑ p<sub>i log2 pi</sub>
```

*   熵是一个正数，它指定了编码信息所需的最小位数。因此，编码冗余被给出为用于编码的平均比特数和熵之间的差值。

```
coding redundancy = Average number of bits - Entropy
```

*   通过消除冗余，任何信息都可以以紧凑的方式存储。这是数据压缩的基础。