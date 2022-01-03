# SQL |算术运算符

> 原文:[https://www.geeksforgeeks.org/sql-arithmetic-operators/](https://www.geeksforgeeks.org/sql-arithmetic-operators/)

先决条件:[基本选择语句](https://www.geeksforgeeks.org/sql-select-clause/)、[插入子句](https://www.geeksforgeeks.org/sql-insert-statement/)、 [Sql 创建子句](https://www.geeksforgeeks.org/sql-create/)、 [SQL 别名](https://www.geeksforgeeks.org/sql-aliases/)

我们可以对存储在表中的数据使用各种算术运算符。

算术运算符有:

```
+           [Addition]
-           [Subtraction]
/           [Division]
*           [Multiplication]
%           [Modulus]
```

#### **添加** (+):

用于对数据项进行**加法运算**，数据项包括单列或多列。

**实施**:

```
SELECT employee_id, employee_name, salary, salary + 100
   AS "salary + 100" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资+100 |
| one | 亚历克斯 | Twenty-five thousand | Twenty-five thousand one hundred |
| Two | 阻力比 | Fifty-five thousand | Fifty-five thousand one hundred |
| three | jpm | Fifty-two thousand | Fifty-two thousand one hundred |
| four | ggshmr | Twelve thousand three hundred and twelve | Twelve thousand four hundred and twelve |

在这里，我们对每个员工的工资进行了 100 的加法运算，即单列加法运算。

让我们执行**添加 2 列**:

```
SELECT employee_id, employee_name, salary, salary + employee_id
   AS "salary + employee_id" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 薪资+员工 id |
| one | 亚历克斯 | Twenty-five thousand | Twenty-five thousand and one |
| Two | 阻力比 | Fifty-five thousand | Fifty-five thousand and two |
| three | jpm | Fifty-two thousand | Fifty-two thousand and three |
| four | ggshmr | Twelve thousand three hundred and twelve | Twelve thousand three hundred and sixteen |

这里我们已经完成了 2 列的相互添加，即每个员工的 employee_id 都添加了其工资。

#### **减法** (-):

用于对数据项进行**减法运算**，数据项包括单列或多列。

**实施**:

```
SELECT employee_id, employee_name, salary, salary - 100
    AS "salary - 100" FROM subtraction;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资-100 |
| Twelve | 雀类 | Fifteen thousand | Fourteen thousand nine hundred |
| Twenty-two | 彼得（男子名） | Twenty-five thousand | Twenty-four thousand nine hundred |
| Thirty-two | 报警器 | Five thousand six hundred | Five thousand five hundred |
| forty-two | 沃森 | Ninety thousand | Eighty-nine thousand nine hundred |

这里我们对每个员工的工资做了 100 的减法，即单列减法运算。

让我们执行 2 列的**减法:**

```
SELECT employee_id, employee_name, salary, salary - employee_id
    AS "salary - employee_id" FROM subtraction;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资-员工 id |
| Twelve | 雀类 | Fifteen thousand | Fourteen thousand nine hundred and eighty-eight |
| Twenty-two | 彼得（男子名） | Twenty-five thousand | Twenty-four thousand nine hundred and seventy-eight |
| Thirty-two | 报警器 | Five thousand six hundred | Five thousand five hundred and sixty-eight |
| forty-two | 沃森 | Ninety thousand | Eighty-nine thousand nine hundred and fifty-eight |

在这里，我们做了两列相互相减，即每个员工的 employee_id 从其工资中减去。

**分部** (/):对于**分部**请参考此链接- [分部在 SQL](https://www.geeksforgeeks.org/sql-division/)

#### **乘** (*):

它用于执行数据项**乘法**。

**实施**:

```
SELECT employee_id, employee_name, salary, salary * 100
    AS "salary * 100" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资* 100 |
| one | 雀类 | Twenty-five thousand | Two million five hundred thousand |
| Two | 彼得（男子名） | Fifty-five thousand | Five million five hundred thousand |
| three | 报警器 | Fifty-two thousand | Five million two hundred thousand |
| four | 沃森 | Twelve thousand three hundred and twelve | One million two hundred and thirty-one thousand two hundred |

这里我们对每个员工的工资做了 100 的乘法，即单列乘法运算。

让我们执行 2 列的**乘法:**

```
SELECT employee_id, employee_name, salary, salary * employee_id
     AS "salary * employee_id" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资*员工 id |
| one | 雀类 | Twenty-five thousand | Twenty-five thousand |
| Two | 彼得（男子名） | Fifty-five thousand | One hundred and ten thousand |
| three | 报警器 | Fifty-two thousand | One hundred and fifty-six thousand |
| four | 沃森 | Twelve thousand three hundred and twelve | Forty-nine thousand two hundred and forty-eight |

这里我们已经完成了 2 列的乘法运算，即每个员工的 employee_id 与其工资相乘。

#### **模量** ( %):

当一个数据被另一个数据除时，用来得到**余数**。

**实施**:

```
SELECT employee_id, employee_name, salary, salary % 25000
    AS "salary % 25000" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资% 25000 |
| one | 雀类 | Twenty-five thousand | Zero |
| Two | 彼得（男子名） | Fifty-five thousand | Five thousand |
| three | 报警器 | Fifty-two thousand | Two thousand |
| four | 沃森 | Twelve thousand three hundred and twelve | Twelve thousand three hundred and twelve |

这里我们对每个员工的工资做了 100 的模数，即单列的模数运算。

让我们在两列之间执行**模数运算:**

```
SELECT employee_id, employee_name, salary, salary % employee_id
    AS "salary % employee_id" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 工资百分比员工 id |
| one | 雀类 | Twenty-five thousand | Zero |
| Two | 彼得（男子名） | Fifty-five thousand | Zero |
| three | 报警器 | Fifty-two thousand | one |
| four | 沃森 | Twelve thousand three hundred and twelve | Zero |

这里，我们对两列进行了模数转换，也就是说，每个员工的工资都用其 id 来划分，并显示相应的余数。

基本上**模**是用来检查一个数是**偶数**还是**奇数**。假设一个给定的数如果除以 2 给出 1 作为余数，那么它就是一个*奇数*或者如果除以 2 给出 0 作为余数，那么它就是一个*偶数*。

#### **空的概念**:

如果我们对 **NULL** 进行任何算术运算，那么答案是*总是* null。

**实施**:

```
SELECT employee_id, employee_name, salary, type, type + 100
    AS "type+100" FROM addition;

```

输出:

| 员工 id | 员工名称 | 薪水 | 类型 | + 100 型 |
| one | 雀类 | Twenty-five thousand | 空 | 空 |
| Two | 彼得（男子名） | Fifty-five thousand | 空 | 空 |
| three | 报警器 | Fifty-two thousand | 空 | 空 |
| four | 沃森 | Twelve thousand three hundred and twelve | 空 | 空 |

在这里，输出总是为空，因为对空执行任何操作总是会产生一个*空值*。

**注意**:确保空为**不可用**、**未分配**、**未知**。空是**不是**与*空格*或*零*相同。
要深入了解 NULL，请参考[本链接](https://www.geeksforgeeks.org/sql-null/)。

**参考文献** : [甲骨文文档](https://docs.oracle.com/cd/B19306_01/server.102/b14200/operators002.htm)