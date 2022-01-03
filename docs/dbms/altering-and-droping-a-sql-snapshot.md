# 更改和删除 SQL 快照

> 原文:[https://www . geesforgeks . org/altering-and-drop-a-SQL-snapshot/](https://www.geeksforgeeks.org/altering-and-droping-a-sql-snapshot/)

**先决条件–**[SQL 快照](https://www.geeksforgeeks.org/sql-snapshots/)

随着数据库发生变化，快照开始增长/变化，甚至可能看到大小的显著变化。因此，我们会在需要时更改它们，以避免磁盘空间不足警报。因此，我们会在必要时更改快照。如果由于错误(或任何其他情况)用户删除了存储过程、视图或表或任何对象，您可以使用快照恢复数据库对象。如果删除了所有对象和数据，就有可能将快照中的所有信息恢复到原始数据库中。

**更改 SQL 中的快照:**

**语法:**

```
ALTER SNAPSHOT <snapshot-name>
[schema]
[ [PCTFREE <Integer>] [PCTUSED <Integer>] 
[INITRANS <Integer>] [MAXTRANS <Integer>] 
[TABLESPACE <Tablespace>] [STORAGE <StorageClause>] 
[CLUSTER <cluster>(<column1> [<column2>, ....])]
]
[USING
 [INDEX
     [PCTFREE <Integer>] [PCTUSED <Integer>] 
     [INITRANS <Integer>] [MAXTRANS <Integer>]
]
[DEFAULT ROLLBACK SEGMENT
  [MASTER <RollbackSegment>/LOCAL]
]
]
[REFRESH [FAST/COMPLETE/FORCE]
 [START WITH <Date>][NEXT <Date>]  
 [WITH [PRIMARY KEY/ROWID]]
]
```

**关键词及参数:**

*   **模式–**
    包含快照。如果未指定，Oracle 会在用户的方案中创建快照。
*   **pctfile、PCTUSED、INITRANS 和 MAXTRANS–**
    这些为 Oracle 用来维护快照数据的内部表建立指定参数的值。
*   **表空间–**
    指定要在其中创建快照的表空间。如果省略，Oracle 会在快照方案所有者的默认表空间中创建快照。
*   **存储–**
    为 Oracle 用来维护快照数据的表建立存储特征。
*   **集群–**
    创建快照作为指定集群的一部分。因为群集快照使用群集的空间分配。
*   **使用索引–**
    指定索引的参数以维护快照。PCTFREE、PCTUSED、INITRANS 和 MAXTRANS 指定快照的默认存储和事务属性。
*   **回滚段–**
    指定快照刷新期间要使用的本地快照和/或远程主回滚段。
*   **MASTER–**
    指定使用哪个回滚段。
*   **本地–**
    指定要用于包含快照的本地刷新组的回滚段。如果未指定，则默认情况下 Oracles 会使用此选项。如果用户指定 DEFAULT，则用户不能指定回滚段。

*   **REFRESH–**
    指定 Oracle 自动刷新快照的方式和时间。*   **FAST–**
    指定快速刷新或仅使用存储在与主表相关联的快照日志中的更新数据进行刷新。*   **完成–**
    指定完全刷新或重新执行快照查询。*   **FORCE–**
    指定快速刷新(如果可能)，或者指定完全刷新(如果不可能快速刷新)。这是神谕诱导的默认。*   **以–**
    开始指定首次自动刷新时间的日期表达式。*   **NEXT–**
    指定计算自动刷新间隔的日期表达式。*   **带主键–**
    指定要创建的主键快照。这允许识别快照主表，而不影响快照继续快速刷新的能力。*   **WITH ROWID –**
    Specifies that ROWID snapshots are to be created that provide backward compatibility with Oracle.

    **示例:**

    ```
    ALTER SNAPSHOT snp_emp
    REFRESH COMPLETE  
    START WITH TRUNC(SYSDATE+7) + 2/24 
    NEXT SYSDATE+1
    ```

    **删除一个 SQL 快照:**
    删除一个 SQL 快照会从数据库中删除该快照。

    **语法:**

    ```
    DROP SNAPSHOT 
    ```

    删除快照时，如果快照日志与之关联，则仅删除维护该快照所需的行。删除快照所基于的主表不会删除快照。但是，任何后续刷新都将失败。

    **示例:**

    ```
    drop snapshot snp_emp;
    ```