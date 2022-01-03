# 最后一分钟笔记–数据库管理系统

> 原文:[https://www.geeksforgeeks.org/last-minute-notes-dbms/](https://www.geeksforgeeks.org/last-minute-notes-dbms/)

参见所有科目的最后一分钟笔记[此处](https://www.geeksforgeeks.org/lmns-gq/)。

我们将以总结的形式讨论对 GATE 考试有用的重要要点。详情可参考[本](https://www.geeksforgeeks.org/gate-cs-notes-gq/)。 

[**E-R 图**](https://www.geeksforgeeks.org/database-management-system-er-model/):ER 图中最常见的问题是给定 ER 图所需的最小表格数。一般使用以下标准:

<colgroup><col><col></colgroup>
| **基数**T5】 | **最小表数** |
| 1:1 基数，两个实体部分参与 | 2 |
| 1:1 的基数，至少有 1 个实体参与 | 1 |
| 1:n 基数 | 2 |
| m:n 基数 | 3 |

**注:** 这是一般的观察。特殊情况需要注意。如果关系的属性不能移动到任何实体端，我们可能需要额外的表。

[**关系的键**](https://www.geeksforgeeks.org/dbms-keys-candidate-super-primary-alternate-and-foreign/) :关系中有各种类型的键，它们是:

*   **候选关键字:** 能够唯一确定元组的最小属性集。一个关系可以有 1 个以上的候选关键字，其适当的子集不能唯一地确定元组，也不能为空。
*   **超级键:** 能够唯一确定一个元组的属性集。候选键总是一个超级键，但反之则不是。
*   **主键和备用键:** 在各种候选键中，一个键作为主键，其他为备用键。
*   **外键:** 外键是表中的一组属性，用于引用同一表或其他表的主键或替代键。

[**正常形态**](https://www.geeksforgeeks.org/database-normalization-normal-forms/)

*   **第一范式:** 一个关系如果不包含任何多值或复合属性，则处于第一范式。
*   **第二范式:** 如果一个关系不包含任何部分依赖，则它处于第二范式。如果候选关键字的任何适当子集确定了非质数(不是候选关键字的一部分)属性，则该依赖关系称为部分依赖关系。
*   **第三范式:** 一个关系如果不包含任何传递依赖，则处于第三范式。对于处于第三范式的关系，要么 FD 的 LHS 是超级键，要么 RHS 是主属性。
*   **Boyce-Codd 范式:** 一个关系是在**Boyce-Codd**范式如果说 LHS 的每一个 FD 都是超级关键的。正常形式之间的关系可以表示为:**1nf****⊃**t352nft44**⊃**t48T50】t52】3nf****

****[**【关系代数】**](https://www.geeksforgeeks.org/database-management-system-relational-algebra/) :带有基本和扩展运算符的程序语言。****

<colgroup><col><col></colgroup>
| [**基础符**](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/) | **语义**T5】 |
| **σ(选择)**T5】 | 根据给定条件选择行 |
| **【投影】** | 项目部分栏目 |
| **X(叉积)**T5】 | 关系的叉积，返回**m * n**行，其中 m 和 n 分别是 R1 和 R2 的行数。 |
| **U(联盟)**T5】 | 返回 R1 或 R2 的元组。返回的最大行数**= m+n**和 返回的最小行数= **最大行数(m，n)** |
| **【负】** | R1-R2 返回那些在 R1 但不在 R2 的元组。返回的最大行数=**m**和 Min 返回的行数=**m-n** |
| **ρ(重命名)**T5】 | 将关系重命名为其他关系。T3】 |

<colgroup><col><col></colgroup>
| [**扩展运算符**](https://www.geeksforgeeks.org/extended-operators-in-relational-algebra/) | **语义**T5】 |
| **∩(路口)** | 返回 R1 和 R2 的元组。返回的最大行数=最小值(m，n)，返回的最小行数= 0 |
| **⋈ <sub>c</sub> (有条件加入)**

 | 基于某种条件从两个或多个表中选择(叉积后接选择) |
| **【等同连接】** | 是条件连接的一种特例，在属性之间只应用相等条件。T3】 |
| **⋈(Natural 加入)** | 在自然连接中，默认情况下，公共属性的相等条件保持不变，重复属性被移除。 **注:** 自然联接相当于叉积如果两个关系没有共同的属性，一个关系 R 与自身的自然联接将只返回 R。 |
| **⟕(Left 天外加入)** | 对 R 和 S 两个关系应用联接时，R 或 S 的一些元组没有出现在不满足联接条件的结果集中。但是左外连接给出了结果集中 R 的所有元组。对于 的属性，不满足连接条件的 R 元组的值为空 |
| **⟖(Right 天外加入)** | 对 R 和 S 两个关系应用联接时，R 或 S 的一些元组没有出现在不满足联接条件的结果集中。但是右外连接给出了结果集中所有的元组。对于 的属性，不满足连接条件的元组的值为空 |
| **⟗(Full 天外加入)** | 对 R 和 S 两个关系应用联接时，R 或 S 的一些元组没有出现在不满足联接条件的结果集中。但是全外连接给出了结果集中 S 的所有元组和 R 的所有元组。不满足连接条件的 S 的元组对于 R 的属性将具有空值，反之亦然。T3】 |
| **/(师符)** | 除法运算符 A/B 将返回与 B 的每个元组相关联的 A 中的那些元组。 **注意:**B 的属性应该是 A 的属性的适当子集。A/B 中的属性将是 A 的属性-B 的属性。 |

 ****[如何为 GATE 解决关系代数问题–SET 1](https://www.geeksforgeeks.org/how-to-solve-relational-algebra-problems-for-gate/) [如何为 GATE 解决关系代数问题–SET 2](https://www.geeksforgeeks.org/how-to-solve-relational-algebra-problems-for-gate/) [**SQL**【T39】](https://www.geeksforgeeks.org/sql-tutorial/):与关系代数相反，SQL****

<colgroup><col><col></colgroup>
| **符** | **意为** |
| [**选择**](https://www.geeksforgeeks.org/sql-select-query/) | 从一个关系或一组关系中选择列。 **注:** 与关系代数相反，它可能为一个属性的重复值给出重复的元组。 |
| [**出自**](https://www.geeksforgeeks.org/sql-sub-queries-clause/) | **From**用于作为需要从中选择数据的关系或关系集给出输入。 |
| [](https://www.geeksforgeeks.org/sql-where-clause/) | **用于给出条件以用于过滤元组** |
| [**EXISTS**](https://www.geeksforgeeks.org/sql-exists/) | **EXISTS**用于检查相关嵌套查询的结果是否为空(不包含元组)。 |
| [**组乘**](https://www.geeksforgeeks.org/sql-group-by/) | **【分组依据】** 用于根据某个属性或一组属性对元组进行分组，如统计按部门分组的学生人数。 |
| [**按**](https://www.geeksforgeeks.org/sql-order-by/) 排序 | **Order By**用于按照一列或多列对提取的数据进行升序或降序排序。 |
| [**聚合函数**](https://www.geeksforgeeks.org/database-management-system-aggregate-functions/) | 求一个属性的聚合值。主要用于 group by。例如:计数、总和、最小最大值。 **从学生组中选择 count(*)by dept _ id****注:** 我们只能选择属于 group by 的那些列。 |
| [**嵌套查询**](https://www.geeksforgeeks.org/nested-queries-sql/) | 当一个查询是另一个查询的一部分时。解决嵌套查询问题可以在**https://www.geeksforgeeks.org/nested-queries-in-sql/**学习 |

****[**冲突可串行化和冲突等价**](https://www.geeksforgeeks.org/conflict-serializability/) :一个调度如果是冲突等价于一个串行调度，那么它就是冲突可串行化的。****

******检查冲突可串行化******

****要检查一个调度是否冲突可串行化，找到一个调度的所有 **冲突操作对** 并绘制优先图(对于所有冲突操作对， 一个边从 T<sub>I</sub>到 T<sub>j</sub>如果其中一个操作的冲突对是从 T<sub>I而另一个从 T<sub>开始 如果图形不包含循环，则调度是冲突可串行化的，否则它不是冲突可串行化的。</sub></sub>****

****如果一个调度可以通过交换不冲突的操作转换成另一个调度，那么调度被称为冲突等价调度。T3】****

******注:** 两个相位锁定协议产生冲突的可串行化调度但可能遭受死锁。另一方面，基于时间戳的协议没有死锁，但会产生冲突可串行化调度。****

****[**视图可序列化和视图等价**](https://www.geeksforgeeks.org/dbms-how-to-test-two-schedule-are-view-equal-or-not-2/) :如果所有对象的所有条件都满足，则 S1 和 S2 的两个时间表被称为视图等价:****

*   ****若交易T<sub>I</sub>在 S1 读取一个初始值为对象 X，在 S2 也一样，T<sub>I</sub>必须读取****

*   ****若交易T7<sub>I</sub>在 S1 读取交易所写的值T<sub>j</sub>T34】在 S1 为对象 X，同样应****

*   ****若交易T7<sub>I</sub>在 S1 是为一个对象写价值的最终交易 X，在 S2 也是如此，T<sub>I</sub>****

****如果一个时间表与任何串行时间表视图等价，那么它就是视图可序列化的。****

******【不可恢复的时间表:**对于一个交易对<<sub>I</sub>T 如果T<sub>j</sub>正在读取 Ti 更新的值，并且 Tj 是在 Ti 提交之前提交的，则进度将无法恢复。****

******可恢复时间表:**对于一个事务对<<sub>I</sub>T34T 如果T<sub>j</sub>正在读取 Ti 更新的值，并且 Tj 是在提交 Ti 后提交的，则进度将是可恢复的。****

******无级联可恢复计划:**对于一个事务对<T<sub>I</sub>T33】T 如果 Ti 更新的值仅在提交T<sub>I</sub>后被 Tj 读取，则日程将无级联可恢复。****

******严格可恢复:** 对于一个交易对<T15】TT18T20】IT23T26、T28T30】TTT34T36】j 它们之间的关系可以表示为:****

******严格****⊂******无级联可恢复****⊂**t34**可恢复********

****[](https://www.geeksforgeeks.org/indexing-in-databases-set-1/)****

##### ****[文件结构](https://www.geeksforgeeks.org/indexing-in-databases-set-1/)****

****[](https://www.geeksforgeeks.org/indexing-in-databases-set-1/)

**主索引:**:主索引是一个有序的文件，有固定长度的记录，有两个字段。第一个字段与数据文件的主键相同，第二个字段是指向数据块的指针，其中的键是可用的。

使用索引= **日志的平均块访问次数 <sub>2</sub> Bi + 1** ，其中 Bi =索引块数。

**聚类索引:**在数据文件上创建聚类索引，该数据文件的记录在非关键字段(称为聚类字段)上进行物理排序。

**二级索引:**二级索引提供了访问已经存在主要访问权限的文件的二级方式。

```
 Number of index entries = Number of records
```

[**<u>【B 树】</u>**](https://www.geeksforgeeks.org/b-tree-set-1-introduction-2/)
在每一级，我们都有键和数据指针，数据指针指向块或记录。

[**B- Trees 的属性:**](https://www.geeksforgeeks.org/b-tree-set-1-introduction-2/)
B- tree 的根可以在 **2** 和 **P** 之间有子级，其中 P 为树的阶。

**树的顺序**–一个节点可以拥有的最大子节点数。

内部节点可以在 **⌈ P/2 ⌉** 和 **P**
之间有子节点，内部节点可以在**⌈p/2⌉–1**和 **P-1** 之间有键

[**<u>B+ Trees</u>**](https://www.geeksforgeeks.org/database-file-indexing-b-tree-introduction/)
在 b+ Trees 中叶子和非叶子的结构是不同的，所以它们的顺序是。与叶节点相比，非叶节点的顺序更高。

在 B+树中搜索时间会更少，因为它在非叶中没有记录指针，因此深度会降低。

本文由 Sonal Tuteja 供稿。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论****