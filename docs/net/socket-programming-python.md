# Python 中的套接字编程

> 原文:[https://www.geeksforgeeks.org/socket-programming-python/](https://www.geeksforgeeks.org/socket-programming-python/)

套接字编程是连接网络上两个节点相互通信的一种方式。一个套接字(节点)监听某个 IP 的特定端口，而另一个套接字则与另一个套接字建立连接。服务器形成侦听器套接字，而客户端则连接到服务器。
他们才是网页浏览背后真正的中坚力量。简单来说，有一个服务器和一个客户端。
socket 编程是通过导入 Socket 库，制作一个简单的 Socket 开始的。

```
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

这里我们创建了一个套接字实例，并向它传递了两个参数。第一个参数是 **AF_INET** ，第二个参数是 **SOCK_STREAM** 。AF_INET 指的是地址族 ipv4。SOCK_STREAM 表示面向连接的 TCP 协议。
现在我们可以使用这个套接字连接到服务器

### **连接到服务器:**

请注意，如果在创建套接字的过程中出现任何错误，那么套接字。错误被抛出，我们只能通过知道一个服务器的 IP 来连接它。您可以通过以下方式找到服务器的 IP 地址:

```
$ ping www.google.com
```

您也可以使用 python 找到该 IP:

```
import socket 

ip = socket.gethostbyname('www.google.com')
print ip
```

下面是一个连接到谷歌的脚本示例。

## 蟒蛇 3

```
# An example script to connect to Google using socket
# programming in Python
import socket # for socket
import sys

try:
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    print ("Socket successfully created")
except socket.error as err:
    print ("socket creation failed with error %s" %(err))

# default port for socket
port = 80

try:
    host_ip = socket.gethostbyname('www.google.com')
except socket.gaierror:

    # this means could not resolve the host
    print ("there was an error resolving the host")
    sys.exit()

# connecting to the server
s.connect((host_ip, port))

print ("the socket has successfully connected to google")
```

**输出:**

```
Socket successfully created
the socket has successfully connected to google 
on port == 173.194.40.19
```

*   首先，我们做了一个插座。
*   然后我们解析了谷歌的知识产权，最后，我们连接到了谷歌。
*   现在我们需要知道如何通过套接字发送一些数据。
*   为了发送数据，套接字库具有*发送所有*功能。此功能允许您向套接字连接的服务器发送数据，服务器也可以使用此功能向客户端发送数据。

### **一个简单的服务器-客户端程序:**

**服务器:**

服务器有一个 bind()方法，将它绑定到一个特定的 IP 和端口，这样它就可以监听该 IP 和端口上的传入请求。服务器有一个 listen()方法，它将服务器置于侦听模式。这允许服务器监听传入的连接。最后，服务器有一个 accept()和 close()方法。accept 方法启动与客户端的连接，close 方法关闭与客户端的连接。

## 蟒蛇 3

```
# first of all import the socket library
import socket            

# next create a socket object
s = socket.socket()        
print ("Socket successfully created")

# reserve a port on your computer in our
# case it is 12345 but it can be anything
port = 12345               

# Next bind to the port
# we have not typed any ip in the ip field
# instead we have inputted an empty string
# this makes the server listen to requests
# coming from other computers on the network
s.bind(('', port))        
print ("socket binded to %s" %(port))

# put the socket into listening mode
s.listen(5)    
print ("socket is listening")           

# a forever loop until we interrupt it or
# an error occurs
while True:

# Establish connection with client.
  c, addr = s.accept()    
  print ('Got connection from', addr )

  # send a thank you message to the client. encoding to send byte type.
  c.send('Thank you for connecting'.encode())

  # Close the connection with the client
  c.close()

  # Breaking once connection closed
  break
```

*   首先，我们导入必要的套接字。
*   然后我们制作了一个套接字对象，并在我们的电脑上预留了一个端口。
*   之后，我们将服务器绑定到指定的端口。传递空字符串意味着服务器也可以监听来自其他计算机的传入连接。如果我们通过了 127.0.0.1，那么它将只监听本地计算机内的那些呼叫。
*   之后，我们将服务器置于监听模式。5 这里的意思是，如果服务器忙，5 个连接保持等待，如果第 6 个套接字试图连接，则连接被拒绝。
*   最后，我们做一个 while 循环，开始接受所有传入的连接，并在向所有连接的套接字发送感谢消息后关闭这些连接。

**客户端:**
现在我们需要一个服务器可以与之交互的东西。我们可以像这样对服务器进行特殊化，只是为了知道我们的服务器正在工作。在终端中键入以下命令:

```
# start the server
$ python server.py

# keep the above terminal open 
# now open another terminal and type: 

$ telnet localhost 12345
```

如果无法识别“telnet”。在 windows 上搜索 windows 功能并打开“telnet 客户端”功能。

**输出:**

```
# in the server.py terminal you will see
# this output:
Socket successfully created
socket binded to 12345
socket is listening
Got connection from ('127.0.0.1', 52617)
```

```
# In the telnet terminal you will get this:
Trying ::1...
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
Thank you for connectingConnection closed by foreign host.
```

这个输出显示我们的服务器正在工作。
现在对于客户端:

## 蟒蛇 3

```
# Import socket module
import socket            

# Create a socket object
s = socket.socket()        

# Define the port on which you want to connect
port = 12345               

# connect to the server on local computer
s.connect(('127.0.0.1', port))

# receive data from the server and decoding to get the string.
print (s.recv(1024).decode())
# close the connection
s.close()    

```

*   首先，我们制作一个 socket 对象。
*   然后，我们在端口 12345(我们的服务器运行的端口)上连接到 localhost，最后，我们从服务器接收数据并关闭连接。
*   现在将此文件保存为 client.py，并在启动服务器脚本后从终端运行它。

```
# start the server:
$ python server.py
Socket successfully created
socket binded to 12345
socket is listening
Got connection from ('127.0.0.1', 52617)
```

```
# start the client:
$ python client.py
Thank you for connecting
```

参考: [Python Socket 编程](https://pythontips.com/2013/08/06/python-socket-network-programming/)
本文由 [**Kishlay 维尔马**](https://www.linkedin.com/in/kishlayverma/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。