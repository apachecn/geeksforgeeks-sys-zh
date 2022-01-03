# SQL |触发器

> 原文:[https://www.geeksforgeeks.org/sql-triggers/](https://www.geeksforgeeks.org/sql-triggers/)

**Trigger** 是当数据库有任何修改时，系统自动执行的语句。在触发器中，我们首先指定何时执行触发器，然后指定触发器执行时要执行的操作。触发器用于指定某些不能使用 SQL 的约束机制指定的完整性约束和引用约束。

**示例–**
假设我们正在向“献血者”表添加一个元组，该元组是某个人献血了。因此，我们可以设计一个触发器，自动将捐献血液的价值添加到“血液记录”表中。

**触发器的类型–**
我们可以为每个表定义 6 种类型的触发器:

1.  **插入后**在数据插入表格后激活。

2.  **更新后:**表中数据修改后激活。

3.  **AFTER DELETE:** 从表中删除/移除数据后激活。

4.  **在插入之前:**在数据插入表格之前激活。

5.  **更新前:**在修改表中数据前激活。

6.  **BEFORE DELETE:** 在从表中删除/移除数据之前激活。

显示触发器实现的示例:

**1。编写一个触发器，确保数据库中不能插入年龄小于 25 岁的员工。**

```
delimiter $
CREATE TRIGGER  Check_age  BEFORE INSERT ON employee 
FOR EACH ROW
BEGIN
IF NEW.age < 25 THEN
SIGNAL SQLSTATE '45000'
SET MESSAGE_TEXT = 'ERROR: 
         AGE MUST BE ATLEAST 25 YEARS!';
END IF;
END; $
delimiter; 
```

**解释:**每当我们想要向表‘employee’插入任何元组时，那么在向表插入这个元组之前，将执行名为‘Check _ age’的触发器。此触发器将检查年龄属性。如果大于 25，则该元组将被插入到元组中，否则将打印一条错误消息，说明“错误:年龄必须至少为 25 岁！”

**2。在 employee 表中创建一个在删除前有效的触发器，并在另一个表 employee_backup 中创建该记录的副本。**

在写触发器之前，我们需要创建 employee_backup 表。

```
create table employee_backup (employee_no int, 
      employee_name varchar(40), job varchar(40), 
      hiredate date, salary int, 
      primary key(employee_no)); 
```

```
delimiter $
CREATE TRIGGER Backup BEFORE DELETE ON employee 
FOR EACH ROW
BEGIN
INSERT INTO employee_backup
VALUES (OLD.employee_no, OLD.name, 
        OLD.job, OLD.hiredate, OLD.salary);
END; $
delimiter; 
```

**说明:**我们想创建一个备份表，保存那些不再是机构员工的员工的价值。因此，我们创建了一个名为 Backup 的触发器，它将在从表雇员中删除任何 Tuple 之前执行。在删除之前，表 employee 的所有属性值都将存储在表 employee_backup 中。

**3。编写一个触发器来计算使用每个 insert 语句插入的新元组的数量。**

```
Declare count int
Set count=0;
delimiter $
CREATE TRIGGER Count_tupples 
             AFTER INSERT ON employee 
FOR EACH ROW
BEGIN
SET count = count + 1;
END; $
delimiter;
```

**说明:**我们想跟踪员工表中新元组的数量。为此，我们首先创建一个变量“count”，并将其初始化为 0。之后，我们创建一个名为 Count_tuples 的触发器，在表 employee 中插入任何新的 Tuple 后，该触发器将增加 Count 的值。