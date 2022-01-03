# 2 地址指令和 1 地址指令的区别

> 原文:[https://www . geesforgeks . org/2 地址指令和 1 地址指令的区别/](https://www.geeksforgeeks.org/difference-between-2-address-instruction-and-1-address-instructions/)

先决条件–[指令格式](https://www.geeksforgeeks.org/computer-organization-instruction-formats-zero-one-two-three-address-instruction/)
**1。双地址指令:**
双地址指令是机器指令的一种格式。它有一个操作码和两个地址字段。一个地址字段是通用的，可以用于目的地或源，另一个地址字段用于源。

![](img/a241dba1918f82014bc943964573580b.png)

**示例:**

```
X = (A + B) x (C + D) 
```

**解决方案:**

```
MOV R1, A      R1 <- M[A]
ADD R1, B      R1 <- R1 + M[B]
MOV R2, C      R2 <- M[C]
ADD R2, D      R2 <- R2 + D
MUL R1, R2     R1 <- R1 x R2
MOV X, R1      M[X] <- R1 
```

**2。单地址指令:**
单地址指令也是机器指令的一种格式。它只有两个字段。一个用于操作码，另一个用于操作数。

![](img/cf7e69c5297d8acd936c0581407f837e.png)

**示例:**

```
X = (A + B) x (C + D) 
```

**解决方案:**

```
LOAD A      AC <- M[A]
ADD B       AC <- AC + M[B]
STORE T     M[T] <- AC
LOAD C      AC <- M[C]
ADD D       AC <- AC + M[D]
MUL T       AC <- AC x M[T]
STORE X     M[X] <- AC  
```

**双地址指令和单地址指令的区别:**

<center>

| 双地址指令 | 一地址指令 |
| --- | --- |
| 它有三个字段。 | 它只有两个字段。 |
| 它有一个操作码字段和两个地址字段。 | 它有一个操作码字段和一个地址字段。 |
| 与单地址相比，它具有较长的指令长度。 | 而它的指令长度较短。 |
| 访问处理器内部的位置比访问内存要慢。 | 访问处理器内部的位置比访问内存更快。 |
| 它通常需要两次内存访问。 | 它通常需要一次内存访问。 |
| 一条指令可能需要三次存储器访问。 | 一条指令只需要一次内存访问。 |
| 它不能完全消除三个内存访问。 | 它完全消除了两次内存访问。 |

</center>