# 分布式数据库管理系统中的碎片

> 原文:[https://www . geeksforgeeks . org/fragment-in-distributed-DBMS/](https://www.geeksforgeeks.org/fragmentation-in-distributed-dbms/)

碎片化是将整个或完整的数据库划分成各种子表或子关系的过程，以便数据可以存储在不同的系统中。子关系或子表的小片段称为*片段*。这些片段被称为逻辑数据单元，存储在不同的站点。必须确保片段能够用于重建原始关系(即没有任何数据丢失)。

在碎片化过程中，假设一个表 T 被碎片化，并被分成多个碎片，比如 T1、T2、T3…TN。这些碎片包含足够的信息，允许恢复原始表 T。这种恢复可以通过对各种碎片使用 UNION 或 JOIN 操作来完成。这个过程叫做 ***数据碎片化*** 。所有这些片段都是独立的，这意味着这些片段不能从其他片段中派生出来。用户不需要在逻辑上关心碎片，这意味着他们不应该关心数据碎片，这被称为*碎片独立性*或者我们可以说*碎片透明性*。

#### **优势:**

*   由于数据存储在使用地点附近，数据库系统的效率将会提高
*   因为数据在本地可用，所以本地查询优化方法对于某些查询来说已经足够了
*   为了维护数据库系统的安全性和隐私性，碎片化是有利的

#### **缺点:**

*   如果需要来自不同片段的数据，访问速度可能会非常快
*   如果我们使用递归分片，那么它将非常昂贵

我们有三种对表进行数据分段的方法:

*   **水平碎裂**
*   **垂直碎裂**
*   **混合或混合碎片化**

我们一个一个来讨论。

### **水平碎片化–**

水平分段是指通过将关系的每一行或(一组行)分配给一个或多个分段来水平划分表的过程。然后，这些片段被分配给分布式系统中的不同端。表中的一些行或元组放在一个系统中，其余的放在其他系统中。属于水平片段的行由关系的一个或多个属性上的条件指定。在关系代数中表 T 上的水平分片，可以表示如下:

> □t0〔p〕t1〔t〕
> 
> 其中，σ是选择的关系代数运算符
> 
> p 是水平碎片满足的条件

请注意，可以对片段执行并集操作来构造表 T。这样包含表 T 所有行的片段称为*完整水平片段。*

**例如，**考虑一个 EMPLOYEE 表(T) :

<figure class="table">

| eno | **用户名** | **设计** | **工资** | dep |
| One hundred and one | A | 字母表 | Three thousand | one |
| One hundred and two | B | 字母表 | Four thousand | one |
| One hundred and three | C | 字母表 | Five thousand five hundred | Two |
| One hundred and four | D | 字母表 | Five thousand | Two |
| One hundred and five | E | 字母表 | Two thousand | Two |

该 EMPLOYEE 表可以分为不同的片段，如:

EMP 1 = σ <sub>Dep = 1</sub> EMPLOYEE

EMP 2 = σ <sub>Dep = 2</sub> EMPLOYEE

这两个片段是:Dep = 1 的 T1 片段

<figure class="table">

| eno | **用户名** | **设计** | **工资** | dep |
| One hundred and one | A | 字母表 | Three thousand | one |
| One hundred and two | B | 字母表 | Four thousand | one |

类似地，基于 Dep = 2 的 T2 片段将是:

<figure class="table">

| eno | **用户名** | **设计** | **工资** | dep |
| One hundred and three | C | 字母表 | Five thousand five hundred | Two |
| One hundred and four | D | 字母表 | Five thousand | Two |
| One hundred and five | E | 字母表 | Two thousand | Two |

现在，这里有可能得到回 T 为 **T = T1 ∪ T2 ∪ …。∪ TN**

### **垂直碎裂**

垂直分片是指通过属性是列来垂直分解表的过程。在这种碎片化中，一些属性存储在一个系统中，其余的存储在其他系统中。这是因为每个站点可能不需要表的所有列。为了进行恢复，每个片段必须包含表中的主键字段。碎片化的方式应该是，我们可以通过自然的 JOIN 操作从碎片中重建一个表，为了实现这一点，我们需要在模式中包含一个名为 ***Tuple-id*** 的特殊属性。为此，用户可以使用任何超级密钥。这样，元组或行就可以链接在一起。预测如下:

> π <sub>a1，a2，…，an</sub> (T)
> 
> 其中，π是关系代数运算符
> 
> a1…，和是 T 的三个分支
> 
> t 是表(关系)

例如，对于 EMPLOYEE 表，我们将 T1 定义为:

<figure class="table">

| eno | **用户名** | **设计** | **元组 _id** |
| One hundred and one | A | 字母表 | one |
| One hundred and two | B | 字母表 | Two |
| One hundred and three | C | 字母表 | three |
| One hundred and four | D | 字母表 | four |
| One hundred and five | E | 字母表 | five |

第二次。垂直分段后的关系子表如下:

<figure class="table">

| **工资** | dep | **元组 _id** |
| Three thousand | one | one |
| Four thousand | Two | Two |
| Five thousand five hundred | three | three |
| Five thousand | one | four |
| Two thousand | four | five |

</figure>

这是 T2，为了回到最初的 t，我们将这两个片段 T1 和 T2 连接为 **π <sub>雇员</sub> (T1 ⋈ T2)**

### **混合碎裂**

一个表的垂直碎片与一些碎片的进一步水平碎片的组合称为**混合或混合碎片**。为了定义这种类型的碎片，我们使用了关系代数的 SELECT 和 PROJECT 操作。在某些情况下，水平和垂直碎片不足以为某些应用程序分发数据，在这种情况下，我们需要一种称为混合碎片的碎片。

混合碎片化可以通过两种不同的方式完成:

1.  第一种方法是首先创建一组或一组水平片段，然后从一个或多个水平片段创建垂直片段。
2.  第二种方法是首先创建一组或一组垂直片段，然后从一个或多个垂直片段创建水平片段。
    原始关系可以通过 JOIN 和 UNION 操作的组合得到，给出如下:

> σ <sub>P</sub> (π <sub>a1、a2..，一</sub> (T))
> 
> π <sub>a1，a2……。，an</sub> (σ <sub>p</sub> (T))

**例如**，对于我们的 **EMPLOYEE** 表，下面是实现混合分片的是 **π <sub>埃纳姆，设计</sub>(σ<sub>Eno<104</sub>(EMPLOYEE))**

这种碎片化的结果是:

<figure class="table">

| **用户名** | **设计** |
| A | 字母表 |
| B | 字母表 |
| C | 字母表 |

</figure>

</figure>

</figure>

</figure>

</figure>