# 强弱实体的区别

> 原文:[https://www . geesforgeks . org/强弱差异实体/](https://www.geeksforgeeks.org/difference-between-strong-and-weak-entity/)

先决条件–[ER 模型](https://www.geeksforgeeks.org/database-management-system-er-model/)
**强实体:**
强实体不依赖于模式中的任何其他实体。强实体总是有一个主键。[强实体](https://practice.geeksforgeeks.org/problems/what-is-the-difference-between-strong-and-weak-entity)由单个矩形表示。两个强实体之间的关系用一颗钻石来表示。
各种强实体组合在一起，就形成了一个强实体集。

[**【弱实体】**](https://practice.geeksforgeeks.org/problems/explain-weak-entity-types) **:**
弱实体依赖强实体来保证其存在。与强实体不同，弱实体没有任何主键。相反，它有一个部分鉴别键。弱实体由双矩形表示。
一强一弱实体之间的关系用双菱形表示。这种关系也被称为**识别关系。**

![](img/a6b057bd5e5bdefee89811b2d91ab403.png)

**强弱实体区别:**

<figure class="table">

| S.NO | 强实体 | 弱实体 |
| 1. | 强实体总是有一个主键。 | 而弱实体具有部分鉴别器密钥。 |
| 2. | 强实体不依赖于任何其他实体。 | 弱实体依赖强实体。 |
| 3. | 强实体由单个矩形表示。 | 弱实体用双矩形表示。 |
| 4. | 两个强实体的关系用一颗钻石来表示。 | 而一个强实体和一个弱实体之间的关系则用双菱形来表示。 |
| 5. | 强大的实体要么完全参与，要么不参与。 | 而弱实体总是有完全的参与。 |

</figure>