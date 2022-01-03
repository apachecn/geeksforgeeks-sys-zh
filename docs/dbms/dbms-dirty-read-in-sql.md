# SQL 中的脏读

> 原文:[https://www.geeksforgeeks.org/dbms-dirty-read-in-sql/](https://www.geeksforgeeks.org/dbms-dirty-read-in-sql/)

先决条件–[调度类型](https://www.geeksforgeeks.org/dbms-concurrency-control-types-of-schedules/)、[事务隔离级别在 DBMS 中](https://www.geeksforgeeks.org/transaction-isolation-levels-dbms/)、
常见的并发问题主要有四种:脏读、读丢失、不可重复读和幻影读。

**脏读–**
当一个事务被允许读取一个已经被另一个事务修改过的行时，此时还没有提交*脏读*发生。这主要是因为一次有多个事务没有提交。

**示例–**

**表–**记录

| 身份证明 | Cus_Name | 保持平衡 |
| one | 亚当 | One hundred |
| Two | 海英 | One hundred and fifty |

**交易–**
从 S Adam 账户向 Zee Young 账户转账 10:

```
Input:
BEGIN TRY
  BEGIN TRANSACTION
    UPDATE Table SET Balance = Balance - 10 WHERE ID=1;
    UPDATE Table SET Balance = Balance + 10 WHERE ID='C';
  COMMIT TRANSACTION
  PRINT 'Committed'
END TRY
BEGIN CATCH
  ROLLBACK TRANSACTION
  PRINT 'Not Committed'
END CATCH

Output:
Not committed 
```

通过执行上面的查询，输出将是“未提交”，因为有一个错误，没有 ID=C。因此，在那时，如果我们想用该行执行另一个事务，那么时间**脏读**发生。没有部分提交如果两个更新查询都成功，那么输出将是“已提交”。

执行前:

**表–**记录

| 身份证明 | Cus_Name | 保持平衡 |
| one | 亚当 | One hundred |
| Two | 海英 | One hundred and fifty |

执行后:

```
Input: 
        BEGIN TRY
          BEGIN TRANSACTION
            UPDATE Table SET Balance = Balance - 10 WHERE ID=1;
            UPDATE Table SET Balance = Balance + 10 WHERE ID='C';
          COMMIT TRANSACTION
          PRINT 'Committed'
        END TRY
        BEGIN CATCH
          ROLLBACK TRANSACTION
          PRINT 'Not Committed'
        END CATCH

Output: 
        (1row affected)
        (0row affected)
      Not Committed 
```

请注意，如果我们输入一个有效的标识，第一个事务结果将显示为提交或 1 行生效，但第二个不受影响。

**说明–**
如果我们有一个订票系统，一个客户当时想订一张票，票的可用数量是 10，在完成支付之前，第二个客户想订一张票，那么这次第二次交易会向第二个客户显示可用票的数量是 9。问题是，如果第一个客户的借记卡或钱包中没有足够的资金，那么第一个交易将回滚，此时第二个交易读取的 9 个可用座位是*脏读*。

**示例:**
**第一位客户可用票:**

*   **1st Step –**

    ```
    Input:
    -- Transaction 1
    Select *from Bus_ticket; 
    ```

    **输出:**

    | 身份证明 | 总线名称 | 可用座位 |
    | one | KA0017 | Ten |

*   **2nd Step –**
    Booking time for 1st customer

    ```
    Input:  
    --Transaction 1
            BEING Transaction
            UPDATE Bus_Ticket set Available_Seat=9
            WHERE ID=1

            --Payment for Transaction 1
            Waitfor Delay '00.00.30'
            Rollback transaction 
    ```

    **可用票:**第二位顾客，第一位顾客支付票款。

*   **3rd Step –**

    ```
    Input:  
    -- Transaction 1

    set transaction isolation level read uncommitted
    Select *from Bus_ticket where ID=1; 
    ```

    **输出:**

    | 身份证明 | 总线名称 | 可用座位 |
    | one | KA0017 | nine |

请注意，在支付第一笔客户第二笔交易时，如果第一笔交易回滚，则有 9 个席位可用，即脏读数据。回滚第一笔交易后，可用座位再次为 10。第二步和第三步同时发生。

事务 1 回滚后的实际可用座位:

| 身份证明 | 总线名称 | 可用座位 |
| one | KA0017 | Ten |