# PL/SQL 中一个数的阶乘

> 原文:[https://www.geeksforgeeks.org/factorial-number-plsql/](https://www.geeksforgeeks.org/factorial-number-plsql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。
在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

这里，首先，我们取三个变量 num、fact 和 temp，并在 num 变量中赋值(即我们想要哪个数字的阶乘)。
然后我们把事实变量赋值为 1 之后。

示例:

```
Input : 4
Output : 24

```

```
Input : 6
Output : 720

```

以下是所需的实现:

```
declare

-- declare variable num , fact
-- and temp of datatype number
 num number := 6;             
 fact number := 1;            
 temp number;        

begin

temp :=num;

-- here we check condition 
-- with the help of while loop
while( temp>0 )             
loop
fact := fact*temp;
temp := temp-1;

end loop;

dbms_output.put_line('factorial of '|| num || ' is ' || fact);

 end; 

-- Program End
```

**输出:**

```
factorial of 6 is 720.

```