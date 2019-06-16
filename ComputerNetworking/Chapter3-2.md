### Chapter 3 运输层

​	运输层位于应用层和网络层之间，是分层的网络体系结构的重要部分。运输层为运行在不同主机上的应用进程提供直接的通信服务起着至关重要的作用。

#### 3.5  面向连接的运输：TCP

TCP连接：

​	两个进程连接前，必须向“握手”，即它们必须相互发送某些预备报文段，以建立确保数据传输的参数。

​	TCP连接提供   全双工服务。

​	三次握手之后，就建立起了连接，然后开始发送数据。组成包括：两台主机上的缓存、变量与进程连接的套接字。

​	流量控制服务，消除发送方使接收方溢出的可能性。TCP发送方也可能因为ip网络的拥塞而被遏制--拥塞控制。

​	通过让发送方维护一个称为接收窗口的变量来提供流量控制。

TCP报文段结构：

![Image text](http://pt6q77kvw.bkt.clouddn.com/3.5-3.jpg)

​	TCP三次握手：

![Image text](http://pt6q77kvw.bkt.clouddn.com/3.5-1.jpg)

关闭一条TCP连接：

![Image text](http://pt6q77kvw.bkt.clouddn.com/3.5-2.jpg)



客户TCP经历的典型的TCP状态序列：

![Image text](http://pt6q77kvw.bkt.clouddn.com/3.5-4.jpg)

服务器端TCP经历的典型的TCP状态序列：

![Image text](http://pt6q77kvw.bkt.clouddn.com/3.5-5.jpg)