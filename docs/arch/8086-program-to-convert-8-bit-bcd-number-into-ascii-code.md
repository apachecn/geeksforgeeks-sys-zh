# 8086 程序将 8 位 BCD 号转换为 ASCII 码

> 原文:[https://www . geesforgeks . org/8086-程序-转换-8 位 BCD-number-to-ascii-code/](https://www.geeksforgeeks.org/8086-program-to-convert-8-bit-bcd-number-into-ascii-code/)

**问题–**在 8086 微处理器中编写汇编语言程序，将 8 位 BCD 数转换为各自的 ACSII 代码。

**假设–**
程序起始地址:400
输入内存位置:2000
输出内存位置:3000

**示例:**

```
Input: 
DATA: 98H in memory location 2000

Output:
DATA: 38H in memory location 3000 and 
      39H in memory location 3001 
```

**算法–**

1.  将存储单元 2000 的内容载入寄存器 a1

2.  将寄存器 a1 的内容复制到寄存器 AH 中

3.  用 0F
    对寄存器 A1 执行“与”运算
4.  将 04 分配给 CL 寄存器

5.  使用 CL
    执行 SHR 指令，移动 AH 的内容
6.  用 3030
    对寄存器 AX 执行或运算
7.  将 AX 的内容存储在内存位置 3000

**程序–**

<figure class="table">

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| four hundred | MOV AL，[2000 年] | AL |
| Four hundred and four | 莫夫啊，阿尔 | 啊 |
| Four hundred and six | 和 A1，0F | 铝 |
| Four hundred and eight | MOV CL，04 年 | CL |
| 40A | SHR 啊，CL | 将 AH 内容右移 4 位(CL 的值) |
| 40C | 或 AX，3030 | AX |
| 40F | MOV [3000]，AX | [3000] |
| Four hundred and thirteen | HLT | 停止执行 |

**解释–**

1.  **MOV AL，[2000]:** 在 AL 中加载存储单元 2000 的内容

2.  **MOV AH，AL:** 在 AH 中复制 AL 的内容

3.  **和 a1，0F:** 用 0F
    对 a1 进行 AND 运算
4.  **MOV CL，04** 将 04 分配给 CL 寄存器

5.  **SHR AH，CL:** 将 AH 寄存器的内容右移 4 位，即 CL 寄存器的值

6.  **OR AX，3030:** 用 3030
    对 AX 做 OR 运算
7.  **MOV【3000】，AX:** 将 AX 寄存器对的内容存储在 3000 内存地址

8.  **HLT:** 停止执行程序

</figure>