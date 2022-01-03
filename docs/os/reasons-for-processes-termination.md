# 流程终止的原因

> 原文:[https://www . geesforgeks . org/process-termination/](https://www.geeksforgeeks.org/reasons-for-processes-termination/)

当出现某些错误或缺省情况时，操作系统中的进程可以被终止。以下是导致流程终止的一些原因，

**流程终止原因:**

1.  **Normal Completion:**
    A process can complete its execution in a normal manner by executing an operating system service call.
2.  **Unavailability of the Required Memory:**
    A process is terminated when the system is unable to provide the memory required, as it is more than the memory that it is actually contained in the system

3.  **Exceed in the Execution Time Limit:**
    Process termination also occurs when its execution time is very much longer than the specific time limit i.e., it takes longer time to execute. This is because of the following possibilities,
    **(i)** Total elapsed time
    **(ii)** Time to execute
    **(iii)** The time interval since the last input is provided by Total elapsed time Time to execute the user. This usually occurs in case of interactive processes.
4.  **Violating Memory Access Limits:**
    A process can even be terminated, when it is attempting to access a memory location to which access is not permitted
5.  **Protection Error:**
    A protection error occurs when a process is trying to use a resource (e.g. file) to which access is not granted or using it in an inappropriate manner such as writing to a read-only file.
6.  **Arithmetic Error:**
    Some arithmetic errors such as, division-by-zero or storing a number greater than the hardware capacity also leads to process termination.
7.  **Input/Output Failure:**
    It refers to an error that results from some input/output operation, such as inability to find a file, failure of a read or write operation even after trying a certain number of times.
8.  **Misuse of Data:**
    Misuse of data i.e., using wrong type or un-initialized data also terminates the process.
9.  **Exceeding the Waiting Time Limit:**
    Exceeding the waiting time for occurrence of an event also terminates the process.
10.  **Invalid Instruction Execution:**
    When a process is trying to execute an instruction that actually does not exist, the process gets terminated.
11.  **Using a Privileged Instruction:**
    An attempt to use an operating system instruction by a process stops its execution.
12.  **Interference by an Operating System or an Operator:**
    An operator or an operating system sometimes interferes with process execution and leads to its termination. One such example is the occurrence of deadlocks.
13.  **Parent Process Termination:**
    When a parent process terminates, it causes all its child processes to stop their execution.
14.  **来自父进程的请求:**
    在子进程执行期间，父进程有权随时终止其任何子进程。