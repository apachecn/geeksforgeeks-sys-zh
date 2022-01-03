# k 线图中的各种隐含

> 原文:[https://www.geeksforgeeks.org/various-implicants-in-k-map/](https://www.geeksforgeeks.org/various-implicants-in-k-map/)

**先决条件–**[K–映射(卡诺图)](https://www.geeksforgeeks.org/k-mapkarnaugh-map/)
隐含项是布尔函数的乘积和(SOP)中的乘积/最小项或乘积和(POS)中的和/最大项。例如，考虑一个布尔函数，F = AB + ABC + BC。隐含的是 AB，ABC 和 BC。

1.  **素隐含层–**
    由 K-Map 定义允许的一堆相邻的子元素组成的一组正方形或矩形称为**素隐含层(PI)** ，即 K-Map 中形成的所有可能的组。
    **例:**
    ![](img/fbad8250c6c5b1c851ff62820ea2b585.png)
2.  **本质素隐含–**
    这些子多维数据集(组)覆盖了至少一个不能被任何其他素隐含覆盖的小项。**本质素隐含(EPI)** 是那些总是出现在最终解中的素隐含。
    **例:**
    ![](img/b58ad9c4d038fe4102f1d83cad8c57fd.png)
3.  **冗余素隐含–**
    其每个小项被一些基本素隐含覆盖的素隐含是**冗余素隐含(RPI)** 。这个主要的隐含永远不会出现在最终的解决方案中。
    **例:**
    ![](img/ce5eae1d97b9c63e29f5a13ad3fc1623.png)
4.  **选择性素隐含层**
    那些既不是本质隐含层也不是冗余隐含层的素隐含层被称为**选择性素隐含层(SPI)** 。这些也被称为非本质素蕴涵。它们可能出现在某些解决方案中，也可能不出现在某些解决方案中。
    **例:**
    ![](img/ae8440162509d442e6a1078eb1a82649.png)

**例-1:** 给定 F = ∑(1，5，6，7，11，12，13，15)，求隐含数，PI，EPI，RPI，SPI 的个数。

![](img/3c3782136c366e0475437d431db8085a.png)

```
No. of Implicants = 8
No. of Prime Implicants(PI) = 5
No. of Essential Prime Implicants(EPI) = 4
No. of Redundant Prime Implicants(RPI) = 1
No. of Selective Prime Implicants(SPI) = 0
```

**例-2:** 给定 F =∞(0，1，5，8，12，13)，求隐含数，PI，EPI，RPI，SPI 的个数。

![](img/53bf5f87248b65c5152a6885c866280f.png)

```
No. of Implicants = 6
No. of Prime Implicants(PI) = 6
No. of Essential Prime Implicants(EPI) = 0
No. of Redundant Prime Implicants(RPI) = 0
No. of Selective Prime Implicants(SPI) = 6
```

**例-3:** 给定 F = ∑(0，1，5，7，15，14，10)，求隐含数，PI，EPI，RPI，SPI 的个数。

![](img/ed911a36a9978103d34c193da3495ba7.png)

```
No. of Implicants = 7
No. of Prime Implicants(PI) = 6
No. of Essential Prime Implicants(EPI) = 2
No. of Redundant Prime Implicants(RPI) = 2
No. of Selective Prime Implicants(SPI) = 4
```

**示例-4:** [GATE IT 2006 |问题 35](https://www.geeksforgeeks.org/gate-gate-it-2006-question-35/)