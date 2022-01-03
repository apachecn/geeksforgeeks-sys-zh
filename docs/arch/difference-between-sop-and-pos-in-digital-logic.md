# 数字逻辑中 SOP 和 POS 的区别

> 原文:[https://www . geesforgeks . org/数字逻辑中 sop 和 pos 的区别/](https://www.geeksforgeeks.org/difference-between-sop-and-pos-in-digital-logic/)

在数字逻辑中，函数的输入和输出是二进制数(布尔值)的形式，即值不是零(0)就是一(1)。因此，数字逻辑也被称为‘布尔逻辑’。这些输入和输出可以被称为“布尔变量”。数字信号的输出布尔变量可以用构成“布尔表达式”的输入布尔变量来表示。

布尔表达式的表示主要有两种方式。它们如下:

1.  产品总和表
2.  总和乘积形式

**注:**
如果输入变量个数为 n，那么布尔代数中的组合总数为 2 <sup>n</sup> 。

如果输入变量(字母 A)的值为:

*   零(0)–A 为低-它应该表示为 A '(A 的补码)
*   一(1)–A 为高–应表示为 A

在布尔逻辑中，

```
AND is represented as '.'
A AND B is written as 'A.B'

OR is represented as '+'
A OR B is written as 'A+B' 
```

例如，考虑输入变量数=3，假设 A、B、c
组合总数为:2 <sup>3</sup> =8。

<figure class="table">

| A | B | C |
| --- | --- | --- |
| Zero | Zero | Zero |
| Zero | Zero | one |
| Zero | one | Zero |
| Zero | one | one |
| one | Zero | Zero |
| one | Zero | one |
| one | one | Zero |
| one | one | one |

**乘积之和(SOP):**
它是写布尔表达式的方法之一。顾名思义，它是通过增加(或运算)产品术语而形成的。这些产品术语也被称为“最小术语”。最小项用“m”表示，它们是布尔变量的乘积(与运算)，要么是范式，要么是补形式。

因此，SOP 是最小项的和，表示为:SOP 中的
F =![\Sigma  ](img/b943463150bf206fc1b575cced01b669.png "Rendered by QuickLaTeX.com")<sub>m</sub>(0，3)
这里，F 是最小项 0 和最小项 3 的和。

例如:

```
A=0, B=0, C=0   Minterm is A'.B'.C'
A=1, B=0, C=1   Minterm is A.B'.C  
```

考虑一个函数 X，它的真值表如下:

<figure class="table">

| A | B | C | X |
| --- | --- | --- | --- |
| Zero | Zero | Zero | Zero |
| Zero | Zero | one | one |
| Zero | one | Zero | Zero |
| Zero | one | one | one |
| one | Zero | Zero | Zero |
| one | Zero | one | Zero |
| one | one | Zero | one |
| one | one | one | Zero |

</figure>

当 X 为高(1)时，函数 X 可以通过添加所有的最小项以标准操作程序的形式编写。
编写 SOP 时，应遵循以下约定:

```
If variable A is Low(0) - A'
            A is High(1) - A
```

X (SOP) = ![\Sigma  ](img/b943463150bf206fc1b575cced01b669.png "Rendered by QuickLaTeX.com") <sub> m </sub> (1，3，6)
= A’。b’。' c+A ' b . c+A . b . c '

**和的乘积(POS):**
顾名思义，就是和项相乘(AND 运算)而成。这些求和项也被称为“最大项”。最大项用“M”表示，它们是布尔变量的和(或运算)，要么是范式，要么是补形式。

因此，POS 是 maxterms 的乘积，在 POS = ![\Pi  ](img/f5da70c5e432144142d7e43dc7df12ef.png "Rendered by QuickLaTeX.com") <sub> M </sub> (1，2)中表示为:
F，这里，F 是 maxterms 1 和 maxterms 2 的乘积。

例如:

```
A=0, B=1, C=0   Maxterm is A+B'+C
A=1, B=1, C=1   Maxterm is A'+B'+C'  
```

考虑一个函数 X，其真值表如下:

<figure class="table">

| A | B | C | X |
| --- | --- | --- | --- |
| Zero | Zero | Zero | Zero |
| Zero | Zero | one | one |
| Zero | one | Zero | Zero |
| Zero | one | one | one |
| one | Zero | Zero | Zero |
| one | Zero | one | Zero |
| one | one | Zero | one |
| one | one | one | Zero |

当 X 为低(0)时，函数 X 可以通过乘以所有最大项以 POS 形式编写。
在写 POS 时，应遵循以下约定:

```
If variable A is Low(0) - A
            A is High(1) - A'

X (POS) = M(0, 2, 4, 5, 7)  

        = (A+B+C).(A+B'+C).(A'+B+C).(A'+B+C').(A'+B'+C') 
```

**SOP 与 POS 的区别:**

<figure class="table">

| 没有。 | 标准作业程式(standard operating procedure) | 刷卡机 |
| --- | --- | --- |
| 1. | 一种将布尔表达式表示为乘积项之和的方法。 | 一种将布尔表达式表示为和项乘积的方法。 |
| 2. | 标准操作程序使用薄荷糖。最小项是布尔变量的乘积，要么是范式，要么是补形式。 | POS 使用 maxterms。Maxterm 是正规形式或补充形式的布尔变量的和。 |
| 3. | 这是几分钟的总和。最小项表示为“m” | 它是 maxterms 的产物。Maxterms 表示为“M” |
| 4. | 标准操作程序是通过考虑所有输出为高电平(1)的微处理器而形成的 | POS 是通过考虑所有最大项形成的，其输出为低(0) |
| 5. | 在为 SOP 编写 minterms 时，值为 1 的输入被视为变量本身，值为 0 的输入被视为输入的补码。 | 在为 POS 编写 maxterms 时，值为 1 的输入被视为补码，值为 0 的输入被视为变量本身。 |

</figure>

</figure>

</figure>