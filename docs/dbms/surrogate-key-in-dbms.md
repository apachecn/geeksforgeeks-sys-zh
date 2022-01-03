# 数据库管理系统中的代理键

> 原文:[https://www.geeksforgeeks.org/surrogate-key-in-dbms/](https://www.geeksforgeeks.org/surrogate-key-in-dbms/)

代理键也称为合成主键，当新记录被数据库自动插入表中时生成，该数据库可以声明为该表的主键。它是数据库外部的序列号，可供用户和应用程序使用，或者它充当数据库中的对象，但用户或应用程序看不到它。

我们可以说，在表中没有自然主键的情况下，我们需要人工创建一个主键来唯一标识表中的一行，这个键被称为表的代理键或合成主键。然而，代理键并不总是主键。假设数据库中有多个对象连接到代理键，那么主键和代理键之间就会有多对一的关联，代理键不能用作主键。

**代理键的特征:**

*   它由系统自动生成。
*   它保存匿名整数。
*   它包含表中所有记录的唯一值。
*   用户或应用程序永远不能修改该值。
*   代理键被称为无事实键，因为它只是为了便于识别唯一值而添加的，并且不包含对表有用的相关事实(或信息)。

**考虑一个例子:**
假设我们有两个不同学校的两个表，具有相同的列 registration_no，name 和 percentage，每个表都有自己的自然主键，即 registration_no.
表的学校 A–

<figure class="table">

| **注册号** | **名称** | **百分比** |
| Two hundred and ten thousand one hundred and one | （英、瑞）哈里（人名） | Ninety |
| Two hundred and ten thousand one hundred and two | 麦克斯韦 | Sixty-five |
| Two hundred and ten thousand one hundred and three | 李 | Eighty-seven |
| Two hundred and ten thousand one hundred and four | 克莉丝 | Seventy-six |

</figure>

学校 B 表–

<figure class="table">

| **注册号** | **名称** | **百分比** |
| CS107 | 泰勒 | forty-nine |
| CS108 | 西蒙 | Eighty-six |
| CS109 | 萨姆（男子名） | Ninety-six |
| CS110 | 安迪(男子名ˌ等于 Andrew) | Fifty-eight |

现在，假设我们想要将两所学校的详细信息合并到一个表中。
结果表将是–

<figure class="table">

| **surr_no** | **注册号** | **名称** | **百分比** |
| one | Two hundred and ten thousand one hundred and one | （英、瑞）哈里（人名） | Ninety |
| Two | Two hundred and ten thousand one hundred and two | 麦克斯韦 | Sixty-five |
| three | Two hundred and ten thousand one hundred and three | 李 | Eighty-seven |
| four | Two hundred and ten thousand one hundred and four | 克莉丝 | Seventy-six |
| five | CS107 | 泰勒 | forty-nine |
| six | CS108 | 西蒙 | Eighty-six |
| seven | CS109 | 萨姆（男子名） | Ninety-six |
| eight | CS110 | 安迪(男子名ˌ等于 Andrew) | Fifty-eight |

我们可以观察上面的表，看到 registry _ no 不能是表的主键，因为它与表的所有记录都不匹配，尽管它保存了表的所有唯一值。现在，在这种情况下，我们必须人为地为这个表创建一个主键。我们可以通过在表中添加一个包含匿名整数且与其他列没有直接关系的列 surr_no 来实现这一点。surr_no 的这个附加列是表的代理键。

**代理键的优势:**

*   由于没有与表相关的直接信息，因此更改仅基于应用程序的要求。
*   由于密钥的值相对较小，性能得到了提高。
*   保证键值包含唯一的信息。
*   由于它保存较小的常数值，这使得表的集成变得容易。
*   使我们能够运行快速查询(与自然主键相比)

**代理键的缺点:**

*   代理键值永远不能用作搜索关键字。
*   由于键值与表的数据无关，因此违反了第三范式。
*   代理键的额外列将需要额外的磁盘空间。
*   当我们必须插入或更新表的数据时，我们将需要额外的输入输出。

**代理键的一些例子有:**

*   系统日期和时间戳
*   随机字母数字字符串

</figure>

</figure>