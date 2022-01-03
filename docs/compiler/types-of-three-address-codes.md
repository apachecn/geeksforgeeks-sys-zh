# 三地址码类型

> 原文:[https://www.geeksforgeeks.org/types-of-three-address-codes/](https://www.geeksforgeeks.org/types-of-three-address-codes/)

[三地址码](https://www.geeksforgeeks.org/three-address-code-compiler/)是一般形式的语句序列 **A := B op C** ，其中 A、B、C 或者是程序员定义的名称、常量，或者是编译器生成的临时名称； **op** 代表应用于 A、B 上的操作。简单地说，一行中最多有三个地址的代码称为三个地址代码。

**例:**

```
(a+b)*(a+b+c) 
```

以上表达式的三个地址码为:

```
t1=a+b
t2=t1+c
t3=t1*t2
```

在编译器设计中，最流行的中间代码表示是三地址代码。它被全球接受，使用最广泛。有很多三地址语句。所有复杂的三地址语句通常是简单的三地址语句的组合。

这些语句分为以下七类，可以称为三地址语句的构造块-

<figure class="table">

| 声明 | 意义 |
| X = Y 运算 Z | 二元运算 |
| X= op Z | 一元运算 |
| X = Y | 分配 |
| 如果 X(相对运算)Y 转到 L | 条件转到 |
| 转到 L | 无条件转到 |
| A[i] = X
Y= A[i] | 数组索引 |
| P = addr X
Y = *P
*P = Z | 指针操作 |

现在，通过使用上述语句，让我们转换三地址代码中一些流行的高级结构。

**1。While 语句–**

```
while E do S
```

三地址编码:

```
L:if(E==0) goto L1
  S
  goto L
L1:end
```

**2。声明–**

```
for(E1;E2;E3) do S
```

三地址编码:

```
  E1
L:if(E2) goto L1
  goto L2
L1:S
  E3
  goto L
L2:end
```

**3。开关声明–**

```
switch(E){
case 1: S1
        break;
case 2: S2
        break;
default: S3
}
```

三地址编码:

```
  t=E
  goto test
L1:S1
  goto Last
L2:S2
   goto Last
L3:S3
   goto Last
test: if(E==1) goto L1
      if(E==2) goto L2
      goto L3
Last:end
```

因此，我们可以看到，通过使用七条语句，我们可以将语句从高级语言复制到地址码中。

</figure>