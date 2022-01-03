# 在 PL/SQL 中反转一个数字

> 原文:[https://www.geeksforgeeks.org/reverese-number-using-pl-sql/](https://www.geeksforgeeks.org/reverese-number-using-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。
在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

**解释:**
举个例子，输入= 12345。

第一步:mod(12345，10)= 5
rev:= 0 * 10+5 = 5
num = floor(12345/10)= 1234

第二步:mod(1234，10)= 4
rev:= 5 * 10+4 = 54
num = floor(1234/10)= 123

第三步:mod(123，10)= 3
rev:= 54 * 10+3 = 543
num = floor(123/10)= 12

第四步:mod(12，10)= 2
rev:= 543 * 10+2 = 5432
num = floor(12/10)= 1

第五步:mod(1，10)= 1
rev:= 5432 * 10+1 = 54321
num = floor(1/10)= 0
第五步，num =0，不满足 while 条件，循环终止。

rev = 54321

更多示例:

```
Input : 123456
Output :654321

```

```
Input :87459
Output :95478

```

以下是所需的实现:

```
SET SERVEROUTPUT ON;
DECLARE
-- declare a number 'num' for reading actual input
-- declare another number 'rev' that would be reverse of num
num NUMBER;
rev NUMBER;

BEGIN
-- & is used to read input from keyboard
num:=#
-- initialize rev to 0
rev:=0;
-- the loop runs until num is greater than 0
WHILE num>0 LOOP
-- mod function is used to find the modulus/ remainder of num when divided by 10

rev:=(rev*10) + mod(num,10);
-- floor function is used to obtain a result which is an integer
num:=floor(num/10);
END LOOP;
DBMS_OUTPUT.PUT_LINE('Reverse of the number is: ' || rev);
END;
/                        

-- Program End
```

**输出:**

```
Enter value for num : 157439
Reverse of the number is: 934751

```