# 操作系统中的特殊机器指令

> 原文:[https://www . geesforgeks . org/特殊机器操作系统指令/](https://www.geeksforgeeks.org/special-machine-instructions-in-operating-system/)

***机器指令*** 是机器代码程序或命令。换句话说，用计算机的机器代码编写的命令，它可以识别并随后执行。

***机器码*** 或机器语言是指由一串 1 和 0 组成的计算机编程语言，即二进制码。计算机可以直接响应机器代码，即不需要任何方向或转换。

**特殊机器指令:**

*   These types of instructions usually mean that access to one memory location excludes other access to the same location.
*   Extension: The designer proposed a machine instruction that atomically (inseparably) executes two instructions on the same memory unit.
*   The execution of this instruction is mutually exclusive (even on multiple processors).
*   They can be used to provide mutual exclusion, but they need to be supplemented by other mechanisms to meet other requirements of key solution problems.

以下技术用于关键解决方案问题的硬件:

**1。测试和设置指令:**

将内存位置设置为 1，并返回该位置的前一个值。如果返回值为 1，则表示锁被其他人获取。如果返回值为 0，则锁是自由的，它将被设置为 1。自动测试和修改一个单词的内容

```
int test_and_set (int &target) {
int tmp ;
tmp = target ;
target =1 ;     /* True */
return ( tmp )
}
```

用测试和设置实现互斥:

```
external bool lock (false) ;
do {
while ( test_and_set (lock)) ;      /* Wait for Lock  */
critical_section ( )  ;          
Lock =false ;                 /* release the Lock  */
remainder_section ( ) ;
} while (1) ;
```

**2。交换指令:**

*   Atoms exchange two variables
*   Another variation of test and setting is two Boolean variables.

```
void Swap ( boolean &a , boolean &b ) {
boolean temp = a ;
a= b ;
b = temp ;
}
```

的原子交换

实施:

```
Shared Data :  boolean lock = false ;
Process Pi :
do {
key = true ;
while ( key == true ) 
        Swap ( lock , key ) ;
< critical section >
lock = false ;
< remainder section >
}
```

**3。比较和交换说明:**

将内存位置的值与传递给指令的旧值进行比较。如果两个值匹配，则将新值写入内存位置。使用这条指令，我们将一个存储单元设置为一个特定的值，前提是在读取内容后不对其进行充电。如果他们这样做了，那么我们的新价值就不会被设定。

```
int compare_and_swap (int *x , int old , int new ) {
int save = *x ;           /* current contents of the memory */
if (save == old)     *x = new ;
return save ;          /* tell the caller what was read */
}
```

实施:

```
while ( compare_and_swap ( &locked , 0 , 1 ) != 0 ) ;    /* spin until locked == 0  */
 /* if we got here lock got set to 1 and we have it  */
<Critical Section>
locked = 0 ;      /* release the lock  */
<remainder section>
```

**4。获取和递增指令:**

该指令增加内存位置并返回该位置的前一个值。我们抓住一张票(取加)并等待，直到轮到我们。完成后，我们增加转弯，这样抓住下一张票的线程就可以走了。

```
int fetch_and_increment ( int *x ) {
last_value = *x ;
*x = *x +1 ;
return last_value ;
}
```

返回值对应于我们的票的号码，而机器现在准备生成下一个更高的号码。

实施:

```
ticket = 0 ;     turn = 0  ;
. . .
myturn = fetch_and_increment ( & ticket ) ;
while ( turn !=myturn )    /* Busy wait  */
<Criticcal Section>
fetch_and_increment ( &turn ) ; 
```

可变票号代表机器中的票号，可变 myturn 代表我们的票号，turn 代表当前服务的票号。每次有人通过“取和增”获取票证时，票证的值都会增加。每当有人完成他们的关键部分，并准备好下一个线程的服务，他们增加了回合。