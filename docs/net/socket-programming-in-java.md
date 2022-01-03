# Java 中的套接字编程

> 原文:[https://www.geeksforgeeks.org/socket-programming-in-java/](https://www.geeksforgeeks.org/socket-programming-in-java/)

本文描述了一个非常基本的单向客户机和服务器设置，其中客户机连接，向服务器发送消息，服务器使用套接字连接显示消息。要让这些东西发挥作用，有很多低级的东西需要发生，但是 Java API 网络包(java.net)解决了所有这些问题，使得网络编程对程序员来说非常容易。

**客户端编程**

**建立插座连接**

要连接到另一台机器，我们需要一个插座连接。套接字连接意味着两台机器拥有关于彼此网络位置(IP 地址)和 TCP 端口的信息。java.net.Socket 类表示一个 Socket。要打开插座:

```
Socket socket = new Socket(“127.0.0.1”, 5000)
```

*   第一个参数–**服务器**的 IP 地址。(127.0.0.1 是 localhost 的 IP 地址，代码将在单机上运行)。
*   第二个参数–**TCP 端口**。(只是一个代表在服务器上运行哪个应用程序的数字。例如，HTTP 在端口 80 上运行。端口号可以从 0 到 65535)

**通信**
要通过套接字连接进行通信，流用于输入和输出数据。

**关闭连接**

一旦消息被发送到服务器，套接字连接就被显式关闭。

*在程序中，客户端不断读取用户的输入，并将其发送到服务器，直到键入“Over”。*

**Java 实现**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program for a Client
import java.net.*;
import java.io.*;

public class Client
{
    // initialize socket and input output streams
    private Socket socket            = null;
    private DataInputStream  input   = null;
    private DataOutputStream out     = null;

    // constructor to put ip address and port
    public Client(String address, int port)
    {
        // establish a connection
        try
        {
            socket = new Socket(address, port);
            System.out.println("Connected");

            // takes input from terminal
            input  = new DataInputStream(System.in);

            // sends output to the socket
            out    = new DataOutputStream(socket.getOutputStream());
        }
        catch(UnknownHostException u)
        {
            System.out.println(u);
        }
        catch(IOException i)
        {
            System.out.println(i);
        }

        // string to read message from input
        String line = "";

        // keep reading until "Over" is input
        while (!line.equals("Over"))
        {
            try
            {
                line = input.readLine();
                out.writeUTF(line);
            }
            catch(IOException i)
            {
                System.out.println(i);
            }
        }

        // close the connection
        try
        {
            input.close();
            out.close();
            socket.close();
        }
        catch(IOException i)
        {
            System.out.println(i);
        }
    }

    public static void main(String args[])
    {
        Client client = new Client("127.0.0.1", 5000);
    }
}
```

**服务器编程**

**建立插座连接**

要编写一个服务器应用程序，需要两个套接字。

*   等待客户端请求的服务器套接字(当客户端创建新套接字时())
*   用于与客户端通信的普通旧套接字套接字。

**通信**
getOutputStream()方法用于通过套接字发送输出。

**关闭连接**
完成后，通过关闭套接字和输入/输出流来关闭连接非常重要。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program for a Server
import java.net.*;
import java.io.*;

public class Server
{
    //initialize socket and input stream
    private Socket          socket   = null;
    private ServerSocket    server   = null;
    private DataInputStream in       =  null;

    // constructor with port
    public Server(int port)
    {
        // starts server and waits for a connection
        try
        {
            server = new ServerSocket(port);
            System.out.println("Server started");

            System.out.println("Waiting for a client ...");

            socket = server.accept();
            System.out.println("Client accepted");

            // takes input from the client socket
            in = new DataInputStream(
                new BufferedInputStream(socket.getInputStream()));

            String line = "";

            // reads message from client until "Over" is sent
            while (!line.equals("Over"))
            {
                try
                {
                    line = in.readUTF();
                    System.out.println(line);

                }
                catch(IOException i)
                {
                    System.out.println(i);
                }
            }
            System.out.println("Closing connection");

            // close connection
            socket.close();
            in.close();
        }
        catch(IOException i)
        {
            System.out.println(i);
        }
    }

    public static void main(String args[])
    {
        Server server = new Server(5000);
    }
}
```

**要点**

*   服务器应用程序在一个 5000 的特定端口上建立一个服务器套接字。这将启动我们的服务器，监听来自端口 5000 的客户端请求。
*   然后服务器创建一个新的套接字与客户端通信。

```
socket = server.accept()
```

*   accept()方法阻塞(只是停留在那里)直到客户端连接到服务器。
*   然后我们使用 getInputStream()方法从套接字获取输入。我们的服务器不断接收消息，直到客户端发送“结束”。
*   完成后，我们通过关闭套接字和输入流来关闭连接。
*   要在您的计算机上运行客户机和服务器应用程序，请编译这两个应用程序。然后首先运行服务器应用程序，然后运行客户端应用程序。

**在终端或命令提示符下运行**

打开两个窗口，一个用于服务器，另一个用于客户端

1.首先运行服务器应用程序，

```
$ java Server
```

服务器启动
等待客户端…

2.然后在另一个终端上运行客户端应用程序，

```
$ java Client
```

它将显示–已连接，服务器接受客户端，并显示，
客户端接受

3.然后，您可以开始在客户端窗口中键入消息。以下是对客户端的示例输入

```
Hello
I made my first socket connection
Over
```

服务器同时接收和显示，

```
Hello
I made my first socket connection
Over
Closing connection
```

请注意，发送“Over”会关闭客户机和服务器之间的连接，就像前面所说的那样。

**如果你正在使用 Eclipse 或者类似的东西-**

1.  在两个不同的终端或标签上编译它们
2.  首先运行服务器程序
3.  然后运行客户端程序
4.  在客户端窗口中键入将由服务器窗口同时接收和显示的消息。
5.  键入结束。

本文由 **Souradeep Barua** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。