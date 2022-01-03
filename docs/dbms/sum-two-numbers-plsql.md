# PL/SQL 中两个数之和

> 原文:[https://www.geeksforgeeks.org/sum-two-numbers-plsql/](https://www.geeksforgeeks.org/sum-two-numbers-plsql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。

在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

这里，首先，我们取三个变量 x，y 和 z，并在 x 和 y 中赋值，在两个数字相加后，我们将结果值赋给 z 并打印 z。

示例:

```
Input : 15 25
Output : 40
```

```
Input : 250 400
Output : 650
```

以下是所需的实现:

## 结构化查询语言

```
declare

-- declare variable x, y
-- and z of datatype number
x number(5);            
y number(5);           
z number(7);       

begin

-- Here we Assigning 10 into x
x:=10;                

-- Assigning 20 into x
y:=20;                

-- Assigning sum of x and y into z
z:=x+y;                

-- Print the Result
dbms_output.put_line('Sum is '||z);
end;
/                        
-- Program End
```

**输出:**

```
Sum is 30
```