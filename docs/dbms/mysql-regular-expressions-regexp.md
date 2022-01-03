# MySQL |正则表达式(Regexp)

> 原文:[https://www . geesforgeks . org/MySQL-正则表达式-regexp/](https://www.geeksforgeeks.org/mysql-regular-expressions-regexp/)

MySQL 支持另一种基于正则表达式和 REGEXP 运算符的模式匹配操作。

1.  它提供了强大而灵活的模式匹配，可以帮助我们为数据库系统实现强大的搜索工具。
2.  REGEXP 是执行正则表达式模式匹配时使用的运算符。RLIKE 是同义词。
3.  它还支持许多元字符，这些元字符在执行模式匹配时允许更大的灵活性和控制。
4.  反斜杠用作转义字符。只有在使用了双反斜杠的情况下，才会在模式匹配中考虑它。
5.  不区分大小写。

| **图案** | **模式匹配什么** |
| * | 它前面零个或多个字符串实例 |
| + | 它前面的一个或多个字符串实例 |
| 。 | 任何单个字符 |
| ？ | 匹配前面字符串的零个或一个实例。 |
| ^ | caret(^)匹配字符串的开头 |
| $ | 字符串结尾 |
| [abc] | 方括号中列出的任何字符 |
| [^abc] | 方括号中未列出的任何字符 |
| [阿-兹] | 匹配任何大写字母。 |
| [a-z] | 匹配任何小写字母 |
| [0-9] | 匹配从 0 到 9 的任何数字。 |
| [[:<:/> | 匹配单词的开头。 |
| [[:>:]] | 匹配单词的结尾。 |
| [:类:] | 匹配字符类，即[:alpha:]匹配字母，[:space:]匹配空格，[:pi 点:]是匹配标点符号，而[:upper:]是匹配大写字母。 |
| p1&#124;p2&#124;p3 | 交替；匹配任何模式 p1、p2 或 p3 |
| {n} | 前面元素的 n 个实例 |
| {m，n} | 前面元素的 m 到 n 个实例 |

**举例说明:**

*   **Match beginning of string(^):**
    Gives all the names starting with ‘sa’.Example- sam,samarth.

    ```
    SELECT name FROM student_tbl WHERE name REGEXP '^sa';

    ```

*   **Match the end of a string($):**
    Gives all the names ending with ‘on’.Example – norton,merton.

    ```
    SELECT name FROM student_tbl WHERE name REGEXP 'on{content}apos;;

    ```

*   **Match zero or one instance of the strings preceding it(?):**
    Gives all the titles containing ‘com’.Example – comedy , romantic comedy.

    ```
    SELECT title FROM movies_tbl WHERE title REGEXP 'com?'; 

    ```

*   **matches any of the patterns p1, p2, or p3(p1|p2|p3):**
    Gives all the names containing ‘be’ or ‘ae’.Example – Abel, Baer.

    ```
    SELECT name FROM student_tbl WHERE name REGEXP 'be|ae' ;

    ```

*   **Matches any character listed between the square brackets([abc]):**
    Gives all the names containing ‘j’ or ‘z’.Example – Lorentz, Rajs.

    ```
    SELECT name FROM student_tbl WHERE name REGEXP '[jz]' ;

    ```

*   **Matches any lower case letter between ‘a’ to ‘z’- ([a-z]) ([a-z] and (.)):**
    Retrieve all names that contain a letter in the range of ‘b’ and ‘g’, followed by any character, followed by the letter ‘a’.Example – Tobias, sewall.

    匹配任何单个字符(。)

    ```
    SELECT name FROM student_tbl WHERE name REGEXP '[b-g].[a]' ;

    ```

*   **Matches any character not listed between the square brackets.([^abc]):**
    Gives all the names not containing ‘j’ or ‘z’. Example – nerton, sewall.

    ```
    SELECT name FROM student_tbl WHERE name REGEXP '[^jz]' ;

    ```

*   **Matches the end of words[[:>:]]:**
    Gives all the titles ending with character “ack”. Example – Black.

    ```
    SELECT title FROM movies_tbl WHERE REGEXP 'ack[[:>:]]'; 

    ```

*   **Matches the beginning of words[[:<:]]:**
    Gives all the titles starting with character “for”. Example – Forgetting Sarah Marshal.

    ```
    SELECT title FROM movies_tbl WHERE title REGEXP '[[:<:]]for'; 

    ```

*   **匹配字符类[:class:]:**
    ，即[:lower:]-小写字符、[:digit:]-数字字符等。
    给出所有仅包含字母字符的标题。例子——奇怪的事情，复仇者联盟。

    ```
    SELECT title FROM movies_tbl WHERE REGEXP '[:alpha:]' ;

    ```