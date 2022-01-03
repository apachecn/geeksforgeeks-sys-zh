# SQL | MERGE 语句

> 原文:[https://www.geeksforgeeks.org/sql-merge-statement/](https://www.geeksforgeeks.org/sql-merge-statement/)

**先决条件–**[插入](https://www.geeksforgeeks.org/sql-insert-statement/)、[更新](https://www.geeksforgeeks.org/sql-update-statement/)、[删除](https://www.geeksforgeeks.org/sql-delete-statement/)

SQL 中的 **MERGE** 命令实际上是三个 SQL 语句的组合: **INSERT、UPDATE 和 DELETE** 。简单地说，SQL 中的 MERGE 语句提供了一种方便的方法来一起执行所有这三个操作，这在处理大型运行数据库时非常有帮助。但与 INSERT、UPDATE 和 DELETE 语句不同，MERGE 语句需要一个源表来对被称为目标表的所需表执行这些操作。

现在我们知道，SQL 中的 MERGE 需要两个表:一个是我们要对其执行 INSERT、UPDATE 和 DELETE 操作的目标表，另一个是源表，它包含目标表的新的已修改和正确的数据，并实际与实际的目标表进行比较，以便对其进行修改。

换句话说，SQL 中的 MERGE 语句基本上是根据指定的条件将源结果集中的数据合并到目标表中。MERGE 语句的语法一开始可能很难理解，但是一旦你知道了它的意思，就很容易理解了。所以，为了不混淆，让我们先讨论一些基础知识。假设您有两个表:源表和目标表，现在考虑是否要借助由最新详细信息组成的源表对所需的目标表进行更改。

*   何时需要在目标表中插入数据？
    显然当源表中有数据而目标表中没有数据时*即*当数据与目标表不匹配时。
*   什么时候需要更新数据？
    当源表中的数据与目标表匹配，但主键以外的任何条目不匹配时。
*   什么时候需要删除数据？
    当目标表中有数据而源表中没有数据时*，即当数据与源表不匹配时*。

现在，我们知道何时使用 INSERT、UPDATE 和 DELETE 语句，以防我们想要使用 MERGE 语句，这样您理解下面给出的语法应该没有问题:

```
//.....syntax of MERGE statement....//

//you can use any other name in place of target
MERGE target_table_name AS TARGET  

//you can use any other name in place of source 
USING source_table_name AS SOURCE   
ON condition (for matching source and target table)
WHEN MATCHED (another condition for updation)

 //now use update statement syntax accordingly
THEN UPDATE                       
WHEN NOT MATCHED BY TARGET 

//now use insert statement syntax accordingly
THEN INSERT                        
WHEN NOT MATCHED BY SOURCE 
THEN DELETE;

```

这就是 MERGE 语句及其语法的全部内容。

**参考资料–**
[MERGE–docs . Microsoft](https://docs.microsoft.com/en-us/sql/t-sql/statements/merge-transact-sql)
[MERGE–docs . Oracle](https://docs.oracle.com/cd/B19306_01/server.102/b14200/statements_9016.htm)

本文由 [**Dimpy Varshni**](https://auth.geeksforgeeks.org/profile.php?user=Dimpy Varshni) 投稿，如果你喜欢 GeeksforGeeks 并且愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章，或者把文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。