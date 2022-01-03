# SQL | PL/SQL 中函数和存储过程的区别

> 原文:[https://www . geesforgeks . org/SQL-函数和存储过程的区别-in-pl-sql/](https://www.geeksforgeeks.org/sql-difference-between-functions-and-stored-procedures-in-pl-sql/)

**先决条件:**

*   [PL/SQL 中的程序](https://www.geeksforgeeks.org/sql-procedures/)
*   [PL/SQL 中的函数。](https://www.geeksforgeeks.org/functions-in-plsql/)

## PL/SQL 中函数和存储过程的区别

存储过程和函数之间的区别(用户定义函数(UDF)):

**1。SP** *可能会也可能不会*返回值，但是 **UDF** **必须**返回值。函数的 return 语句将控制权返回给调用程序，并返回函数的结果。
**示例:**

```
SP ->
create or replace procedure GEEKS(x int) 
is
y int;
begin
.....

UDF->
FUNCTION GEEKS(x int)  
/*return statement so we must return value in function */  
RETURN int             
IS  
  y int;  
BEGIN 
.....
```

**2。SP** 可以有*输入/输出*参数，但是 **UDF** **只有**有输入参数。
**示例:**

```
 SP ->
 CREATE OR REPLACE PROCEDURE Factorial(x IN NUMBER, result OUT NUMBER)
 is
 begin
 ....

UDF ->
FUNCTION Factorial(x IN NUMBER) /* only input parameter */ 
return  NUMBER
is
result NUMBER;
begin
.....
```

**3。**我们可以从 **SP** 调用 **UDF** ，但是**不能从函数调用 **SP** 。
**示例:****

```
Calling UDF cal() inside SP square() but reverse is not possible.

set serveroutput on;
declare
a int;
c int;

function cal(temp  int)
return int
as 
ans int;
begin
ans:=temp* temp;
return ans;
end;

procedure square(x in int, ans out int) 
is
begin
dbms_output.put_line('calling function in procedure');
ans:= cal(x);
end;

begin
a:=6;
square(a, c);
dbms_output.put_line('the answer is '|| c);
end;

OUTPUT: 
calling function in procedure
the answer is 36
```

**4。**我们**不能在像 SELECT、INSERT、UPDATE、DELETE、MERGE 等 SQL 语句中使用 **SP** 。但是我们可以和 UDF 一起使用。**

**5。**我们可以在 SP 中使用 try-catch 异常处理，但是我们**不能在 **UDF** 中这样做。**

**6。**我们可以在 **SP** 使用交易，但在 **UDF** 则不可以。

**7。**我们可以考虑 **UDF** 作为一个表达，但是在 **SP 中是不可能的。**