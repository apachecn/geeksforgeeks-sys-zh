# 分层架构中回调的使用

> 原文:[https://www . geeksforgeeks . org/使用分层体系结构中的回调/](https://www.geeksforgeeks.org/use-of-callbacks-in-layered-architecture/)

从网络的 OSI 模型到操作系统，任何日常生活项目都是基于分层架构的。想过上层和下层之间的抽象是如何产生的吗？

都是关于[回调](https://www.geeksforgeeks.org/callbacks-in-c/)。因此，一般来说，上层是为了使事情更简单和更容易使用而创建的(如 SDK)，下层是与网络(对于基于网络的项目)或系统级调用(对于基于操作系统的项目)交互的实际层。因此，我们可以从上层源文件中直接调用在下层定义(并声明)的函数，并通过函数参数传递数据。但是，我们不能只从下层调用上层的函数，因为那样会产生循环依赖。所以，这里[回调](https://www.geeksforgeeks.org/callbacks-in-c/)进入画面。

**回调**是将一个函数通过它的引用作为另一个函数的参数传递，然后通过引用调用它的方式。

假设**上层 c** 和**下层 c** 分别是上层和下层的源文件。**下层 h** 是**下层 c** 的头文件。在**上层 c** 中，首先将 **notify_observer()** 的函数引用作为 **register_callback()** 的参数传递给**下层 c** 。这叫做在底层注册回调。现在下层知道 **notify_observer()** 的函数引用了。 **register_callback()** 函数只是将函数引用存储到全局函数指针 **g_notify_ob** 中，这样文件中的任何函数都可以调用 **notify_observer()** 。现在，每当下层需要向上层传递数据(或需要发送通知)时，只需通过调用 **g_notify_ob()** 来调用 **notify_observer()** 。

下面是上层

```
#include <stdio.h>
#include "lowerlayer.h"

void notify_observer()
{
    printf("Function called by callback\n");
}

int main()
{
    // Calling register_callback function and 
    // passing address of notify_observer as argument
    register_callback(notify_observer);  
    lowerlevelfunction();
}
```

这是 lowerlayer.h .突出显示的行只是表示回调函数的原型，它将作为引用实际传递。原型的基本模板是这样的，

```
typedef <Function return type> (*<Name of the function pointer type>)
                      (<Type of Function arguments separated by comma>)
```

```
// Below is the prototype of the function 
// that will be actually passed by reference 
typedef void (*notify_ob)(void);

void register_callback(notify_ob);

void lowerlevelfunction();
```

这是下层

```
#include "lowerlayer.h"
#define NULL 0

notify_ob g_notify_ob;

// Callback function
void lowerlevelfunction()
{ 
    // Calling back to notify_observer
    g_notify_ob(); 
}

// Callback registration
void register_callback(notify_ob fun)
{
    g_notify_ob = fun;
}
```

如果我们像这样编译和运行这些文件，输出将是这样的。

```
$gcc -c upperlayer.c
$gcc -c lowerlayer.c
$gcc -o exe upperlayer.o lowerlayer.o
$./exe

Output: Function called by callback 
```