# 关系代数在 DBMS 中的介绍

> 原文:[https://www . geesforgeks . org/关系代数在 dbms 中的介绍/](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)

关系代数是以关系为输入，以生成关系为输出的过程查询语言。关系代数主要为关系数据库和 SQL 提供理论基础。

**关系代数中的运算符**

**投影(π)**
投影用于从关系中投影所需的列数据。

示例:

```
     R 
  (A  B  C)    
  ----------
   1  2  4
   2  2  3
   3  2  3
   4  3  4
```

```
π (BC) 
B  C
-----
2  4
2  3
3  4
```

**注意:**默认情况下，投影会删除重复数据。

**选择(σ)**
选择用于选择关系的所需元组。

对于上述关系
σ (c > 3)R
将选择 c 大于 3 的元组。

**注意:**选择操作符只选择需要的元组，不显示。为了显示，使用数据投影算子。

对于上面选择的元组，要显示我们还需要使用投影。

```
 π (σ (c>3)R ) will show following tuples.

A  B  C
-------
1  2  4
4  3  4
```

**并集(U)**
关系代数中的并集运算与集合论中的并集运算相同，唯一的约束是对于两个关系的并集，两个关系必须具有相同的属性集。

**集合差(-)**
关系代数中的集合差是与集合论中相同的集合差运算，其约束是两个关系应该具有相同的属性集。

**重命名(ρ)**
重命名是一元操作，用于重命名关系的属性。
ρ (a/b)R 将关系的属性‘b’重命名为‘a’。

**叉积(X)**

两个关系之间的叉积比如说 A 和 B，那么 A X B 之间的叉积将产生 A 的所有属性，然后是 B 的每个属性。A 的每个记录将与 B 的每个记录配对

下面是例子

```
   A                                  B
    (Name   Age  Sex )                (Id   Course)  
    ------------------                -------------
    Ram    14   M                      1     DS
    Sona   15   F                      2     DBMS
    kim    20   M

     A X B
  Name   Age   Sex   Id   Course
---------------------------------
  Ram    14    M      1    DS
  Ram    14    M      2    DBMS
  Sona   15    F      1    DS
  Sona   15    F      2    DBMS
  Kim    20    M      1    DS
  Kim    20    M      2    DBMS
```

**注意:**如果 A 有‘n’个元组，B 有‘m’个元组，那么 A X B 将有‘n * m’个元组。

**自然加入(⋈)**

自然连接是二元运算符。两个或多个关系之间的自然连接将产生所有元组组合的集合，其中它们具有相同的公共属性。

让我们看看下面的例子

```

           Emp                              Dep
   (Name   Id   Dept_name )          (Dept_name   Manager)
   ------------------------          ---------------------    
     A     120    IT                    Sale     Y
     B     125    HR                    Prod     Z
     C     110    Sale                  IT       A
     D     111    IT                      

Emp ⋈ Dep

Name   Id   Dept_name   Manager
-------------------------------
A     120   IT          A 
C     110   Sale        Y
D     111   IT          A
```

**条件连接**

条件连接的工作方式类似于自然连接。在自然连接中，默认情况下公共属性之间的条件是相等的，而在条件连接中，我们可以指定任何条件，如大于、小于、不相等

让我们看看下面的例子

```
         R                           S
  (ID   Sex   Marks)          (ID   Sex   Marks)
  ------------------          -------------------- 
   1   F   45                   10   M   20
   2   F   55                   11   M   22
   3   F   60                   12   M   59

Join between R And S with condition  R.marks >= S.marks

R.ID   R.Sex   R.Marks   S.ID   S.Sex   S.Marks
-----------------------------------------------
1       F       45        10     M        20
1       F       45        11     M        22
2       F       55        10     M        20
2       F       55        11     M        22
3       F       60        10     M        20
3       F       60        11     M        22
3       F       60        12     M        59
```

* * *

深度文章:
[基本-关系代数中的运算符](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/) [扩展关系代数运算符](https://www.geeksforgeeks.org/extended-operators-in-relational-algebra/)
以下是往年门题
[https://www . geesforgeks . org/Gate-Gate-cs-2012-Question-50/](https://www.geeksforgeeks.org/gate-gate-cs-2012-question-50/)
[https://www . geesforgeks . org/Gate-Gate-cs-2012-Question-43/](https://www.geeksforgeeks.org/gate-gate-cs-2012-question-43/)

**参考文献:**
[https://en.wikipedia.org/wiki/Relational_algebra](https://en.wikipedia.org/wiki/Relational_algebra)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论