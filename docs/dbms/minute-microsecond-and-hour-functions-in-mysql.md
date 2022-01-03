# MySQL 中的 MINUTE()、微秒()和小时()函数

> 原文:[https://www . geesforgeks . org/分钟-微秒-小时-函数-in-mysql/](https://www.geeksforgeeks.org/minute-microsecond-and-hour-functions-in-mysql/)

**1。MINUTE():**
MySQL MINUTE()函数用于返回日期时间值的分钟部分。它可以在 0 到 59 之间。当 datetime 传入 minute()函数时，它将返回 MINUTE 值。

**语法–**

```
MINUTE(datetime) 
```

**参数–**
它取参数一个日界线值。

**Return–**
返回 0 到 59 之间的分钟数值。

**示例-1:**

```
SELECT MINUTE ("2020-06-29 10:34:00"); 
```

**输出–**

```
34
```

**示例-2:**

```
SELECT MINUTE("4:10:17");
```

**输出–**

```
10
```

**2。微秒()–**
MySQL 函数微秒()用于返回日期时间值的微秒部分。它可以在 0 到 999999 之间。当日期时间在 MINUTE()函数中传递时，它将返回微秒值。

**语法[-**

```
MICROSECOND(datetime)
```

**参数–**
日期时间值。

**返回–**
返回一个整数

**示例-1:**

```
SELECT MICROSECOND("2010-07-20 06:24:10.967423"); 
```

**输出–**

```
967423
```

**示例-2:**

```
SELECT MICROSECOND("2005-10-10 12:24:17.000007"); 
```

**输出–**

```
7
```

**3。HOUR():**
MySQL 函数 HOUR()返回给定日期时间的小时部分。它可以在 0 到 838 之间。

**语法–**

```
HOUR(datetime) 
```

**参数–**
日期时间值。

**返回–**
返回一个整数值。

**示例-1:**

```
SELECT HOUR("12:24:17.000007"); 
```

**输出–**

```
12
```

**示例-2:**

```
SELECT MICROSECOND(""838:59:59""); 
```

**输出–**

```
838
```

**支持的 MySQL 版本:**

*   MySQL 4.0
*   MySQL 4.1
*   MySQL 5.0
*   MySQL 5.1
*   MySQL 5.5
*   MySQL 5.6
*   MySQL 5.7