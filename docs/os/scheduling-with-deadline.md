# 带截止日期的日程安排

> 原文:[https://www.geeksforgeeks.org/scheduling-with-deadline/](https://www.geeksforgeeks.org/scheduling-with-deadline/)

前提条件: [CPU 调度](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)

**什么是带截止日期的排产？**
调度问题的目标是对任务进行调度，从而获得最大的总利润。这种有期限的调度算法不同于没有期限的调度，因为这里的任务完成与利润相关联。为了盈利，工作必须在截止日期前完成。否则，工作完成根本不算数，也赚不到利润。这个问题的目标是构造一个给出最大利润的可行序列。

如果所有工作都在截止日期前结束，那么序列是可行的。如果至少有一个序列是可能的，那么一组作业称为可行集。与最大利润相关的序列被称为最优序列，构成该序列的元素构成了最优作业集。

**示例**–
考虑下表中显示的项目和利润，让我们找到可以安排的最佳工作集，以便利润最大化。

该表描述了有截止日期和利润的工作

<figure class="table">

| 工作 | 最后期限 | PROFIT(₨) |
| --- | --- | --- |
| one | Two | Sixty |
| Two | one | Thirty |
| three | Two | Forty |
| four | one | Eighty |

给定问题的目标是找到一组可行的解决方案。让我们运用贪婪的方法。

*   最初解决方案=空，然后添加作业 1，因此解决方案= {1}。可以观察到，作业 2 作为任务{2，1}添加时是可能的，但作为任务{1，2}添加时是不可能的。
    为什么？让我们检查一下情况，
*   考虑序列{1，2}。任务 1 的调度是可能的。但是，调度任务 2 是不可能的，因为它的截止日期只有 1 个单位，已经花在等待时间上了。另一方面{2，1，}是可行的，因为没有违反作业 2 的截止日期，作业 1 的截止日期是 2 个单位。因此，在作业 2 被处理之后，作业 1 可以很好地被容纳。类似地，可以观察到作业序列{1，4}、{2，4}、{3，4}、{1，2，3}、{2，3，4}和{1，2，3，4}的调度是不可能的。

**所有可能的序列是–**

<figure class="table">

| 加工序列 | 总利润 |
| --- | --- |
| 2, 1 | Ninety |
| 3、1 或 1、3 | One hundred |
| 2, 3 | Seventy |
| 4, 1 | One hundred and forty |
| 4, 3 | One hundred and twenty |

最大利润与序列{4，1}相关。因此，最佳顺序为{4，1}。我们还可以观察到，虽然{4，1}是最佳的，但是由于违反了截止日期条件，序列{1，4}是不可能的。

**算法:**

```
Step1: Sort the jobs in a non-increasing order by profit
Step2: Solution = null
Step3: For all the task do the following:
        select the next job;
        if task is feasible (i.e, the task deadline is not violated) then add this job to the solution
        EEND if
Step4: If all the instances are solved then exit.
```

**形式上，带截止期的调度问题的算法如下:**

```
Algorithm Schedule_with_deadline
%%Input: A set of jobs 1 to n with service item
%%Output: An optimal schedule

Begin
    s= sorted array of jobs based on profit in non-decreasing order
    i=1
    schedule=NULL
    while(i <= n) do                        %%for all jobs do
        select the next job i from S        %% selection procedure
        if(Scheduling job is feasible) then    %%Feasibility check
        solution = schedule U job i of S
        i=i+1
    End while
    return(solution)
End
```

可以观察到，该算法首先根据利润对作业进行排序，然后在不违反截止日期考虑的情况下逐个选择作业进行调度。对所有作业重复这个过程，最后，算法返回解。

存在一个检查作业序列可行性的原则，该原则指出，如果作业序列根据非递减的截止日期进行调度是可行的，则作业序列是可行的。

*   因此，序列{1，2，3}是可行的，因为作业是基于非递减的截止日期安排的。
*   另一方面，序列{1，2，3，4}是不可行的。
*   原因是虽然有 4 个作业，但这个顺序意味着所有作业都应该在 3 个时间单位之前完成。
*   由于每个作业至少需要 1 个时间单位，因此该顺序是不可行的。
    因此，人们可以使用这种观察来检查作业调度的可行性，因为这在竞争性考试期间节省了时间。

</figure>

</figure>