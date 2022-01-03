# 不同类型的 MySQL 触发器(举例)

> 原文:[https://www . geeksforgeeks . org/不同类型的 mysql 触发器示例/](https://www.geeksforgeeks.org/different-types-of-mysql-triggers-with-examples/)

MySQL **触发器**是一个存储的程序(带有查询)，它被自动执行以响应特定的事件，例如表中发生的插入、更新或删除。

MySQL 中有 6 种不同类型的触发器:

**1。在更新触发器之前:**
顾名思义，它是在调用更新之前启动的触发器。如果我们编写一个 update 语句，那么触发器的操作将在实现更新之前执行。

**例:**
考虑表格:

```
create table customer (acc_no integer primary key, 
                                 cust_name varchar(20), 
                                  avail_balance decimal);
create table mini_statement (acc_no integer, 
                              avail_balance decimal, 
                     foreign key(acc_no) references customer(acc_no) on delete cascade); 
```

在其中插入值:

```
insert into customer values (1000, "Fanny", 7000);
insert into customer values (1001, "Peter", 12000); 
```

在更新客户记录/表中的任何记录之前，将(旧的)值插入 mini_statement 记录(包括作为参数的帐号和可用余额)的触发器:

```
delimiter //
create trigger update_cus
      -> before update on customer
      -> for each row
      -> begin
      -> insert into mini_statement values (old.acc_no, old.avail_balance);
      -> end; // 
```

更新以调用触发器:

```
delimiter;
update customer set avail_balance = avail_balance + 3000 where acc_no = 1001;
update customer set avail_balance = avail_balance + 3000 where acc_no = 1000; 
```

**输出:**

```
select *from mini_statement;
+--------+---------------+
| acc_no | avail_balance |
+--------+---------------+
|   1001 |         12000 |
|   1000 |          7000 |
+--------+---------------+
2 rows in set (0.0007 sec) 
```

**2。更新触发器后:**
顾名思义，在更新发生后调用此触发器。(即，它在执行 update 语句后实现。).

**示例:**
我们创建另一个表:

```
create table micro_statement (acc_no integer, 
                                  avail_balance decimal, 
            foreign key(acc_no) references customer(acc_no) on delete cascade); 
```

向客户插入另一个价值:

```
insert into customer values (1002, "Janitor", 4500);
Query OK, 1 row affected (0.0786 sec) 
```

发生更新后，触发将账号和可用余额的(新)值插入到微对帐单记录中:

```
delimiter //
create trigger update_after
       -> after update on customer
       -> for each row
       -> begin
       -> insert into micro_statement values(new.acc_no, new.avail_balance);
       -> end; // 
```

更新以调用触发器:

```
delimiter ;
update customer set avail_balance = avail_balance + 1500 where acc_no = 1002; 
```

**输出:**

```
select *from micro_statement;
+--------+---------------+
| acc_no | avail_balance |
+--------+---------------+
|   1002 |          6000 |
+--------+---------------+
1 row in set (0.0007 sec) 
```

**3。在插入触发器之前:**
顾名思义，这个触发器在插入之前或者在执行插入语句之前被调用。

**例:**
考虑表格:

```
create table contacts (contact_id INT (11) NOT NULL AUTO_INCREMENT, 
                              last_name VARCHAR (30) NOT NULL, first_name VARCHAR (25),
             ->birthday DATE, created_date DATE, 
                            created_by VARCHAR(30), 
                            CONSTRAINT contacts_pk PRIMARY KEY (contact_id)); 
```

在插入之前，触发将姓名、生日和创建日期/用户等联系信息插入表格联系人:

```
delimiter //
create trigger contacts_before_insert
            -> before insert
            -> on contacts for each row
            -> begin
            ->    DECLARE vUser varchar(50);
            ->
            ->    -- Find username of person performing INSERT into table
            ->    select USER() into vUser;
            ->
            ->    -- Update create_date field to current system date
            ->    SET NEW.created_date = SYSDATE();
            ->
            ->    -- Update created_by field to the username of the person performing the INSERT
            ->    SET NEW.created_by = vUser;
            -> end; // 
```

进行插入以调用触发器:

```
delimiter;
insert into contacts values (1, "Newton", "Enigma", 
                             str_to_date ("19-08-1999", "%d-%m-%Y"), 
                             str_to_date ("17-03-2018", "%d-%m-%Y"), "xyz"); 
```

**输出:**

```
select *from contacts;
+------------+-----------+------------+------------+--------------+----------------+
| contact_id | last_name | first_name | birthday   | created_date | created_by     |
+------------+-----------+------------+------------+--------------+----------------+
|          1 | Newton    | Enigma     | 1999-08-19 | 2019-05-11   | root@localhost |
+------------+-----------+------------+------------+--------------+----------------+ 
```

**4。在插入触发器之后:**
顾名思义，该触发器在实现插入后被调用。

**例:**
考虑表格:

```
create table contacts (contact_id int (11) NOT NULL AUTO_INCREMENT, 
                              last_name VARCHAR(30) NOT NULL, 
                              first_name VARCHAR(25), birthday DATE,
                              ->CONSTRAINT contacts_pk PRIMARY KEY (contact_id));
create table contacts_audit (contact_id integer, 
                             created_date date, 
                             created_by varchar (30)); 
```

发生插入后，触发将联系人 id 和联系人创建日期/用户信息插入联系人审核记录:

```
delimiter //
create trigger contacts_after_insert
            -> after insert
            -> on contacts for each row
            -> begin
            ->    DECLARE vUser varchar(50);
            ->
            ->    -- Find username of person performing the INSERT into table
            ->    SELECT USER() into vUser;
            ->
            ->    -- Insert record into audit table
            ->    INSERT into contacts_audit
            ->    ( contact_id,
            ->      created_date,
            ->      created_by)
            ->    VALUES
            ->    ( NEW.contact_id,
            ->      SYSDATE(),
            ->      vUser );
            -> END; // 
```

进行插入以调用触发器:

```
insert into contacts values (1, "Kumar", "Rupesh", 
                         str_to_date("20-06-1999", "%d-%m-%Y")); 
```

**输出:**

```
select *from contacts_audit;
+------------+--------------+----------------+
| contact_id | created_date | created_by     |
+------------+--------------+----------------+
|          1 | 2019-05-11   | root@localhost |
+------------+--------------+----------------+
1 row in set (0.0006 sec) 
```

**5。在删除触发器之前:**
顾名思义，在删除发生之前，或者在执行删除语句之前调用这个触发器。

**例:**
考虑表格:

```
create table contacts (contact_id int (11) NOT NULL AUTO_INCREMENT, 
                             last_name VARCHAR (30) NOT NULL, first_name VARCHAR (25), 
                             birthday DATE, created_date DATE, created_by VARCHAR(30), 
                             CONSTRAINT contacts_pk PRIMARY KEY (contact_id));
create table contacts_audit (contact_id integer, deleted_date date, deleted_by varchar(20)); 
```

在删除发生之前，触发将联系人 id 和联系人删除日期/用户信息插入联系人审核记录:

```
delimiter //
create trigger contacts_before_delete
            -> before delete
            -> on contacts for each row
            -> begin
            ->
            ->    DECLARE vUser varchar(50);
            ->
            ->    -- Find username of person performing the DELETE into table
            ->    SELECT USER() into vUser;
            ->
            ->    -- Insert record into audit table
            ->    INSERT into contacts_audit
            ->    ( contact_id,
            ->      deleted_date,
            ->      deleted_by)
            ->    VALUES
            ->    ( OLD.contact_id,
            ->      SYSDATE(),
            ->      vUser );
            -> end; // 
```

进行插入，然后删除该插入以调用触发器:

```
delimiter;
insert into contacts values (1, "Bond", "Ruskin", 
                             str_to_date ("19-08-1995", "%d-%m-%Y"), 
                             str_to_date ("27-04-2018", "%d-%m-%Y"), "xyz");
delete from contacts where last_name="Bond"; 
```

**输出:**

```
select *from contacts_audit;
+------------+--------------+----------------+
| contact_id | deleted_date | deleted_by     |
+------------+--------------+----------------+
|          1 | 2019-05-11   | root@localhost |
+------------+--------------+----------------+
1 row in set (0.0007 sec) 
```

**6。删除触发器后:**
顾名思义，这个触发器是在删除发生后，或者在执行删除操作后调用的。

**示例:**
考虑一下表格:

```
create table contacts (contact_id int (11) NOT NULL AUTO_INCREMENT, 
                            last_name VARCHAR (30) NOT NULL, first_name VARCHAR (25), 
                            birthday DATE, created_date DATE, created_by VARCHAR (30), 
                            CONSTRAINT contacts_pk PRIMARY KEY (contact_id));
create table contacts_audit (contact_id integer, deleted_date date, deleted_by varchar(20));
```

发生删除后，触发将联系人 id 和联系人删除日期/用户信息插入联系人审核记录:

```
create trigger contacts_after_delete
           -> after delete
           -> on contacts for each row
           -> begin
           ->
           ->    DECLARE vUser varchar(50);
           ->
           ->    -- Find username of person performing the DELETE into table
           ->    SELECT USER() into vUser;
           ->
           ->    -- Insert record into audit table
           ->    INSERT into contacts_audit
           ->    ( contact_id,
           ->      deleted_date,
           ->      deleted_by)
           ->    VALUES
           ->    ( OLD.contact_id,
           ->      SYSDATE(),
           ->      vUser );
           -> end; // 
```

进行插入和删除以调用触发器:

```
delimiter;
insert into contacts values (1, "Newton", "Isaac", 
                             str_to_date ("19-08-1985", "%d-%m-%Y"), 
                             str_to_date ("23-07-2018", "%d-%m-%Y"), "xyz");
delete from contacts where first_name="Isaac"; 
```

**输出:**

```
select *from contacts_audit;
+------------+--------------+----------------+
| contact_id | deleted_date | deleted_by     |
+------------+--------------+----------------+
|          1 | 2019-05-11   | root@localhost |
+------------+--------------+----------------+
1 row in set (0.0009 sec) 
```