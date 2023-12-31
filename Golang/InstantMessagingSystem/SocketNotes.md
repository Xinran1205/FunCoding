# Socket 
首先，程序员其实不需要关注应用层以下的层，这些层由内核封装好了    
其次，在应用层我们可以不对数据打包（不加应用层协议），直接发送  
也可以在应用层加上应用层协议，接收端按照指定的应用层协议解析数据

https://subingwen.cn/linux/socket/

inet_pton()函数将点分十进制的IP地址转换为网络字节序的整数表示的IP地址  
inet_ntop()函数将网络字节序的整数表示的IP地址转换为点分十进制的IP地址  

**很重要：方便理解套接字编程**
在Java Web开发中，后端使用的是Servlet容器，比如Tomcat、Jetty等，它们内部实现了基于套接字的网络通信。  
当浏览器向服务器发送HTTP请求时，Servlet容器会使用套接字与浏览器建立连接，并处理HTTP请求，最终将HTTP响应发送回浏览器。  
在前端，我们通常使用JavaScript库（如axios）来发送HTTP请求。这些库会将HTTP请求发送到后端服务器的特定端口，并使用套接字与服务器进行通信，以获取HTTP响应。  
因此，虽然前端代码本身并没有直接使用套接字编程，但它们在底层使用了套接字进行网络通信。
在Java Web开发中，开发人员通常不需要直接使用套接字编程，因为Servlet容器已经为开发人员提供了高层次的API，可以方便地处理HTTP请求和响应。  
但在某些情况下，比如需要开发自定义的网络协议或实现非标准的网络通信方式时，套接字编程可能是必要的。 

HTTP是一种应用层协议，它是在TCP协议之上实现的，并且通常使用HTTP的默认端口80或443。
在前端向后端发送HTTP请求时，使用的是HTTP协议，而不是直接使用套接字编程。
HTTP协议定义了一组规则，用于在客户端和服务器之间传输数据。当你使用axios发送HTTP请求时，它会自动处理HTTP协议的细节，
包括建立TCP连接、发送请求、接收响应等，这些都是由axios库内部实现的，你不需要手动编写套接字代码来完成这些操作。
套接字编程通常被用于实现更底层的网络通信，例如在应用层协议之上实现自定义协议，
或在网络层协议之上实现更高级别的应用层协议。使用套接字编程可以更加灵活地控制数据传输的细节 
但也需要编写更多的代码来处理网络通信的各个方面。因此，当你只需使用HTTP协议进行简单的请求响应时，使用现成的HTTP库是更为方便和高效的做法。  

当你需要实现自定义网络协议或在更底层的网络层上进行网络通信时，可能需要使用套接字编程。套接字编程可以提供更底层的网络控制，允许你直接控制数据传输的细节，如数据包的大小和格式、数据包的序列化和反序列化、错误处理等，因此可以更加灵活地定制网络通信。
举个例子，假设你需要开发一个实时游戏，需要实现实时的多人同步。这时候使用HTTP协议进行通信可能会带来较高的延迟和不稳定性，因为HTTP协议是基于TCP协议实现的，而TCP协议在传输数据时会进行一些额外的包头和序列号等控制信息的添加，这些额外的控制信息会增加数据传输的延迟和网络负载，从而降低实时性。
此时，使用套接字编程可以自定义一个更加轻量级的协议，去除掉不必要的控制信息，从而提高实时性和稳定性。
套接字编程的优点是可以提供更加灵活的网络控制，但也需要更多的编程工作来处理网络通信的各个方面。在大多数情况下，使用现成的网络库或框架可以更加高效和方便地完成网络通信的任务。只有在特定的需求场景下，才需要使用套接字编程。
当你需要在底层网络层实现自定义协议、需要使用UDP协议进行数据传输、需要实现高性能的网络通信时，可能需要使用套接字编程。此外，在某些操作系统或设备上，可能无法使用现成的网络库或框架，这时候也需要使用套接字编程。