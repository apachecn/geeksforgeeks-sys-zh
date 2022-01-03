# 数据库管理系统中断言和触发器的区别

> 原文:[https://www . geesforgeks . org/DBMS 中断言和触发器的区别/](https://www.geeksforgeeks.org/difference-between-assertions-and-triggers-in-dbms/)

**1。什么是断言？**
当一个约束涉及 2 个(或更多)表时，表约束机制有时会很难，结果可能不会像预期的那样。为了覆盖这种情况 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 支持创建断言，这些断言是不仅仅与一个表相关联的约束。断言语句应该确保数据库中始终存在某个条件。每当在相应的表中进行修改时，数据库管理系统总是检查断言。

**语法–**

```
CREATE ASSERTION  [ assertion_name ]
CHECK ( [ condition ] );
```

**示例–**

```
CREATE TABLE sailors (sid int,sname varchar(20), rating int,primary key(sid),
CHECK(rating >= 1 AND rating <=10)
CHECK((select count(s.sid) from sailors s) + (select count(b.bid)from boats b)<100) ); 
```

在上面的例子中，我们强制执行 CHECK 约束，即船只和水手的数量应该少于 100。因此，在这里，我们能够同时检查两个平板电脑的约束。

**2。什么是** [**触发**](https://www.geeksforgeeks.org/sql-trigger-student-database/) **？**
触发器是与表相关联的数据库对象，当对表执行定义的操作时，它将被激活。当我们运行以下语句时，可以执行触发器:

1.  插入
2.  更新
3.  删除

并且可以在事件之前或之后调用。

**语法–**

```
create trigger [trigger_name]       
[before | after]          
{insert | update | delete} 
on [table_name]  
[for each row]    
[trigger_body]  
```

**示例–**

```
create trigger t1  before  UPDATE on sailors
for each row
begin
   if new.age>60 then
      set new.age=old.age;
   else
      set new.age=new.age;
   end if;
end;
$ 
```

在上面的例子中，我们在更新之前创建了触发器。所以，如果新时代大于 60 岁我们就不应该更新，否则我们就应该更新。我们可以使用“{content}”来调用这个触发器。符号。

**断言和触发器的区别:**

<figure class="table">

| S.No | 断言 | 扳机 |
| --- | --- | --- |
| 1. | 当我们知道给定的特定条件总是真的时，我们可以使用断言。 | 我们可以使用触发器，即使特定条件可能为真，也可能为假。 |
| 2. | 当不满足 SQL 条件时，整个表甚至数据库都有可能被锁定。 | 如果查询条件不为真，触发器会捕获错误。 |
| 3. | 断言没有链接到特定的表或事件。它执行用户指定或定义的任务。 | 它有助于维护数据库表中的完整性约束，尤其是在没有定义主键和外键约束的情况下。 |
| 4. | 断言不维护对表中所做更改的任何跟踪。 | 触发器跟踪表中发生的所有更改。 |
| 5. | 与触发器相比，断言的语法很小。 | 它们有很大的语法来指示创建的触发器的每个细节。 |
| 6. | 现代数据库不使用断言。 | 触发器在现代数据库中使用得非常好。 |

断言不能修改数据，也不能链接到数据库中的任何特定表或事件，但是触发器更强大，因为它们可以检查条件，也可以修改数据库中表内的数据，这与断言不同。

</figure>