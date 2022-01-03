# Python 多线程套接字编程

> 原文:[https://www . geesforgeks . org/socket-编程-多线程-python/](https://www.geeksforgeeks.org/socket-programming-multi-threading-python/)

*先决条件:[Python 中的 Socket 编程](https://www.geeksforgeeks.org/socket-programming-python/)*[Python 中的多线程](https://www.geeksforgeeks.org/multithreading-python-set-1/)

**套接字编程** - >它帮助我们将客户端连接到服务器。客户端是消息的发送者和接收者，而服务器只是一个对客户端发送的数据进行处理的监听器。

**什么是线？**
线程是一个轻量级的进程，不需要太多的内存开销，它们比进程便宜。

**什么是多线程套接字编程？**
多线程是在单个进程中同时执行多个线程的进程。

**多线程模块:**
A*_ 线程模块&线程模块*用于 python 中的多线程，这些模块有助于同步，并为正在使用的线程提供锁。

```
from _thread import *
import threading

```

锁对象由->创建

```
print_lock = threading.Lock()

```

锁有两种状态，“锁定”或“解锁”。它有两种基本方法:获取()和释放()。当状态解锁时 **print_lock.acquire()** 用于将状态更改为锁定， **print_lock.release()** 用于将状态更改为解锁。

函数**thread . start _ new _ thread()**用于启动一个新线程并返回其标识符。第一个参数是要调用的函数，第二个参数是包含参数位置列表的元组。

让我们通过代码来研究客户机-服务器多线程套接字编程-
*注意:-代码与 python3 一起工作。*

**多线程服务器代码**

```
# import socket programming library
import socket

# import thread module
from _thread import *
import threading

print_lock = threading.Lock()

# thread function
def threaded(c):
    while True:

        # data received from client
        data = c.recv(1024)
        if not data:
            print('Bye')

            # lock released on exit
            print_lock.release()
            break

        # reverse the given string from client
        data = data[::-1]

        # send back reversed string to client
        c.send(data)

    # connection closed
    c.close()

def Main():
    host = ""

    # reverse a port on your computer
    # in our case it is 12345 but it
    # can be anything
    port = 12345
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.bind((host, port))
    print("socket binded to port", port)

    # put the socket into listening mode
    s.listen(5)
    print("socket is listening")

    # a forever loop until client wants to exit
    while True:

        # establish connection with client
        c, addr = s.accept()

        # lock acquired by client
        print_lock.acquire()
        print('Connected to :', addr[0], ':', addr[1])

        # Start a new thread and return its identifier
        start_new_thread(threaded, (c,))
    s.close()

if __name__ == '__main__':
    Main()
```

```
Console Window:
socket binded to port 12345
socket is listening
Connected to : 127.0.0.1 : 11600
Bye

```

**客户端代码**

```
# Import socket module
import socket

def Main():
    # local host IP '127.0.0.1'
    host = '127.0.0.1'

    # Define the port on which you want to connect
    port = 12345

    s = socket.socket(socket.AF_INET,socket.SOCK_STREAM)

    # connect to server on local computer
    s.connect((host,port))

    # message you send to server
    message = "shaurya says geeksforgeeks"
    while True:

        # message sent to server
        s.send(message.encode('ascii'))

        # messaga received from server
        data = s.recv(1024)

        # print the received message
        # here it would be a reverse of sent message
        print('Received from the server :',str(data.decode('ascii')))

        # ask the client whether he wants to continue
        ans = input('\nDo you want to continue(y/n) :')
        if ans == 'y':
            continue
        else:
            break
    # close the connection
    s.close()

if __name__ == '__main__':
    Main()
```

```
Console Window:
Received from the server : skeegrofskeeg syas ayruahs

Do you want to continue(y/n) :y
Received from the server : skeegrofskeeg syas ayruahs

Do you want to continue(y/n) :n

Process finished with exit code 0

```

参考->
[https://docs.python.org/2/library/thread.html](https://docs.python.org/2/library/thread.html)

本文由 **[SHAURYA UPPAL](https://www.linkedin.com/in/shaurya-uppal-3b7a6373/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。