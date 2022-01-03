# 在 SQL 中 CHAR vs VARCHAR

> 原文:[https://www.geeksforgeeks.org/char-vs-varchar-in-sql/](https://www.geeksforgeeks.org/char-vs-varchar-in-sql/)

**1。CHAR 数据类型:**
它是 SQL 中的一种数据类型，用于存储指定固定长度的字符串。如果字符串的长度小于设定长度或固定长度，则用额外的空格填充，使其长度等于设定长度。CHAR 数据类型的存储大小为 n 字节(集长)。当我们期望一列中的数据值长度相同时，我们应该使用这种数据类型。

**示例:**
考虑查询:

```
CREATE TABLE Student(Name VARCHAR(30), Gender CHAR(6));
INSERT into Student VALUES('Herry', 'Male');
INSERT into Student VALUES('Mahi', 'Female');
SELECT LENGTH(Gender) FROM Student;
```

**输出:**

```
LENGTH(Gender)
6
6
```

**2。VARCHAR 数据类型:**
它是 SQL 中的一种数据类型，用于存储可变长度的字符串，但不能超过指定的最大设置长度。如果字符串的长度小于设定或固定长度，那么它将按原样存储，而不会用额外的空格填充。VARCHAR 数据类型的存储大小等于输入字符串的实际长度(以字节为单位)。当我们期望列中的数据值是可变长度时，我们应该使用这种数据类型。

**示例:**
考虑查询:

```
CREATE TABLE Student(Name VARCHAR(20), Gender CHAR(6));
INSERT into Student VALUES('Herry', 'Male');
INSERT into Student VALUES('Mahi', 'Female');
SELECT LENGTH(Name) FROM Student;
```

**输出:**

```
LENGTH(Name)
5
4
```

**CHAR 和 VARCHAR 数据类型的区别**

<figure class="table">

| 不，先生。 | 茶 | 可变长字符串 |
| --- | --- | --- |
| 1. | CHAR 数据类型用于存储固定长度的字符串 | VARCHAR 数据类型用于存储可变长度的字符串 |
| 2. | 在 CHAR 中，如果字符串的长度小于设定长度或固定长度，则用额外的内存空间填充。 | 在 VARCHAR 中，如果字符串的长度小于设置或固定长度，那么它将按原样存储，而不会用额外的内存空间填充。 |
| 3. | CHAR 代表“性格” | VARCHAR 代表“可变字符” |
| 4. | CHAR 数据类型的存储大小等于 n 字节，即设置长度 | VARCHAR 数据类型的存储大小等于输入字符串的实际长度(以字节为单位)。 |
| 5. | 当我们期望一列中的数据值长度相同时，我们应该使用 CHAR 数据类型。 | 当我们期望一列中的数据值是可变长度时，我们应该使用 VARCHAR 数据类型。 |
| 6. | CHAR 为每个字符取 1 个字节 | VARCHAR 为每个字符取 1 个字节，并取一些额外字节来保存长度信息 |
| 9. | 比 VARCHAR 性能更好 | 与 CHAR 相比，性能不佳 |

**结论**:当值的长度有变化时，VARCHAR 节省空间，但是 CHAR 在性能方面可能更好。

</figure>