# 自由裁量权的类型

> 原文:[https://www . geeksforgeeks . org/全权特权类型/](https://www.geeksforgeeks.org/types-of-discretionary-privileges/)

**特权**允许用户以某种方式访问某些数据，以读取、写入或删除等。

**自主特权的类型:**
自主访问控制包括授予和撤销被称为自主特权的特权。这种访问控制由每个资源的所有者帐户组成，所有者帐户可以控制权限的访问，如读取数据或修改数据库的数据。

数据库系统中有两个级别的自由特权:

1.  **帐户级别–**
    数据库管理员根据数据库中的关系指定每个帐户拥有的权限。帐户级别的权限是创建模式或创建表权限或创建视图。

*   **更改**权限以执行模式更改，如在关系中添加或删除属性。
*   **删除**权限删除关系或视图，
*   **修改**插入、删除或更新元组的权限

*   **选择**权限从数据库中检索信息或数据。

*   **Relation / Table Level –**
    It is the second level of privileges which is applied to the relation level. This includes tables or relations and virtual relations known as views. A user who has created a database object such as a table or a view will get all privileges on that object.This user is the holder of owner account which is created for each relation.

    在此级别中，将为每个关系创建一个所有者帐户，该帐户也将有权通过向其他用户的帐户授予权限来将权限传递给其他用户。

    授予和撤销自由特权可以通过使用一种称为访问矩阵模型的模型来完成。该模型规定了每个主体对每个对象的权利。

    **访问矩阵模型:**

    <center>

    | 科目 | 文件 1 | 文件 2 | 文件 3 |
    | --- | --- | --- | --- |
    | 玛丽 | 阅读 | 写 |  |
    | 萨希 |  | 阅读 | 写 |
    | Rahul | 写 | 阅读 | 附加 |

    </center>

    在这里，Mary 只有文件 1 的读取权限，她不能修改文件 1。所以，我们可以表示每个主体对每个对象的特权。矩阵 M 由类似用户、账户等主题的行和类似关系、视图等对象的列组成。矩阵中的每一个位置 M(i，j)代表了权限的类型，比如读、写、更新我持有的对象 j 上的主题。