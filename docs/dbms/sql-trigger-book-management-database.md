# SQL 触发器|图书管理数据库

> 原文:[https://www . geesforgeks . org/SQL-trigger-book-management-database/](https://www.geeksforgeeks.org/sql-trigger-book-management-database/)

先决条件–[SQL 触发器|学生数据库](https://www.geeksforgeeks.org/sql-trigger-student-database/)
例如，给定图书馆图书管理数据库模式与学生数据库模式。在这些数据库中，如果任何学生从图书馆借书，那么指定的书的数量应该减少。为此，

*假设模式中有一些数据，*

```
mysql> select * from book_det; 
+-----+-------------+--------+ 
| bid | btitle      | copies | 
+-----+-------------+--------+ 
|   1 | Java        |     10 | 
|   2 | C++         |      5 | 
|   3 | MySql       |     10 | 
|   4 | Oracle DBMS |      5 | 
+-----+-------------+--------+ 
4 rows in set (0.00 sec) 

mysql> select * from book_issue; 
+------+------+--------+ 
| bid  | sid  | btitle | 
+------+------+--------+ 
1 row in set (0.00 sec)
```

为了实现这样的过程，其中如果系统将数据插入 book_issue 数据库，触发器应该自动调用 copy 属性并将它减 1，以便可以保持对 book 的正确跟踪。

**系统触发–**

```
create trigger book_copies_deducts 
after INSERT 
on book_issue 
for each row 
update book_det set copies = copies - 1 where bid = new.bid; 
```

以上触发器将在 book_issue 数据库中执行插入操作时激活，它将更新 book_det 模式设置副本，使当前 book id(bid)减少 1。

**结果–**

```
mysql> insert into book_issue values(1, 100, "Java");
Query OK, 1 row affected (0.09 sec) 

mysql> select * from book_det; 
+-----+-------------+--------+ 
| bid | btitle      | copies | 
+-----+-------------+--------+ 
|   1 | Java        |      9 | 
|   2 | C++         |      5 | 
|   3 | MySql       |     10 | 
|   4 | Oracle DBMS |      5 | 
+-----+-------------+--------+ 
4 rows in set (0.00 sec) 

mysql> select * from book_issue; 
+------+------+--------+ 
| bid  | sid  | btitle | 
+------+------+--------+ 
|    1 |  100 | Java   | 
+------+------+--------+ 
1 row in set (0.00 sec)
```

如上所述，结果表明，一旦插入数据，书籍的副本就会从系统中的书籍模式中推断出来。