# 生产者消费者问题及其 C++实现

> 原文:[https://www . geesforgeks . org/producer-consumer-problem-and-it-implementation-with-c/](https://www.geeksforgeeks.org/producer-consumer-problem-and-its-implementation-with-c/)

**概述:**
在本文中，我们将讨论[生产者-消费者问题](https://www.geeksforgeeks.org/producer-consumer-problem-using-semaphores-set-1/)及其 C++实现。生产者-消费者问题是一个经典的两过程同步问题。我们一个一个来讨论。

**问题表述:**
生产者-消费者问题中有一个生产者，一个消费者。

1.  **生产者–**
    生产者进程执行一组 int produce 语句来创建一个数据元素，并将其存储在缓冲区中。
2.  **Consumer–**
    如果缓冲区有项目，则一个 Consumer 进程执行一个以数据元素为参数的语句 consume。

**解决方案:**
出现问题是因为流程不同步，因此生产和消费的物品可能不一致。为了解决这个问题，我们使用信号量来解决这个问题，即临界区问题。

**c++中的实现:**
这个问题可以进一步细分为以下两部分。

**Part-1:其中缓冲区大小是无限的–**
在这种情况下，生产者存储商品和消费者消费商品的缓冲区大小不是固定的。

## C++14

```
#include<bits/stdc++.h>
#include<pthread.h>
#include<semaphore.h>
#include <unistd.h> 
using namespace std;

// Declaration
int r1,total_produced=0,total_consume=0;

// Semaphore declaration
sem_t notEmpty;

// Producer Section
void* produce(void *arg){
    while(1){
      cout<<"Producer produces item."<<endl;
      cout<<"Total produced = "<<++total_produced<<
        " Total consume = "<<total_consume*-1<<endl;
      sem_post(¬Empty);    
      sleep(rand()%100*0.01);
    }
}

// Consumer Section
void* consume(void *arg){
    while(1){
      sem_wait(¬Empty);
      cout<<"Consumer consumes item."<<endl;    
      cout<<"Total produced = "<<total_produced<<
        " Total consume = "<<(--total_consume)*-1<<endl;
      sleep(rand()%100*0.01);
    }    
}

int main(int argv,char *argc[]){

    // thread declaration
    pthread_t producer,consumer;

    // Declaration of attribute......
    pthread_attr_t attr;

    // semaphore initialization
    sem_init(¬Empty,0,0);

    // pthread_attr_t initialization
    pthread_attr_init(&attr);
    pthread_attr_setdetachstate(&attr,PTHREAD_CREATE_JOINABLE);

    // Creation of process
    r1=pthread_create(&producer,&attr,produce,NULL);
    if(r1){
      cout<<"Error in creating thread"<<endl;
      exit(-1);
    }

    r1=pthread_create(&consumer,&attr,consume,NULL);
    if(r1){
      cout<<"Error in creating thread"<<endl;
      exit(-1);
    }

    // destroying the pthread_attr
    pthread_attr_destroy(&attr);

    // Joining the thread
    r1=pthread_join(producer,NULL);
    if(r1){
      cout<<"Error in joining thread"<<endl;
      exit(-1);
    }

    r1=pthread_join(consumer,NULL);
    if(r1){
      cout<<"Error in joining thread"<<endl;
      exit(-1);
    }

    // Exiting thread
    pthread_exit(NULL);

    return 0;
}
```

**Part-2:其中缓冲区大小是固定的或有限的–**
在这种情况下，生产者存储项目和消费者消费项目大小的缓冲区是固定的。

## C++14

```
#include <bits/stdc++.h>
#include <pthread.h>
#include <semaphore.h>
#include <unistd.h>
using namespace std;

// Declaration
int r1, items = 0;

// Semaphore declaration
sem_t notEmpty, notFull;

// Producer Section
void* produce(void* arg)
{
    while (1) {
        sem_wait(¬Full);
        sleep(rand() % 100 * 0.01);
        cout << 
      "Producer produces item.Items Present = "
             << ++items << endl;
        sem_post(¬Empty);
        sleep(rand() % 100 * 0.01);
    }
}

// Consumer Section
void* consume(void* arg)
{
    while (1) {
        sem_wait(¬Empty);
        sleep(rand() % 100 * 0.01);
        cout << 
     "Consumer consumes item.Items Present = "
             << --items << endl;
        sem_post(¬Full);
        sleep(rand() % 100 * 0.01);
    }
}

int main(int argv, char* argc[])
{

    int N;
    cout << 
      "Enter the capacity of the buffer" << endl;
    cin >> N;

    // thread declaration
    pthread_t producer, consumer;

    // Declaration of attribute......
    pthread_attr_t attr;

    // semaphore initialization
    sem_init(¬Empty, 0, 0);
    sem_init(¬Full, 0, N);

    // pthread_attr_t initialization
    pthread_attr_init(&attr);
    pthread_attr_setdetachstate(&attr,
             PTHREAD_CREATE_JOINABLE);

    // Creation of process
    r1 = pthread_create(&producer, &attr, 
                        produce, NULL);
    if (r1) {
        cout << 
          "Error in creating thread" << endl;
        exit(-1);
    }

    r1 = pthread_create(&consumer, &attr, 
                        consume, NULL);
    if (r1) {
        cout << 
          "Error in creating thread" << endl;
        exit(-1);
    }

    // destroying the pthread_attr
    pthread_attr_destroy(&attr);

    // Joining the thread
    r1 = pthread_join(producer, NULL);
    if (r1) {
        cout << "Error in joining thread" << endl;
        exit(-1);
    }

    r1 = pthread_join(consumer, NULL);
    if (r1) {
        cout << "Error in joining thread" << endl;
        exit(-1);
    }

    // Exiting thread
    pthread_exit(NULL);

    return 0;
}
```