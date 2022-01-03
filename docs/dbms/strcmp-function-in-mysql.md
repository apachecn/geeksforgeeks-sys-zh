# MySQL 中的 STRCMP()函数

> 原文:[https://www.geeksforgeeks.org/strcmp-function-in-mysql/](https://www.geeksforgeeks.org/strcmp-function-in-mysql/)

**MySQL 中的 STRCMP** ()函数用于比较两个字符串。如果两个字符串相同，则返回 0，如果根据定义的顺序，第一个参数小于第二个参数，则返回-1，当第二个参数小于第一个参数时，则返回 1。

**语法:** STRCMP(Str1，Str2)

**参数:**该方法接受如下描述的双参数:

*   **str1:** is the first string for comparison.
*   **str2:** is the second string for comparison.

**返回:**可以给出四种值–

*   如果 string1 = string2，此函数返回 0
*   如果 string1 < string2，此函数返回-1
*   如果 string1 > string2，此函数返回 1
*   如果任意一个或两个字符串都为空，此函数将返回空值。

**示例-1 :** STRCMP()函数比较两个相等的字符串。由于两个给定的字符串相等，它将返回 0。

```
Select STRCMP('Geeks', 'Geeks') As 'Cmp_Value'
```

**输出:**

T5】

| CMP _ Value |
| --- |
| 0 |

**示例-2 :** STRCMP()函数用于在第二个字符串小于第一个字符串时比较两个字符串。这里，返回值将是 1。

```
Select STRCMP('Geeks', 'Geek') As 'Cmp_Value'
```

**输出:**

T5】

| CMP _ Value |
| --- |
| 1 |

**示例-3 :** STRCMP()函数在第二个字符串大于第一个字符串时比较两个字符串。由于第二个字符串大于第一个字符串，结果将为-1。

```
Select STRCMP('Geek', 'Geeks') As 'Cmp_Value'
```

**输出:**

| CMP _ Value |
| --- |
| -1 |

**示例-4 :** STRCMP()函数在至少一个字符串为空时比较两个字符串。

```
Select STRCMP('Geek', NULL) As 'Cmp_Value'
```

**输出:**

T5】

| CMP _ Value |
| --- |
| NULL |

**示例-5 :** STRCMP()函数也可以用于列数据。为了演示，创建一个名为 StudentDetails 的表。

```
CREATE TABLE StudentDetails(

    Student_id INT AUTO_INCREMENT,  
    First_name VARCHAR(100) NOT NULL,
    Last_name VARCHAR(100) NOT NULL,
    Student_Class VARCHAR(20) NOT NULL,
    TotalExamGiven INT   NOT NULL,
    PRIMARY KEY(Student_id )
```

将数据插入表中:

```
INSERT INTO  
    StudentDetails(First_name, Last_name, Class, TotalExamGiven )

VALUES
    ('Sayan', 'Jana', 'IX', 8 ),
    ('Nitin', 'Sharma', 'X',  5 ),
    ('Aniket', 'Srivastava', 'XI', 6 ),
    ('Abdur', 'Ali', 'X',  7 ),
    ('Riya', 'Malakar', 'IX', 4 ),
    ('Jony', 'Patel', 'X', 10 ),
    ('Deepak', 'Saini',  'X',  7 ),
    ('Ankana', 'Biswas',  'XII', 5 ),
    ('Shreya', 'Majhi', 'X',  8 ) ;
```

要验证是否使用了以下命令，如下所示。

```
SELECT * FROM StudentDetails;
```

**输出:**

【Jana】 IX

| 学生标识 | 名字 | 姓氏 | 班级 | 全面检查 |
| --- | --- | --- | --- | --- |
| 【1】 | 【say an】 |
| --- | --- |
|  |
| --- |
| 【4】 |
| --- |
| 【6】 | 【jony】 | 【Patel】 |  |  |
| --- | --- | --- | --- | --- |

现在，我们将使用 STRCMP 函数来比较名列和姓列。

```
SELECT First_Name, Last_Name,
STRCMP(First_Name, Last_Name) AS Cmp_Value 
FROM StudentDetails;
```

**输出:**

【Nitin】【t】

| 名字 | 姓氏 | CMP _ value |
| --- | --- | --- |
| 【say an】 | 【Jana】 |
| --- | --- |
| 【Sharma】【t】 安康〔t59〕 | 【biswas】 | -1】 |
| --- | --- | --- |
| 【shreya】 |  | 【1】 |
| --- | --- | --- |