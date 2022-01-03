# 数据库管理系统中功能依赖的类型

> 原文:[https://www . geesforgeks . org/DBMS 中的函数依赖类型/](https://www.geeksforgeeks.org/types-of-functional-dependencies-in-dbms/)

前提:[功能依赖和属性闭包](https://www.geeksforgeeks.org/functional-dependency-and-attribute-closure/)

函数依赖是一种约束，它指定两组属性之间的关系，其中一组属性可以准确地确定其他组的值。表示为 **X → Y** ，其中 X 是一组能够确定 Y 值的属性，箭头左侧的属性集 **X** 称为**行列式**，右侧的属性集 **Y** 称为**从属**。函数依赖用于数学表达数据库实体之间的关系，对于理解关系数据库系统中的高级概念和理解像 Gate 这样的竞争性考试中的问题非常重要。

**例:**

<figure class="table">

| 滚动 _ 否 | 名字 | 部门名称 | 部门建设 |
| --- | --- | --- | --- |
| forty-two | 字母表 | 指挥官（commanding officer) | A4 号 |
| Forty-three | pqr | 信息技术 | A3 号 |
| forty-four | xyz | 指挥官（commanding officer) | A4 号 |
| 45  | xyz | 信息技术 | A3 号 |
| Forty-six | mno | 欧盟委员会（European Commission） | B2 |
| Forty-seven | jkl | 我 | B2 |

**从上表我们可以得出一些有效的函数依赖关系:**

*   roll_no → { name，dept_name，dept_building }，→在这里，roll_no 可以确定字段名称、dept_name 和 dept_building 的值，因此是有效的函数依赖项
*   roll_no → dept_name，因为 roll_no 可以决定{name，dept_name，dept_building}的整个集合，所以它也可以决定它的子集 dept_name。
*   dept_name → dept_building，dept_name 可以准确识别 dept_building，因为不同 Dept_name 的部门也会有不同的 dept_building
*   更有效的功能依赖:roll_no → name，{roll_no，name} ⇢ {dept_name，dept_building}等。

**这里有一些无效的函数依赖关系:**

*   名称→部门名称同名的学生可以有不同的部门名称，因此这不是有效的函数依赖关系。
*   dept_building → dept_name 同一栋楼可以有多个部门，例如上表中的部门 me 和 EC 在同一栋楼 B2，因此 dept_building → dept_name 是无效的功能依赖关系。
*   更多无效的功能依赖:名称→ roll_no，{name，dept_name} → roll_no，dept_building → roll_no 等。

**阿姆斯特朗的函数依赖公理/性质:**

1.  **反身性:**如果 Y 是 X 的子集，那么 X→Y 通过反身性规则
    成立，例如{roll_no，name} → name 有效。
2.  **增强:**如果 X → Y 是有效的依赖关系，那么 XZ → YZ 根据增强规则也是有效的。
    例如，如果{ rol _ no，name} → dept_building 有效，那么{ rol _ no，name，dept_name} → {dept_building，dept_name}也有效。→
3.  **及物性**:如果 X → Y 和 Y → Z 都是有效的依赖关系，那么 X→Z 根据及物性规则也是有效的。
    比如 roll _ no→dept _ name&dept _ name→dept _ building，那么 roll_no → dept_building 也是有效的。

### **<u>数据库管理系统中功能依赖的类型:</u>**

1.  琐碎的函数依赖
2.  非平凡函数依赖
3.  多值函数依赖
4.  传递函数依赖

#### 1.<u>琐碎的功能依赖</u>

在**平凡函数依赖**中，依赖始终是行列式的子集。
即如果**X→Y****Y 是 X** 的子集，则称之为琐碎功能依赖

**例如**

<figure class="table">

| 滚动 _ 否 | 名字 | 年龄 |
| --- | --- | --- |
| forty-two | 字母表 | Seventeen |
| Forty-three | pqr | Eighteen |
| forty-four | xyz | Eighteen |

这里， **{roll_no，name} → name** 是琐碎的函数依赖，既然依赖的 **name** 是行列式集 **{roll_no，name}**
的子集，同样， **roll_no → roll_no** 也是琐碎的函数依赖的一个例子。

#### 2.<u>非平凡功能依赖</u>

在**非平凡函数依赖**中，依赖严格来说不是行列式的子集。
即如果**X→Y****Y****不是 X** 的子集，则称之为非平凡函数依赖。

**例如**

<figure class="table">

| **滚动 _ 号** | 名字 | 年龄 |
| --- | --- | --- |
| forty-two | 字母表 | Seventeen |
| Forty-three | pqr | Eighteen |
| forty-four | xyz | Eighteen |

这里， **roll_no → name** 是一个非平凡的函数依赖，既然被依赖的 **name** 是**不是**行列式**roll _ no**T8】的子集同样， **{roll_no，name} → age** 也是一个非平凡的函数依赖，既然 **age** 是**不是{roll_no，name}** 的子集

#### 3.<u>多值函数依赖关系</u>

在**多值函数依赖**中，依赖集的实体相互之间是**而不是** **。**
即如果 **a → {b，c}** 且 **b 与 c** 之间不存在**函数依赖**，则称之为**多值函数依赖。**

**例如**

<figure class="table">

| 滚动 _ 否 | 名字 | 年龄 |
| --- | --- | --- |
| forty-two | 字母表 | 17  |
| Forty-three | pqr | Eighteen |
| forty-four | xyz | Eighteen |
| Forty-five | 字母表 | Nineteen |

在这里， **roll_no → {name，age}** 是多值函数依赖，既然被依赖者 **name** & **age** 是**互不依赖**(即 **name → age** 或 **age → name 不存在！**)

#### <u>4。传递函数依赖</u>

在传递函数依赖中，依赖间接依赖于行列式。
即如果 **a → b** & **b → c** ，那么根据及物性公理， **a → c** 。这是一个**传递函数依赖**

**例如**

<figure class="table">

| 注册 _ 否 | 名字 | 处 | 建筑 _ 编号 |
| --- | --- | --- | --- |
| forty-two | 字母表 | 指挥官（commanding officer) | four |
| Forty-three | pqr | 欧盟委员会（European Commission） | Two |
| forty-four | xyz | 信息技术 | one |
| Forty-five | 字母表 | 欧盟委员会（European Commission） | Two |

这里，**regulate _ no→dept**、 **dept → building_no** 、
因此，根据及物性公理，**regulate _ no→building _ no**是有效的函数依赖。这是一种间接的函数依赖，因此称为传递函数依赖。

</figure>

</figure>

</figure>

</figure>

</figure>