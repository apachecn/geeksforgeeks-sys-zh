# MySQL 中的 DATE()

> 原文:[https://www.geeksforgeeks.org/date-in-mysql/](https://www.geeksforgeeks.org/date-in-mysql/)

**DATE()** 函数用于从 DateTime 表达式中提取日期部分。这个函数是 MySQL 中的一个内置函数。MySQL 中的 DATE()函数可以用来知道给定日期或 DateTime 的日期。DATE()函数以日期值作为参数，并返回日期。日期参数表示有效的日期或日期时间。

**语法:**

```
select date('Expression'); 

```

*   **Parameter:** It only accepts one parameter.
*   **Expression:** indicates the date/date time value.
*   **Return value:** Returns the date, or null if the expression is not a date.

以下是 DATE()函数的一些常见示例或用法:

*   **示例-1:** 从给定日期提取日期。

    ```
    Select DATE('2020-06-23'); 
    ```

    **输出:**

    ```
    2020-06-23 
    ```

*   **示例-2:** 从给定的日期时间中提取日期。

    ```
    Select DATE("2020-06-23 10:34:29"); 
    ```

    **输出:**

    ```
    2020-06-23 
    ```

*   **示例-3:** 从给定日期提取日期。

    ```
    SELECT DATE("The date is 2020-06-23"); 
    ```

    **输出:**

    ```
    NULL 
    ```