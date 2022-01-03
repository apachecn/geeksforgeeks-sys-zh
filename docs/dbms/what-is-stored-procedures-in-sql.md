# 什么是 SQL 中的存储过程？

> 原文:[https://www . geesforgeks . org/什么是 sql 中的存储过程/](https://www.geeksforgeeks.org/what-is-stored-procedures-in-sql/)

**存储过程**是为了在数据库上执行一个或多个 DML 操作而创建的。它只不过是一组 SQL 语句，接受一些参数形式的输入，执行一些任务，可能返回值，也可能不返回值。

**语法:**创建过程

```
CREATE or REPLACE PROCEDURE name(parameters)
IS
variables;
BEGIN
//statements;
END;
```

最重要的部分是参数。参数用于向过程传递值。有 3 种不同类型的参数，如下所示:

1.  **输入:**
    这是程序的默认参数。它总是从调用程序接收值。
2.  **OUT:**
    该参数始终将值发送给调用程序。
3.  **输入输出:**
    该参数执行两种操作。它从调用程序接收值并将值发送到调用程序。

**示例:**
想象一个名为的表，其中 emp_table 存储在数据库中。我们正在编写一个程序，将员工的工资更新为 1000。

```
CREATE or REPLACE PROCEDURE INC_SAL(eno IN NUMBER, up_sal OUT NUMBER)
IS
BEGIN
UPDATE emp_table SET salary = salary+1000 WHERE emp_no = eno;
COMMIT;
SELECT sal INTO up_sal FROM emp_table WHERE emp_no = eno;
END; 
```

*   声明一个变量来存储来自过程的值:

```
VARIABLE v NUMBER;
```

*   程序的执行:

```
EXECUTE INC_SAL(1002, :v);
```

*   要检查更新的薪资，请使用 SELECT 语句:

```
 SELECT * FROM emp_table WHERE emp_no = 1002;
```

*   或使用打印语句:

```
PRINT :v
```