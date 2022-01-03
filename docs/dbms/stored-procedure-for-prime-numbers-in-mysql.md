# MySQL 中质数的存储过程

> 原文:[https://www . geesforgeks . org/MySQL 中质数存储过程/](https://www.geeksforgeeks.org/stored-procedure-for-prime-numbers-in-mysql/)

在本文中，您将看到如何编写存储过程的逻辑来为任何给定的输入生成素数。

**标题:**
给定一个数字 N，使用 MYSQL 中的存储过程打印所有用逗号(，)分隔的质数(< =N)。

**示例-1 :**

```
Input : N = 10
Output : 2, 3, 5, 7

```

**示例-2 :**

```
Input : N = 20
Output : 2, 3, 5, 7, 11, 13, 17, 19

```

**程序:**
演示如何为任何给定输入生成素数的程序。

```
delimiter $
create procedure getPrime(IN n int, OUT result varchar(200))
Begin
declare j, i, flag int;  /* Declare variables */
set j:=2; 
set result:=' '; 
while(j<n) do /* Loop from 2 to n */
set i:=2;
set flag:=0;

while(i<=j) do /* Loop from 2 to j */
if(j%i=0)then
set flag:=flag+1;
end if;
set i:=i+1; /* Increment i */
end while;

if (flag=1) then
set result:=concat(result, j, ', '); 
/* Concat the prime number with ', ' */
end if ;
set j:=j+1; /* Increment j */
end while;

End
$

```

**如何调用过程:**
要调用过程使用了下面给出的查询。

```
call getPrime(20, @result);
select substr(@result, 1, length(@result)-1); /* To remove last character */

```

**输出:**

```
2, 3, 5, 7, 11, 13, 17, 19

```