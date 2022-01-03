# 打印 PL/SQL 中所有‘m’到‘n’之间的质数

> 原文:[https://www . geesforgeks . org/print-all-the-prime-numbers-in-pl-SQL/](https://www.geeksforgeeks.org/print-all-the-prime-numbers-between-m-and-n-in-pl-sql/)

先决条件–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

**问题:**
用 PL/SQL 写一个脚本，显示任意两个正整数之间的所有素数。

**说明:**
这里返回作为输入的任意两个数之间作为上限和下限的所有素数。质数是大于 1 的自然数，不能由两个较小的自然数相乘而成。

在这个实现中，出现在两个极限之间的数的除数被计数，它应该是 2 (1 和数本身)。如果除数为 2，则返回该数。

例如，考虑数字 5。它只有两个除数:1 和数字 5 本身。
因此，它是一个质数。

**示例:**

```
Input: 10  20
Output: 11 13 17 19

Input: 20  30
Output: 23 29  
```

**下面是实现:**

```

DECLARE
--the upper limit and the lower limit are taken as user inputs.
   low number(2);
   high number(2);
   n number(2);
   m number(2);
   c number(20);
BEGIN
   dbms_output.put_line('Enter the lower and higher limit:');
   low:=&low;
   high:=&high;
--The main operation happens in this loop
  for n IN low.. high 
    loop
       c:=0;
       for m IN 1.. n
         loop  
           if mod(n, m)=0 then
             c:=c+1;
            end if;
            end loop;
--the number of divisors for each number in the range is counted and then checked.
            if c<=2 then 
               dbms_output.put_line(n||'\n');
            end if;
         end loop;

END;
```

**输出:**

```
Input: 
Enter the lower and higher limit:1  10
Output: 2
        3
        5
        7 
```