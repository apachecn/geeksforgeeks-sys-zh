# 不同到达时间的循环调度

> 原文:[https://www . geesforgeks . org/不同到达时间的循环调度/](https://www.geeksforgeeks.org/round-robin-scheduling-with-different-arrival-times/)

**先决条件:** [到达时间为 0 的循环调度](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/)

循环**调度算法**用于为每个作业公平地调度进程一个时隙或时间段，并且如果该作业没有完成，则中断该作业，然后该作业跟随在时间段内到达的另一个作业，使得这些调度公平。

**注:**

*   循环赛在本质上是循环的，所以饥饿不会发生
*   循环调度是先到先得调度的变体
*   对任何过程或任务都没有给予优先、特别的重视
*   RR 调度也称为时间分片调度

**优势:**

*   每个进程由 CPU 在固定的时间内提供服务，因此每个进程的优先级是相同的
*   饥饿不会因为它的周期性而发生。

**缺点:**

*   吞吐量取决于量子时间。
*   如果我们想给一些过程优先权，我们不能。

<figure class="table">

| 过程 | 到达时间 | 突发时间 | 完成时间 | 解题时间 | 等待时间 |
| --- | --- | --- | --- | --- | --- |
| 第一亲代 | Zero | five | Twelve | Twelve | seven |
| P2 | one | four | Eleven | Ten | six |
| P3 | Two | Two | six | four | Two |
| P4 | three | one | nine | six | five |

</figure>

**量子时间为 2** 这意味着每个进程一次只执行 2 个时间单位。
**如何计算这些流程请求:-**

1.  采取最先发生的过程，并开始执行该过程(仅针对时间段)。
2.  检查是否有任何其他流程请求到达。如果一个进程请求在另一个进程正在执行的时间段内到达，那么将新进程添加到就绪队列中
3.  量程时间过去后，检查就绪队列中的任何进程。如果就绪队列为空，则继续当前过程。如果队列不为空且当前进程未完成，则将当前进程添加到就绪队列的末尾。
4.  从就绪队列中取出第一个进程并开始执行它(相同的规则)
5.  从 2-5 重复以上所有步骤
6.  如果过程完成，并且就绪队列为空，则任务完成

在所有这些之后，我们得到三次，它们是:

1.  **完成时间:**一个过程完成所花费的时间。
2.  **周转时间:**流程在系统中存在的总时间。(完成时间-到达时间)。
3.  **等待时间:**等待它们完全执行的总时间。(周转时间–爆发时间)。

**如何用** **编程语言**实现

```
1\. Declare arrival[], burst[], wait[], turn[] arrays and initialize them. Also declare a timer
   variable and initialize it to zero. To sustain the original burst array create another 
   array (temp_burst[]) and copy all the values of burst array in it.

2\. To keep a check we create another array of bool type which keeps the record of whether a
   process is completed or not. we also need to maintain a queue array which contains the process
   indicies (initially the array is filled with 0).

3\. Now we increment the timer variable until the first process arrives and when it does, we add the
   process index to the queue array 

4\. Now we execute the first process until the time quanta and during that time quanta, we check 
   whether any other process has arrived or not and if it has then we add the index in the queue
   (by calling the fxn. queueUpdation()).

5\. Now, after doing the above steps if a process has finished, we store its exit time and 
   execute the next process in the queue array. Else, we move the currently executed process at 
   the end of the queue (by calling another fxn. queueMaintainence()) when the time slice expires.

6\. The above steps are then repeated until all the processes have been completely executed. If a
   scenario arises where there are some processes left but they have not arrived yet, then we
   shall wait and the CPU will remain idle during this interval.
```

下面是上述方法的实现:

(为了简单起见，我们假设到达时间是以排序的方式输入的)
C++

## C++

```
//C++ Program for implementing
//Round Robin Algorithm
//code by sparsh_cbs
#include <iostream>

using namespace std;

void queueUpdation(int queue[],int timer,int arrival[],int n, int maxProccessIndex){
    int zeroIndex;
    for(int i = 0; i < n; i++){
        if(queue[i] == 0){
            zeroIndex = i;
            break;
        }
    }  
    queue[zeroIndex] = maxProccessIndex + 1;
}

void queueMaintainence(int queue[], int n){
    for(int i = 0; (i < n-1) && (queue[i+1] != 0) ; i++){
        int temp = queue[i];
        queue[i] = queue[i+1];
        queue[i+1] = temp;
    }
}

void checkNewArrival(int timer, int arrival[], int n, int maxProccessIndex,int queue[]){
    if(timer <= arrival[n-1]){
       bool newArrival = false;
       for(int j = (maxProccessIndex+1); j < n; j++){
             if(arrival[j] <= timer){
              if(maxProccessIndex < j){
                 maxProccessIndex = j;
                 newArrival = true;
              }
           }
       }
       //adds the incoming process to the ready queue
       //(if any arrives)
       if(newArrival)
          queueUpdation(queue,timer,arrival,n, maxProccessIndex);
    }
}

//Driver Code
int main(){
    int n,tq, timer = 0, maxProccessIndex = 0;
    float avgWait = 0, avgTT = 0;
    cout << "\nEnter the time quanta : ";
    cin>>tq;
    cout << "\nEnter the number of processess : ";
    cin>>n;
    int arrival[n], burst[n], wait[n], turn[n], queue[n], temp_burst[n];
    bool complete[n];

    cout << "\nEnter the arrival time of the processess : ";
    for(int i = 0; i < n; i++)
        cin>>arrival[i];

    cout << "\nEnter the burst time of the processess : ";
    for(int i = 0; i < n; i++){
        cin>>burst[i];
        temp_burst[i] = burst[i];
    }

    for(int i = 0; i < n; i++){    //Initializing the queue and complete array
        complete[i] = false;
        queue[i] = 0;
    }
    while(timer < arrival[0])    //Incrementing Timer until the first process arrives
        timer++;
    queue[0] = 1;

    while(true){
        bool flag = true;
        for(int i = 0; i < n; i++){
            if(temp_burst[i] != 0){
                flag = false;
                break;
            }
        }
        if(flag)
            break;

        for(int i = 0; (i < n) && (queue[i] != 0); i++){
            int ctr = 0;
            while((ctr < tq) && (temp_burst[queue[0]-1] > 0)){
                temp_burst[queue[0]-1] -= 1;
                timer += 1;
                ctr++;

                //Checking and Updating the ready queue until all the processes arrive
                checkNewArrival(timer, arrival, n, maxProccessIndex, queue);
            }
            //If a process is completed then store its exit time
            //and mark it as completed
            if((temp_burst[queue[0]-1] == 0) && (complete[queue[0]-1] == false)){
                //turn array currently stores the completion time
                turn[queue[0]-1] = timer;       
                complete[queue[0]-1] = true;
            }

              //checks whether or not CPU is idle
            bool idle = true;
            if(queue[n-1] == 0){
                for(int i = 0; i < n && queue[i] != 0; i++){
                    if(complete[queue[i]-1] == false){
                        idle = false;
                    }
                }
            }
            else
                idle = false;

            if(idle){
                timer++;
                checkNewArrival(timer, arrival, n, maxProccessIndex, queue);
            }

            //Maintaining the entries of processes
            //after each premption in the ready Queue
            queueMaintainence(queue,n);
        }
    }

    for(int i = 0; i < n; i++){
        turn[i] = turn[i] - arrival[i];
        wait[i] = turn[i] - burst[i];
    }

    cout << "\nProgram No.\tArrival Time\tBurst Time\tWait Time\tTurnAround Time"
         << endl;
    for(int i = 0; i < n; i++){
        cout<<i+1<<"\t\t"<<arrival[i]<<"\t\t"
          <<burst[i]<<"\t\t"<<wait[i]<<"\t\t"<<turn[i]<<endl;
    }
    for(int i =0; i< n; i++){
        avgWait += wait[i];
        avgTT += turn[i];
    }
    cout<<"\nAverage wait time : "<<(avgWait/n)
      <<"\nAverage Turn Around Time : "<<(avgTT/n);

    return 0;

}
```

## C#

```
// C# program to implement Round Robin
// Scheduling with different arrival time
using System;

class GFG {
    public static void roundRobin(String[] p, int[] a,
                                  int[] b, int n)
    {
        // result of average times
        int res = 0;
        int resc = 0;

        // for sequence storage
        String seq = "";

        // copy the burst array and arrival array
        // for not effecting the actual array
        int[] res_b = new int[b.Length];
        int[] res_a = new int[a.Length];

        for (int i = 0; i < res_b.Length; i++) {
            res_b[i] = b[i];
            res_a[i] = a[i];
        }

        // critical time of system
        int t = 0;

        // for store the waiting time
        int[] w = new int[p.Length];

        // for store the Completion time
        int[] comp = new int[p.Length];

        while (true) {
            Boolean flag = true;
            for (int i = 0; i < p.Length; i++) {

                // these condition for if
                // arrival is not on zero

                // check that if there come before qtime
                if (res_a[i] <= t) {
                    if (res_a[i] <= n) {
                        if (res_b[i] > 0) {
                            flag = false;
                            if (res_b[i] > n) {

                                // make decrease the b time
                                t = t + n;
                                res_b[i] = res_b[i] - n;
                                res_a[i] = res_a[i] + n;
                                seq += "->" + p[i];
                            }
                            else {

                                // for last time
                                t = t + res_b[i];

                                // store comp time
                                comp[i] = t - a[i];

                                // store wait time
                                w[i] = t - b[i] - a[i];
                                res_b[i] = 0;

                                // add sequence
                                seq += "->" + p[i];
                            }
                        }
                    }
                    else if (res_a[i] > n) {

                        // is any have less arrival time
                        // the coming process then execute
                        // them
                        for (int j = 0; j < p.Length; j++) {

                            // compare
                            if (res_a[j] < res_a[i]) {
                                if (res_b[j] > 0) {
                                    flag = false;
                                    if (res_b[j] > n) {
                                        t = t + n;
                                        res_b[j]
                                            = res_b[j] - n;
                                        res_a[j]
                                            = res_a[j] + n;
                                        seq += "->" + p[j];
                                    }
                                    else {
                                        t = t + res_b[j];
                                        comp[j] = t - a[j];
                                        w[j] = t - b[j]
                                               - a[j];
                                        res_b[j] = 0;
                                        seq += "->" + p[j];
                                    }
                                }
                            }
                        }

                        // now the previous process
                        // according to ith is process
                        if (res_b[i] > 0) {
                            flag = false;

                            // Check for greaters
                            if (res_b[i] > n) {
                                t = t + n;
                                res_b[i] = res_b[i] - n;
                                res_a[i] = res_a[i] + n;
                                seq += "->" + p[i];
                            }
                            else {
                                t = t + res_b[i];
                                comp[i] = t - a[i];
                                w[i] = t - b[i] - a[i];
                                res_b[i] = 0;
                                seq += "->" + p[i];
                            }
                        }
                    }
                }

                // if no process is come on the critical
                else if (res_a[i] > t) {
                    t++;
                    i--;
                }
            }

            // for exit the while loop
            if (flag) {
                break;
            }
        }

        Console.WriteLine("name   ctime   wtime");
        for (int i = 0; i < p.Length; i++) {
            Console.WriteLine(" " + p[i] + "\t" + comp[i]
                              + "\t" + w[i]);

            res = res + w[i];
            resc = resc + comp[i];
        }

        Console.WriteLine("Average waiting time is "
                          + (float)res / p.Length);
        Console.WriteLine("Average compilation time is "
                          + (float)resc / p.Length);
        Console.WriteLine("Sequence is like that " + seq);
    }

    // Driver Code
    public static void Main(String[] args)
    {
        // name of the process
        String[] name = { "p1", "p2", "p3", "p4" };

        // arrival for every process
        int[] arrivaltime = { 0, 1, 2, 3 };

        // burst time for every process
        int[] bursttime = { 10, 4, 5, 3 };

        // quantum time of each process
        int q = 3;

        // cal the function for output
        roundRobin(name, arrivaltime, bursttime, q);
    }
}

// This code is contributed by Rajput-Ji
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//JAVA Program for implementing
//Round Robin Algorithm
// code by Sparsh_cbs
import java.util.*;

public class RoundRobin{
    private static Scanner inp = new Scanner(System.in);
    //Driver Code
    public static void main(String[] args){
        int n,tq, timer = 0, maxProccessIndex = 0;
        float avgWait = 0, avgTT = 0;
        System.out.print("\nEnter the time quanta : ");
        tq = inp.nextInt();
        System.out.print("\nEnter the number of processess : ");
        n = inp.nextInt();
        int arrival[] = new int[n];
        int burst[] = new int[n];
        int wait[] = new int[n];
        int turn[] = new int[n];
        int queue[] = new int[n];
        int temp_burst[] = new int[n];
        boolean complete[] = new boolean[n];

        System.out.print("\nEnter the arrival time of the processess : ");
        for(int i = 0; i < n; i++)
            arrival[i] = inp.nextInt();

        System.out.print("\nEnter the burst time of the processess : ");
        for(int i = 0; i < n; i++){
            burst[i] = inp.nextInt();
            temp_burst[i] = burst[i];
        }

        for(int i = 0; i < n; i++){    //Initializing the queue and complete array
            complete[i] = false;
            queue[i] = 0;
        }
        while(timer < arrival[0])    //Incrementing Timer until the first process arrives
            timer++;
        queue[0] = 1;

        while(true){
            boolean flag = true;
            for(int i = 0; i < n; i++){
                if(temp_burst[i] != 0){
                    flag = false;
                    break;
                }
            }
            if(flag)
                break;

            for(int i = 0; (i < n) && (queue[i] != 0); i++){
                int ctr = 0;
                while((ctr < tq) && (temp_burst[queue[0]-1] > 0)){
                    temp_burst[queue[0]-1] -= 1;
                    timer += 1;
                    ctr++;

                    //Updating the ready queue until all the processes arrive
                    checkNewArrival(timer, arrival, n, maxProccessIndex, queue);
                }
                if((temp_burst[queue[0]-1] == 0) && (complete[queue[0]-1] == false)){
                    turn[queue[0]-1] = timer;        //turn currently stores exit times
                    complete[queue[0]-1] = true;
                }

                  //checks whether or not CPU is idle
                boolean idle = true;
                if(queue[n-1] == 0){
                    for(int k = 0; k < n && queue[k] != 0; k++){
                        if(complete[queue[k]-1] == false){
                            idle = false;
                        }
                    }
                }
                else
                    idle = false;

                if(idle){
                    timer++;
                    checkNewArrival(timer, arrival, n, maxProccessIndex, queue);
                }

                //Maintaining the entries of processes after each premption in the ready Queue
                queueMaintainence(queue,n);
            }
        }

        for(int i = 0; i < n; i++){
            turn[i] = turn[i] - arrival[i];
            wait[i] = turn[i] - burst[i];
        }

        System.out.print("\nProgram No.\tArrival Time\tBurst Time\tWait Time\tTurnAround Time"
                         + "\n");
        for(int i = 0; i < n; i++){
            System.out.print(i+1+"\t\t"+arrival[i]+"\t\t"+burst[i]
                             +"\t\t"+wait[i]+"\t\t"+turn[i]+ "\n");
        }
        for(int i =0; i< n; i++){
            avgWait += wait[i];
            avgTT += turn[i];
        }
        System.out.print("\nAverage wait time : "+(avgWait/n)
                         +"\nAverage Turn Around Time : "+(avgTT/n));
    }
    public static void queueUpdation(int queue[],int timer,int arrival[],int n, int maxProccessIndex){
        int zeroIndex = -1;
        for(int i = 0; i < n; i++){
            if(queue[i] == 0){
                zeroIndex = i;
                break;
            }
        }
        if(zeroIndex == -1)
            return;
        queue[zeroIndex] = maxProccessIndex + 1;
    }

    public static void checkNewArrival(int timer, int arrival[], int n, int maxProccessIndex,int queue[]){
        if(timer <= arrival[n-1]){
            boolean newArrival = false;
            for(int j = (maxProccessIndex+1); j < n; j++){
                if(arrival[j] <= timer){
                    if(maxProccessIndex < j){
                        maxProccessIndex = j;
                        newArrival = true;
                    }
                }
            }
            if(newArrival)    //adds the index of the arriving process(if any)
                queueUpdation(queue,timer,arrival,n, maxProccessIndex);       
        }
    }

    public static void queueMaintainence(int queue[], int n){

        for(int i = 0; (i < n-1) && (queue[i+1] != 0) ; i++){
            int temp = queue[i];
            queue[i] = queue[i+1];
            queue[i+1] = temp;
        }
    }
}
```

**输出:**

```
Enter the time quanta : 2

Enter the number of processess : 4

Enter the arrival time of the processess : 0 1 2 3

Enter the burst time of the processess : 5 4 2 1

Program No.     Arrival Time    Burst Time      Wait Time       TurnAround Time
1               0               5               7               12
2               1               4               6               10
3               2               2               2               4
4               3               1               5               6

Average wait time : 5
Average Turn Around Time : 8
```

如果对代码有任何疑问或问题，请写在注释部分。

**注意:**可以使用 Queue 数据结构对上面实现的代码进行稍微优化，如下所示:

## C++

```
#include <bits/stdc++.h>

using namespace std;

struct Process
{
    int pid;
    int arrivalTime;
    int burstTime;
    int burstTimeRemaining; // the amount of CPU time remaining after each execution
    int completionTime;
    int turnaroundTime;
    int waitingTime;
    bool isComplete;
    bool inQueue;
};

/*
 * At every time quantum or when a process has been executed before the time quantum,
 * check for any new arrivals and push them into the queue
*/
void checkForNewArrivals(Process processes[], const int n, const int currentTime, queue<int> &readyQueue)
{
    for (int i = 0; i < n; i++)
    {
        Process p = processes[i];
        // checking if any processes has arrived
        // if so, push them in the ready Queue.
        if (p.arrivalTime <= currentTime && !p.inQueue && !p.isComplete)
        {
            processes[i].inQueue = true;
            readyQueue.push(i);
        }
    }
}

/*
 * Context switching takes place at every time quantum
 * At every iteration, the burst time of the processes in the queue are handled using this method
*/
void updateQueue(Process processes[], const int n, const int quantum, queue<int> &readyQueue, int ¤tTime, int &programsExecuted)
{
    int i = readyQueue.front();
    readyQueue.pop();

    // if the process is going to be finished executing,
    // ie, when it's remaining burst time is less than time quantum
    // mark it completed and increment the current time
    // and calculate its waiting time and turnaround time
    if (processes[i].burstTimeRemaining <= quantum)
    {
        processes[i].isComplete = true;
        currentTime += processes[i].burstTimeRemaining;
        processes[i].completionTime = currentTime;
        processes[i].waitingTime = processes[i].completionTime - processes[i].arrivalTime - processes[i].burstTime;
        processes[i].turnaroundTime = processes[i].waitingTime + processes[i].burstTime;

        if (processes[i].waitingTime < 0)
            processes[i].waitingTime = 0;

        processes[i].burstTimeRemaining = 0;

        // if all the processes are not yet inserted in the queue,
        // then check for new arrivals
        if (programsExecuted != n)
        {
            checkForNewArrivals(processes, n, currentTime, readyQueue);
        }
    }
    else
    {
        // the process is not done yet. But it's going to be pre-empted
        // since one quantum is used
        // but first subtract the time the process used so far
        processes[i].burstTimeRemaining -= quantum;
        currentTime += quantum;

        // if all the processes are not yet inserted in the queue,
        // then check for new arrivals
        if (programsExecuted != n)
        {
            checkForNewArrivals(processes, n, currentTime, readyQueue);
        }
        // insert the incomplete process back into the queue
        readyQueue.push(i);
    }
}

/*
 * Just a function that outputs the result in terms of their PID.
*/
void output(Process processes[], const int n)
{
    double avgWaitingTime = 0;
    double avgTurntaroundTime = 0;
    // sort the processes array by processes.PID
    sort(processes, processes + n, [](const Process &p1, const Process &p2)
         { return p1.pid < p2.pid; });

    for (int i = 0; i < n; i++)
    {
        cout << "Process " << processes[i].pid << ": Waiting Time: " << processes[i].waitingTime << " Turnaround Time: " << processes[i].turnaroundTime << endl;
        avgWaitingTime += processes[i].waitingTime;
        avgTurntaroundTime += processes[i].turnaroundTime;
    }
    cout << "Average Waiting Time: " << avgWaitingTime / n << endl;
    cout << "Average Turnaround Time: " << avgTurntaroundTime / n << endl;
}

/*
 * This function assumes that the processes are already sorted according to their arrival time
 */
void roundRobin(Process processes[], int n, int quantum)
{
    queue<int> readyQueue;
    readyQueue.push(0); // initially, pushing the first process which arrived first
    processes[0].inQueue = true;

    int currentTime = 0; // holds the current time after each process has been executed
    int programsExecuted = 0; // holds the number of programs executed so far

    while (!readyQueue.empty())
    {
        updateQueue(processes, n, quantum, readyQueue, currentTime, programsExecuted);
    }
}

int main()
{
    int n, quantum;

    cout << "Enter the number of processes: ";
    cin >> n;
    cout << "Enter time quantum: ";
    cin >> quantum;

    Process processes[n + 1];

    for (int i = 0; i < n; i++)
    {
        cout << "Enter arrival time and burst time of each process " << i + 1 << ": ";
        cin >> processes[i].arrivalTime;
        cin >> processes[i].burstTime;
        processes[i].burstTimeRemaining = processes[i].burstTime;
        processes[i].pid = i + 1;
        cout << endl;
    }

    // stl sort in terms of arrival time
    sort(processes, processes + n, [](const Process &p1, const Process &p2)
         { return p1.arrivalTime < p2.arrivalTime; });

    roundRobin(processes, n, quantum);

    output(processes, n);

    return 0;
}
```

```
Enter the number of processes: 4

Enter time quantum: 2

Enter the arrival time and burst time of each process: 
0 5
1 4
2 2
3 1

Process 1: Waiting Time: 7 Turnaround Time: 12
Process 2: Waiting Time: 6 Turnaround Time: 10
Process 3: Waiting Time: 2 Turnaround Time: 4
Process 4: Waiting Time: 5 Turnaround Time: 6

Average Waiting Time: 5
Average Turnaround Time: 8
```