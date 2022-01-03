# MySQL 中不同类型的程序

> 原文:[https://www . geesforgeks . org/不同类型的 mysql 中的过程/](https://www.geeksforgeeks.org/different-types-of-procedures-in-mysql/)

一个**程序**是一个常规脚本语言的子程序(像子程序一样)，存储在数据库中。在 MySQL 的情况下，过程用 MySQL 编写，并存储在 MySQL 数据库/服务器中。MySQL 过程有一个名称、一个参数列表和一条或多条 SQL 语句。

有四种不同类型的 MySQL 过程:

**1。没有参数的过程:**
没有参数的过程不接受任何输入或间接转换输出。它只是用过程名后跟()(不带任何参数)来调用。它用于简单的查询。

**例:**
考虑两个表作者和书:

```
create table author (author_id integer primary key, 
                            authorName varchar(30), 
                            email varchar (25), gender varchar (6));

create table book (BookId integer not null unique, 
                        ISBN integer primary key, 
                       book_name varchar (30) not null, 
                        author integer, ed_num integer, 
                      price integer, pages integer, 
         foreign key (author) references author (author_id) on delete cascade);
```

向其中插入值:

```
insert into author values 
              (1, "Kraig Muller", "Wordnewton@gmail.com", "Male");
insert into author values
              (2, "Karrie Nicolette", "karrie23@gmail.com", "Female");
insert into book values
              (1, 001, "Glimpses of the past", 1, 1, 650, 396);
insert into book values
              (2, 002, "Beyond The Horizons of Venus", 1, 1, 650, 396);
insert into book values
              (3, 003, "Ultrasonic Aquaculture", 2, 1, 799, 500);
insert into book values
              (4, 004, "Cyrogenic Engines", 2, 1, 499, 330); 
```

显示所有书籍的程序(无参数):

```
delimiter //
create procedure display_book() 
                      -> begin 
                      -> select *from book; 
                      -> end //
call display_book(); //
```

**输出:**

```
+--------+------+------------------------------+--------+--------+-------+-------+
| BookId | ISBN | book_name                    | author | ed_num | price | pages |
+--------+------+------------------------------+--------+--------+-------+-------+
|      1 |    1 | Glimpses of the past         |      1 |      1 |   650 |   396 |
|      2 |    2 | Beyond The Horizons of Venus |      1 |      1 |   650 |   396 |
|      3 |    3 | Ultrasonic Aquaculture       |      2 |      1 |   799 |   500 |
|      4 |    4 | Cyrogenic Engines            |      2 |      1 |   499 |   330 |
+--------+------+------------------------------+--------+--------+-------+-------+
4 rows in set (0.0012 sec)

```

**2。带输入参数的过程:**
输入参数用于将参数作为输入，如属性。当我们在过程中定义一个输入参数时，调用程序必须向存储过程传递一个参数。此外，输入参数的值受到保护。这意味着即使在过程内部更改了 IN 参数的值，它的原始值在过程结束后仍会保留(如按值传递)。换句话说，该过程仅适用于输入参数的副本。

**例:**
以图书的 ISBN 及其新价格为输入更新图书价格的程序:(考虑上表)

```
delimiter //
create procedure update_price (IN temp_ISBN varchar(10), IN new_price integer)
               -> begin
               -> update book set price=new_price where ISBN=temp_ISBN;
               -> end; //
call update_price(001, 600); //

```

我们把书号为‘001’(过去的一瞥)的书的价格改成了 600(从默认价格 650)。

**输出:**

```
delimiter ;
select *from book;
+--------+------+------------------------------+--------+--------+-------+-------+
| BookId | ISBN | book_name                    | author | ed_num | price | pages |
+--------+------+------------------------------+--------+--------+-------+-------+
|      1 |    1 | Glimpses of the past         |      1 |      1 |   600 |   396 |
|      2 |    2 | Beyond The Horizons of Venus |      1 |      1 |   650 |   396 |
|      3 |    3 | Ultrasonic Aquaculture       |      2 |      1 |   799 |   500 |
|      4 |    4 | Cyrogenic Engines            |      2 |      1 |   499 |   330 |
+--------+------+------------------------------+--------+--------+-------+-------+
4 rows in set (0.0013 sec)
```

**3。带有输出参数的过程:**
输出参数用于像选择操作符一样传递参数作为输出或显示，但是隐式的(通过设定值)。OUT 参数的值可以在过程内部更改，并且它的新值会传递回调用程序。过程启动时无法访问输出参数的初始值。

**示例:**
用输出参数显示所有书籍中最高价格的程序:

```
delimiter //
create procedure disp_max(OUT highestprice integer)
                 -> begin
                 -> select max(price) into highestprice from book;
                 -> end; //
call disp_max(@M); //
select @M; 
```

**输出:**
我们图书数据库最高价是 ISBN 003(超声波水产养殖)的书，价格 799，显示出来。

```
+-----+
| @M  |
+-----+
| 799 |
+-----+
1 row in set (0.0005 sec) 
```

**4。带输入输出参数的程序:**
输入输出参数是输入输出参数的组合。这意味着调用程序可以传递参数，存储过程可以修改 INOUT 参数，并将新值传递回调用程序。

**示例:**
采用性别类型输入(此处为“男性”/“女性”)的程序，输入/输出参数反映了属于该性别类别/类型的作者数量:

```
delimiter //
create procedure disp_gender(INOUT mfgender integer, IN emp_gender varchar(6))  
                     -> begin 
                     -> select COUNT(gender) 
                         INTO mfgender FROM author where gender = emp_gender;   
                     -> end; //
delimiter ;
call disp_gender(@M, "Male");
select @M;
call disp_gender(@F, "Female");
select @F; 
```

**输出:**
根据表格作者的插入，我们有两个作者，一个是男性，一个是女性。因此，一名男性作者的产出为 1，一名女性作者的产出为 1。

```
+----+
| @M |
+----+
|  1 |
+----+
1 row in set (0.0004 sec)
+----+
| @F |
+----+
|  1 |
+----+
1 row in set (0.0005 sec)

```