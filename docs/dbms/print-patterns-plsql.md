# 打印 PL/SQL 中的图案

> 原文:[https://www.geeksforgeeks.org/print-patterns-plsql/](https://www.geeksforgeeks.org/print-patterns-plsql/)

你已经给了一个数字 n，然后你必须打印一个数字的直角金字塔*
示例:

```
Input : 3
Output :
*
**
***

Input : 7
Output :
*
**
***
****
*****
******
*******
```

## C

```
DECLARE
  -- declare variable n,
  --I AND J of datatype number
  N NUMBER := 7;
  I NUMBER;
  J NUMBER;
BEGIN
  -- loop from 1 to n
  FOR I IN 1..N
  LOOP
    FOR J IN 1..I
    LOOP
      DBMS_OUTPUT.PUT('*') ; -- printing *
    END LOOP;
    DBMS_OUTPUT.NEW_LINE; -- for new line
  END LOOP;
END;
--Program End
```

输出:

```
*
**
***
****
*****
******
*******
```