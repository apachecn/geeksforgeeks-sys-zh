# 在 SQL Server 中创建登录

> 原文:[https://www.geeksforgeeks.org/create-login-in-sql-server/](https://www.geeksforgeeks.org/create-login-in-sql-server/)

登录名是一个用户帐户，您可以使用它来访问 SQL server。登录通过安全标识符(SID)附加到用户。

**创建登录的权限:**
具有安全管理员或系统管理员固定服务器角色成员身份的用户可以在服务器上创建登录。

1.  **Creating a login with a password :**

    **语法–**

    ```
    CREATE LOGIN <loginname> WITH PASSWORD = '<Password>';

    ```

    **注意:**密码区分大小写。

    **示例**使用密码为特定用户创建登录。

    ```
    CREATE LOGIN geeks 
    WITH PASSWORD = 'gEe@kF0rG##ks'; 
    ```

2.  **Creating a login with a password that has got to be changed :**

    **语法–**

    ```
    CREATE LOGIN <loginname> WITH PASSWORD = '<Password>'
    MUST_CHANGE, CHECK_EXPIRATION = ON;

    ```

    **示例**为有密码的用户创建登录。

    ```
    CREATE LOGIN geeks WITH PASSWORD = 'gEe@kF0rG##ks'
    MUST_CHANGE, CHECK_EXPIRATION = ON;

    ```

    **注意–**
    MUST _ CHANGE 选项要求用户在首次连接到服务器时更改此密码。当检查到期关闭时，不能使用必须更改选项。

3.  **Creating a login from a Windows domain account :**

    **语法–**

    ```
    CREATE LOGIN [<domainname>\<loginname>] 
    FROM WINDOWS;

    ```

    **示例**从 Windows 域帐户创建登录。

    ```
    CREATE LOGIN [AD\geeks] FROM WINDOWS; 
    ```

4.  **Creating a login from a SID :**

    **语法–**

    ```
    CREATE LOGIN <loginname> 
    WITH PASSWORD = '<Password>', 
    SID = 0x241C11948AEEB749B0D22646DB1AXXXX;

    ```

    **示例**从 SID 创建登录。

    ```
    CREATE LOGIN geeks 
    WITH PASSWORD = 'gEe@kF0rG##ks', 
    SID = 0x241C11948AEEB749B0D22646DB1AXXXX; 
    ```

5.  **Creating a login with multiple arguments**

    **语法–**

    ```
    CREATE LOGIN <loginname>
    WITH PASSWORD = '<Password>',
    DEFAULT_DATABASE = <Databasename>,
    CHECK_POLICY = OFF,
    CHECK_EXPIRATION = OFF ; 
    ```

    **示例**使用多个参数一起创建登录。

    ```
    CREATE LOGIN geeks WITH PASSWORD = 'gEe@kF0rG##ks'
    DEFAULT_DATABASE = GeeksDB,
    CHECK_POLICY = OFF,
    CHECK_EXPIRATION = OFF ; 
    ```

    **注意:**
    不支持 CHECK_POLICY = OFF 和 CHECK _ EXPIRATION 的组合。