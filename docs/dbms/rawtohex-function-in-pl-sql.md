# PL/SQL 中的 RAWTOHEX 函数

> 原文:[https://www.geeksforgeeks.org/rawtohex-function-in-pl-sql/](https://www.geeksforgeeks.org/rawtohex-function-in-pl-sql/)

目的是在 [PL/SQL 代码](https://www.geeksforgeeks.org/plsql-introduction/)中使用函数 RAWTOHEX。

**目的:**
这个内置函数有利于将原始值转换为十六进制格式的字符值。

**语法:**

```
RAWTOHEX(x) 
```

其中**x**–以字符串值的形式返回要转换为十六进制值和十六进制等价物的原始值。

这里可能有一个简单的程序来演示函数的用法–

**示例-1:** 将十六进制转换值存储在变量“随机”中。

```
CREATE PROCEDURE TEST_RAW2HEX
IS
   random varchar2(20);
BEGIN
   SELECT RAWTOHEX('JAVA') INTO random FROM dual;
   dbms_output.put_line('random = ' || random);
EXCEPTION
WHEN OTHERS
THEN
   dbms_output.put_line(Exception occurred.)
END TEST_RAW2HEX;
```

创建过程并使用 SQL 脚本运行时–

```
BEGIN
    TEST_RAW2HEX;
END;
```

我们得到的输出为–

```
random = 5859 
```

该函数接受除 **LONG、LONG RAW、CLOB、BLOB、**或 **BFILE** 之外的任何数据类型的参数。

这里我们看到了函数演示过程的另一个例子。

**示例-2:** 将十六进制转换值存储在变量“random _ 1”&“random _ 2”中。

```
CREATE PROCEDURE TEST1_RAW2HEX
IS
random_1 varchar2(12);
random_2 varchar2(12);
BEGIN
   SELECT RAWTOHEX('JAVA') INTO random_1 FROM dual;
   SELECT RAWTOHEX('CPP')  INTO random_2 FROM dual;

   dbms_output.put_line('random_1 = ' || random_1);
   dbms_output.put_line('random_2 = ' || random_2);
END TEST1_RAW2HEX;
```

创建过程并使用 SQL 脚本运行时–

```
BEGIN
    TEST1_RAW2HEX;
END;
```

我们得到的输出为–

```
random_1 = 4A415641
random_2 = 435050 
```