# 并发事务恢复

> 原文:[https://www . geesforgeks . org/recovery-with-concurrent-transactions/](https://www.geeksforgeeks.org/recovery-with-concurrent-transactions/)

[并发控制](https://www.geeksforgeeks.org/concurrency-control-in-dbms/)是指可以同时执行多个事务，然后出现交错的日志。但是事务结果可能会有变化，所以请保持这些事务的执行顺序。

在恢复过程中，恢复系统很难回溯所有日志，然后开始恢复。

并发事务的恢复可以通过以下四种方式完成。

1.  Interaction with concurrency control
2.  Transaction rollback
3.  checking point
4.  Restart recovery

**与并发控制的交互:**

在该方案中，恢复方案在很大程度上取决于所使用的并发控制方案。因此，要回滚失败的事务，我们必须撤销事务执行的更新。

**事务回滚:**

*   In this scenario, we use logs to roll back a failed transaction.
*   The system scans the log backward after the failed transaction, and for each log record found in the log, the system will restore the data item.

**检查点:**

*   Checkpoint is the process of saving a snapshot of the application state so that it can be restarted from that point in case of failure.
*   Checkpoint is the point in time when records are written from the buffer to the database.
*   Checkpoints shorten the recovery process.
*   When the checkpoint is reached, the transaction will be updated to the database, and before that, the entire log file will be deleted from the file. Then update the log file with the new transaction step until the next checkpoint, and so on.
*   Checkpoint is used to declare the point before the database management system is in a consistent state, and all transactions have been committed.

为了缓解这种情况，大多数数据库管理系统都使用了“[检查点](https://www.geeksforgeeks.org/log-based-recovery-in-dbms/)”概念。

*   In this scheme, we use checkpoints to reduce the number of log records that must be scanned when the system recovers from the crash.
*   In the concurrent transaction processing system, we require the form of checkpoint log record to be , where **' l'** is the list of transactions active at the checkpoint.
*   Fuzzy checkpoints are checkpoints that allow transactions to perform updates, even when buffer blocks are being written out.

**重启恢复:**

*   When the system recovers from the crash, it will build two lists.
*   The undo list consists of transactions to undo, and the redo list consists of transactions to redo.
*   The system builds these two lists as follows: Initially, they are both empty. The system scans the log backward and checks each record until the first record is found.