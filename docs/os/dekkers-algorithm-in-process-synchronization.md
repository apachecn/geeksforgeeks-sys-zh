# 德克尔在进程同步中的算法

> 原文:[https://www . geesforgeks . org/dekkers-进程中算法-同步/](https://www.geeksforgeeks.org/dekkers-algorithm-in-process-synchronization/)

先决条件–[进程同步](https://www.geeksforgeeks.org/process-synchronization-set-1/)、[进程间通信](https://www.geeksforgeeks.org/inter-process-communication/)
为了获得这样的互斥、有界等待和进度，已经实现了几种算法，其中之一是德克尔算法。为了理解算法，让我们先来理解临界区问题的解决方案。
工艺一般表示为:

```
do {
    //entry section
        critical section
    //exit section
        remainder section
} while (TRUE);
```

临界截面问题的解决必须保证以下三个条件:

1.  互斥现象
2.  进步
3.  有界等待

确保上述所有因素的解决方案之一是[彼得森的解决方案](https://www.geeksforgeeks.org/petersons-algorithm-for-mutual-exclusion-set-1/)。
另一个是**德克尔的解决方案**。德克尔的算法是对临界区问题的第一个可证明正确的解决方案。它允许两个线程共享单次使用的资源而不会发生冲突，只使用共享内存进行通信。它避免了天真的话轮转换算法的严格交替，是最早发明的互斥算法之一。
虽然德克尔的解决方案有很多版本，但最终或第五个版本是满足上述所有条件的版本，也是所有版本中效率最高的版本。
**注意–**这里提到的德克尔的解决方案只保证了两个进程之间的互斥，通过适当使用数组和变量，它可以扩展到两个以上的进程。
**算法–**它需要一个布尔值数组和一个整型变量:

```
var flag: array [0..1] of boolean;
turn: 0..1;
repeat

        flag[i] := true;
        while flag[j] do
                if turn = j then
                begin
                        flag[i] := false;
                        while turn = j do no-op;
                        flag[i] := true;
                end;

                critical section

        turn := j;
        flag[i] := false;

                remainder section

until false;
```

**德克尔解决方案第一版–**想法是在进程之间使用公共或共享线程号，如果共享线程指示前一个进程已经在运行，则阻止另一个进程进入其关键部分。

## 卡片打印处理机（Card Print Processor 的缩写）

```
Main()
{

    int thread_number = 1;
    startThreads();
}

Thread1()
{
    do {

        // entry section
        // wait until threadnumber is 1
        while (threadnumber == 2)
            ;

        // critical section

        // exit section
        // give access to the other thread
        threadnumber = 2;

        // remainder section

    } while (completed == false)
}

Thread2()
{

    do {

        // entry section
        // wait until threadnumber is 2
        while (threadnumber == 1)
            ;

        // critical section

        // exit section
        // give access to the other thread
        threadnumber = 1;

        // remainder section

    } while (completed == false)
}
```

## 蟒蛇 3

```
def Thread1():
    doWhile=False
    while not completed or not doWhile:
        doWhile=True
        # entry section
        # wait until threadnumber is 1
        while (threadnumber == 2):
            pass

        # critical section

        # exit section
        # give access to the other thread
        threadnumber = 2

        # remainder section

def Thread2():
    doWhile=False
    while not completed or not doWhile:
        doWhile=True
        # entry section
        # wait until threadnumber is 2
        while (threadnumber == 1):
            pass

        # critical section

        # exit section
        # give access to the other thread
        threadnumber = 1

        # remainder section

if __name__ == '__main__':

    thread_number = 1
    startThreads()
```

上述实现中出现的问题是锁步同步，即每个线程都依赖于另一个线程来执行。如果其中一个进程完成了，那么第二个进程运行，给出对已完成的进程的访问并等待轮到它，然而，前一个进程已经完成，永远不会运行以将访问返回给后一个进程。因此，第二个过程无限等待。
**德克尔解决方案的第二个版本–**为了移除锁步同步，它使用两个标志来指示其当前状态，并在入口和出口部分相应地更新它们。

## 卡片打印处理机（Card Print Processor 的缩写）

```
Main()
{

    // flags to indicate if each thread is in
    // its critical section or not.
    boolean thread1 = false;
    boolean thread2 = false;

    startThreads();
}

Thread1()
{

    do {

        // entry section
        // wait until thread2 is in its critical section
        while (thread2 == true)
            ;

        // indicate thread1 entering its critical section
        thread1 = true;

        // critical section

        // exit section
        // indicate thread1 exiting its critical section
        thread1 = false;

        // remainder section

    } while (completed == false)
}

Thread2()
{

    do {

        // entry section
        // wait until thread1 is in its critical section
        while (thread1 == true)
            ;

        // indicate thread2 entering its critical section
        thread2 = true;

        // critical section

        // exit section
        // indicate thread2 exiting its critical section
        thread2 = false;

        // remainder section

    } while (completed == false)
}
```

## 蟒蛇 3

```
def Thread1():
    doWhile=False
    while not completed or not doWhile:
        doWhile=True
        # entry section
        # wait until thread2 is in its critical section
        while (thread2):
            pass

        # indicate thread1 entering its critical section
        thread1 = True

        # critical section

        # exit section
        # indicate thread1 exiting its critical section
        thread1 = False

        # remainder section

def Thread2():
    doWhile=False
    while not completed or not doWhile:
        doWhile=True
        # entry section
        # wait until thread1 is in its critical section
        while (thread1):
            pass

        # indicate thread1 entering its critical section
        thread2 = True

        # critical section

        # exit section
        # indicate thread2 exiting its critical section
        thread2 = False

        # remainder section

if __name__ == '__main__':

    # flags to indicate if each thread is in
    # its critical section or not.
    thread1 = False
    thread2 = False

    startThreads()
```

上述版本中出现的问题是互斥本身。如果在标志更新期间(即 current_thread = true 期间)线程被抢占(停止)，那么一旦被抢占的线程被重新启动，两个线程都进入它们的临界区，当两个标志都为 false 时，在开始本身也可以观察到同样的情况。
**德克尔解决方案的第三个版本–**为了重新确保互斥，它在入口部分本身之前设置了标志。

## C++

```
Main()
{

    // flags to indicate if each thread is in
    // queue to enter its critical section
    boolean thread1wantstoenter = false;
    boolean thread2wantstoenter = false;

    startThreads();
}

Thread1()
{

    do {

        thread1wantstoenter = true;

        // entry section
        // wait until thread2 wants to enter
        // its critical section
        while (thread2wantstoenter == true)
            ;

        // critical section

        // exit section
        // indicate thread1 has completed
        // its critical section
        thread1wantstoenter = false;

        // remainder section

    } while (completed == false)
}

Thread2()
{

    do {

        thread2wantstoenter = true;

        // entry section
        // wait until thread1 wants to enter
        // its critical section
        while (thread1wantstoenter == true)
            ;

        // critical section

        // exit section
        // indicate thread2 has completed
        // its critical section
        thread2wantstoenter = false;

        // remainder section

    } while (completed == false)
}
```

## 蟒蛇 3

```
if __name__=='__main__':
    # flags to indicate if each thread is in
    # queue to enter its critical section
    thread1wantstoenter = False
    thread2wantstoenter = False

    startThreads()

def Thread1():
    doWhile=False
    while (completed == False or not doWhile):
        doWhile=True
        thread1wantstoenter = True

        # entry section
        # wait until thread2 wants to enter
        # its critical section
        while (thread2wantstoenter == True):
            pass

        # critical section

        # exit section
        # indicate thread1 has completed
        # its critical section
        thread1wantstoenter = False

        # remainder section

def Thread2():
    doWhile=False
    while (completed == False or not doWhile) :
        doWhile=True
        thread2wantstoenter = True

        # entry section
        # wait until thread1 wants to enter
        # its critical section
        while (thread1wantstoenter == True):
            pass

        # critical section

        # exit section
        # indicate thread2 has completed
        # its critical section
        thread2wantstoenter = False

        # remainder section
```

这个版本的问题是死锁的可能性。两个线程可以同时将它们的标志设置为真，并且两个线程都将无限期地等待。
**德克尔解决方案的第四个版本–**使用小时间间隔来重新检查条件，消除死锁并确保互斥。

## 卡片打印处理机（Card Print Processor 的缩写）

```
Main()
{

    // flags to indicate if each thread is in
    // queue to enter its critical section
    boolean thread1wantstoenter = false;
    boolean thread2wantstoenter = false;

    startThreads();
}

Thread1()
{

    do {

        thread1wantstoenter = true;

        while (thread2wantstoenter == true) {

            // gives access to other thread
            // wait for random amount of time
            thread1wantstoenter = false;

            thread1wantstoenter = true;
        }

        // entry section
        // wait until thread2 wants to enter
        // its critical section

        // critical section

        // exit section
        // indicate thread1 has completed
        // its critical section
        thread1wantstoenter = false;

        // remainder section

    } while (completed == false)
}

Thread2()
{

    do {

        thread2wantstoenter = true;

        while (thread1wantstoenter == true) {

            // gives access to other thread
            // wait for random amount of time
            thread2wantstoenter = false;

            thread2wantstoenter = true;
        }

        // entry section
        // wait until thread1 wants to enter
        // its critical section

        // critical section

        // exit section
        // indicate thread2 has completed
        // its critical section
        thread2wantstoenter = false;

        // remainder section

    } while (completed == false)
}
```

## 蟒蛇 3

```
if __name__ == '__main__':

    # flags to indicate if each thread is in
    # queue to enter its critical section
    thread1wantstoenter = False
    thread2wantstoenter = False

    startThreads()

def Thread1():
    doWhile=False
    while (completed == False or not doWhile):
        doWhile=True
        thread1wantstoenter = True

        while (thread2wantstoenter == True) :

            # gives access to other thread
            # wait for random amount of time
            thread1wantstoenter = False

            thread1wantstoenter = True

        # entry section
        # wait until thread2 wants to enter
        # its critical section

        # critical section

        # exit section
        # indicate thread1 has completed
        # its critical section
        thread1wantstoenter = False

        # remainder section

def Thread2():
    doWhile=False
    while (completed == False or not doWhile):
        doWhile=True
        thread2wantstoenter = True

        while (thread1wantstoenter == True) :

            # gives access to other thread
            # wait for random amount of time
            thread2wantstoenter = False

            thread2wantstoenter = True

        # entry section
        # wait until thread1 wants to enter
        # its critical section

        # critical section

        # exit section
        # indicate thread2 has completed
        # its critical section
        thread2wantstoenter = False

        # remainder section
```

这个版本的问题是无限延期。此外，随机的时间量是不稳定的，取决于算法被实现的情况，因此在关键业务系统中不是可接受的解决方案。
**德克尔的算法:最终和完整的解决方案–**-想法是使用偏好的线程概念来确定关键部分的入口。受青睐的线程在提供互斥并避免死锁、无限延期或锁步同步的线程之间交替。

## 卡片打印处理机（Card Print Processor 的缩写）

```
Main()
{

    // to denote which thread will enter next
    int favouredthread = 1;

    // flags to indicate if each thread is in
    // queue to enter its critical section
    boolean thread1wantstoenter = false;
    boolean thread2wantstoenter = false;

    startThreads();
}

Thread1()
{
    do {

        thread1wantstoenter = true;

        // entry section
        // wait until thread2 wants to enter
        // its critical section
        while (thread2wantstoenter == true) {

            // if 2nd thread is more favored
            if (favaouredthread == 2) {

                // gives access to other thread
                thread1wantstoenter = false;

                // wait until this thread is favored
                while (favouredthread == 2)
                    ;

                thread1wantstoenter = true;
            }
        }

        // critical section

        // favor the 2nd thread
        favouredthread = 2;

        // exit section
        // indicate thread1 has completed
        // its critical section
        thread1wantstoenter = false;

        // remainder section

    } while (completed == false)
}

Thread2()
{

    do {

        thread2wantstoenter = true;

        // entry section
        // wait until thread1 wants to enter
        // its critical section
        while (thread1wantstoenter == true) {

            // if 1st thread is more favored
            if (favaouredthread == 1) {

                // gives access to other thread
                thread2wantstoenter = false;

                // wait until this thread is favored
                while (favouredthread == 1)
                    ;

                thread2wantstoenter = true;
            }
        }

        // critical section

        // favour the 1st thread
        favouredthread = 1;

        // exit section
        // indicate thread2 has completed
        // its critical section
        thread2wantstoenter = false;

        // remainder section

    } while (completed == false)
}
```

## 蟒蛇 3

```
if __name__ == '__main__':

    # to denote which thread will enter next
    favouredthread = 1

    # flags to indicate if each thread is in
    # queue to enter its critical section
    thread1wantstoenter = False
    thread2wantstoenter = False

    startThreads()

def Thread1():
    doWhile=False
    while (completed == False or not doWhile) :
        doWhile=True
        thread1wantstoenter = True

        # entry section
        # wait until thread2 wants to enter
        # its critical section
        while (thread2wantstoenter == True) :

            # if 2nd thread is more favored
            if (favaouredthread == 2) :

                # gives access to other thread
                thread1wantstoenter = False

                # wait until this thread is favored
                while (favouredthread == 2):
                    pass

                thread1wantstoenter = True

        # critical section

        # favor the 2nd thread
        favouredthread = 2

        # exit section
        # indicate thread1 has completed
        # its critical section
        thread1wantstoenter = False

        # remainder section

def Thread2():
    doWhile=False
    while (completed == False or not doWhile) :
        doWhile=True
        thread2wantstoenter = True

        # entry section
        # wait until thread1 wants to enter
        # its critical section
        while (thread1wantstoenter == True) :

            # if 1st thread is more favored
            if (favaouredthread == 1) :

                # gives access to other thread
                thread2wantstoenter = False

                # wait until this thread is favored
                while (favouredthread == 1):
                    pass

                thread2wantstoenter = True

        # critical section

        # favour the 1st thread
        favouredthread = 1

        # exit section
        # indicate thread2 has completed
        # its critical section
        thread2wantstoenter = False

        # remainder section

```

这个版本保证了关键解决方案问题的完整解决方案。
**参考资料–**
[德克尔的算法-csisdmz.ul.ie](http://garryowen.csisdmz.ul.ie/~cs4023/resources/oth9.pdf)
[德克尔的算法–维基百科](https://en.wikipedia.org/wiki/Dekker%27s_algorithm)