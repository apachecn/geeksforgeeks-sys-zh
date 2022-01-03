# 8085 程序查找出现一次的元素

> 原文:[https://www . geesforgeks . org/8085-程序查找出现一次的元素/](https://www.geeksforgeeks.org/8085-program-to-find-the-element-that-appears-once/)

先决条件–[找到每隔一个元素出现两次的数组中出现一次的元素](https://www.geeksforgeeks.org/find-element-appears-array-every-element-appears-twice/)
**问题–**给定 11 个数字，编写一个汇编语言程序，找到出现一次的元素，其中 5 个数字出现两次，一个元素出现一次。

**示例:**

```
Input : [01H, 02H, 09H, 01H, 01H, 02H, 0AH, 01H, 09H, 03H, 03H]
Output : 0AH
Every number appears even number of times, except 0AH which appears only once.

```

**算法:**
使用异或。
所有元素的异或将给出出现一次的数字。这是因为一个数与自身的异或是 0，一个数与 0 的异或是数本身。

```
^ => XOR

res = 01H ^ 02H ^ 09H ^ 01H ^ 01H ^ 02H ^ 0AH ^ 01H ^ 09H ^ 03H ^ 03H

Since XOR is associative and commutative :
res = 0AH ^ (01H ^ 01H) ^ (01H ^ 01H) ^ (02H ^ 02H) ^ (03H ^ 03H) ^ (09H ^ 09H) 
    = 0AH ^ 0 ^ 0 ^ 0 ^ 0 ^ 0
    = 0AH ^ 0
    = 0AH

```

**步骤:**

1.  载入 HL 寄存器对中第一个数字的地址
2.  用 0BH 初始化寄存器 C，因为我们必须遍历 11 个元素。它就像一个计数器
3.  用 0 初始化累加器
4.  用累加器对存储在 HL 寄存器中的地址上的值进行异或运算，并增加 HL 寄存器中的地址
5.  对其余 10 个元素重复步骤 4
6.  将累加器的值存储在 201DH 中(任意)

201DH 包含答案。

<center>

| 地址 | 标签 | 记忆的 |
| 2000 小时 |  | LXI H，2012H |
| 2001H |  |  |
| 2002H |  |  |
| 2003H |  | MVI A， 00H |
| 2004H |  |  |
| 2005H |  | MVI C， 0BH |
| 2006H |  |  |
| 2007H | 环 | 莫夫 b，m |
| 2008H |  | XRA B |
| 2009H |  | INX H(消歧义) |
| 200AH |  | DCR C(消歧义) |
| 200BH |  | JNZ 回圈 |
| 200CH |  |  |
| 200DH |  |  |
| 200EH |  | 是 201DH |
| 200FH |  |  |
| 2010H |  |  |
| 2011H |  | HLT |

</center>