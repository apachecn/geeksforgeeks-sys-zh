# 卡珊德拉中的用户定义函数

> 原文:[https://www . geesforgeks . org/user-defined-function in-Cassandra/](https://www.geeksforgeeks.org/user-defined-function-in-cassandra/)

在本文中，我们将讨论如何在 [Cassandra](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/) 中创建用户定义函数。另外，我们将看看如何修改它。让我们看看。

首先，我们将创建一个**用户定义函数(UDF)** 。
让我们举一个例子，我们将创建 Max_value UDF，我们将通过简单地在 UDF 传递值来计算最大值。让我们看看。

**创建 UDF:最大值–**

```
CREATE FUNCTION Max_value(value1 int, value2 int)
CALLED ON NULL INPUT
RETURNS int
LANGUAGE java
AS $return Math.max(value1, value2);$; 
```

现在，为了传递该值作为输入，我们将创建一个简单的表，即 UDF 函数测试，其中 function_id、num1 和 num2 是字段值。
我们来看看。

```
CREATE TABLE UDF_Function_test 
    (
    function_id int,
    num1 int,
    num2 int,
    PRIMARY KEY(function_id)
    ); 
```

现在，我们将在这里插入一些数据，我们将在 UDF 函数中使用这些数据来计算最大值，其中 function_id 将在 101 到 104 的范围内。
我们来看看。

```
INSERT INTO UDF_Function_test(function_id, num1, num2) 
VALUES(101, 400, 600);

INSERT INTO UDF_Function_test(function_id, num1, num2) 
VALUES(102, 500, 400);

INSERT INTO UDF_Function_test(function_id, num2) 
VALUES(103, 900);

INSERT INTO UDF_Function_test(function_id, num1) 
VALUES(104, 500); 
```

让我们验证结果并计算最大值。

```
SELECT function_id, num1, num2, Max_value(num1, num2) 
FROM UDF_Function_test 
WHERE function_id IN(101, 102, 103, 104); 
```

**输出:**

<figure class="table">

| 函数 id | num1 | num2 | udf.Max_value(编号 1、编号 2) |
| --- | --- | --- | --- |
| One hundred and one | four hundred | Six hundred | Six hundred |
| One hundred and two | Five hundred | four hundred | Five hundred |
| One hundred and three | 空 | Nine hundred | 空 |
| One hundred and four | Five hundred | 空 | 空 |

正如我们在输出表中看到的，如果一个输入值为空，那么它将返回空值，因为我们使用的子句在空输入时返回空值。

现在，我们将尝试将在空输入时返回空的子句更改为在空输入时调用，并将看到结果。
我们来看看。

```
CREATE OR REPLACE FUNCTION Max_value(value1 int, value2 int)
CALLED ON NULL INPUT 
RETURNS int
LANGUAGE java
AS 'return Math.max(value1, value2);'; 
```

当我们试图执行时，它会给出以下错误。
我们来看看。

```
InvalidRequest: code=2200 [Invalid query] 
message="Function udf.Max_value : 
(int, int) -> int can only be replaced with CALLED ON NULL INPUT" 
```

我们将看到，一旦我们选择了空输入返回空，就不可能改变它。要修改首先我们需要删除，然后再次创建 UDF 函数。让我们来看看。

```
DROP FUNCTION Max_value; 
```

**再造修改 UDF–**

```
CREATE OR REPLACE FUNCTION Max_value(value1 int, value2 int)
CALLED ON NULL INPUT 
RETURNS int
LANGUAGE java
AS 'return Math.max(value1, value2);'; 
```

现在，让我们执行并看看 UDF 的结果。

```
SELECT function_id, num1, num2, Max_value(num1, num2) 
FROM UDF_Function_test WHERE function_id IN(1, 2, 3); 
```

这里我们可以看到错误是预期的，因为在我们的 UDF 没有空检查。

```
FunctionFailure: code=1400 [User Defined Function failure] 
message="execution of 'udf.Max_value[int, int]' 
failed: java.lang.NullPointerException" 
```

</figure>