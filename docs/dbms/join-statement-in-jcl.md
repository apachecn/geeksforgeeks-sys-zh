# JCL 中的连接语句

> 原文:[https://www.geeksforgeeks.org/join-statement-in-jcl/](https://www.geeksforgeeks.org/join-statement-in-jcl/)

先决条件–[作业控制语言(JCL)](https://www.geeksforgeeks.org/jcl-job-control-language/)
在 RDBMS 中，SQL JOIN 子句用于连接表并对其执行多个操作。为了对不同平面文件中的记录执行操作，使用了 JOINKEYS。借助 SORT JCL 中的 JOINKEYS，可以基于匹配的字段或键对匹配和不匹配的记录执行各种连接操作。连接可以通过多种方式执行，如内部连接、完全外部连接、左外部连接、右外部连接和不成对组合。

join 操作由三个重要的控制语句 JOINKEYS、JOIN 和 REFORMAT 控制。SORTJNF1 和 SORTJNF2 是用于指定将用于执行连接操作的文件的 DD 语句。

**控制语句:**

1.  连接关键字文件=F1，字段=(1，10，A)–指定文件 1 的连接标准。
2.  连接密钥文件=F2，字段=(1，10，A)–指定文件 2 的连接标准。
3.  重新格式化字段=(F1:1，71，F2:1，9)–重新格式化字段告诉排序实用程序，通过指定开始和结束位置，哪些字段将从输入文件写入输出文件。

**JCL SORT 连接两个文件，并从两个文件中写入记录:**

1.  **匹配记录(内部连接)–**
    如果排序卡中没有指定连接语句，F1 和 F2 的配对记录将被写入输出文件。

    ```
    //SYSIN DD *
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            REFORMAT FIELDS=(F1:1, 71, F2:1, 9)
    /*
    ```

2.  **文件 1 中的匹配记录和不匹配记录–**
    排序卡保留 F1 文件中的未配对记录以及配对记录。这种类型的连接称为左外连接。

    ```
    //SYSIN DD *
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            JOIN UNPAIRED, F1
            REFORMAT FIELDS=(F1:1, 71, F2:1, 9)
    /*
    ```

3.  **来自文件 1 的不匹配–**
    排序卡保留来自 F1 文件的未配对记录，不能在 F2 中使用重新格式化。

    ```
    //SYSIN DD * 
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            JOIN UNPAIRED, F1, ONLY
            REFORMAT FIELDS=(F1:1, 71)
    /*
    ```

4.  **文件 2 中的匹配记录和不匹配记录–**
    排序卡保留 F2 文件中的未配对记录以及配对记录。这种类型的连接称为右外连接。

    ```
    //SYSIN DD *
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            JOIN UNPAIRED, F2
            REFORMAT FIELDS=(F1:1, 71, F2:1, 9)
    /*
    ```

5.  **来自文件 2 的不匹配–**
    排序卡保留来自 F2 文件的未配对记录，不能在 F1 中使用重新格式化。

    ```
    //SYSIN DD *
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            JOIN UNPAIRED, F2, ONLY
            REFORMAT FIELDS=(F2:1, 9)
    /*
    ```

6.  **两个文件中的匹配记录和不匹配记录–**
    排序卡保留 F1 和 F2 文件中的未配对记录以及配对记录。这种类型的连接称为完全外部连接。

    ```
    //SYSIN DD *
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            JOIN UNPAIRED, F1, F2
            REFORMAT FIELDS=(F1:1, 71, F2:1, 9)
    /*
    ```

7.  **两个文件中不匹配的记录–**
    排序卡，仅保留 F1 和 F2 文件中不成对的记录。

    ```
    //SYSIN DD *
            SORT FIELDS=COPY
            JOINKEYS FILES=F1, FIELDS=(1, 10, A)
            JOINKEYS FILES=F2, FIELDS=(1, 10, A)
            JOIN UNPAIRED, F1, F2, ONLY or JOIN UNPAIRED, ONLY
            REFORMAT FIELDS=(F1:1, 71, F2:1, 9)
    /*
    ```