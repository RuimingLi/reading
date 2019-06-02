### Chapter 1 计算机网络和因特网

#### 1.1 因特网 

* 构成描述：通过构成因特网的基本硬件和软件组件来描述因特网

  ​	因特网是一个世界范围的计算机网络，即一个互联全世界数十亿计算机的网络；

  ​        这些计算机被称为主机或端系统，例如：服务器、手机、路由器等等；

  ​	端系统通过通信链路和分组交换机连接到一起，不同链路的传输速率（单位：bit/s或bps）不同；

  ​	因特网中最终名的额分组交换机类型是：路由器（router）和链路层交换机（link-layer switch）；

  ​	端系统之间发送数据时，发送端系统将数据分段，并为每段加上首部字节，由此形成的信息包成为分组（packet）；

  ​	从发送端到接收端系统，一个分组所经历的一些列通信链路和分组交换机称为通过该网络的路径（path或route）；

  ​	端系统通过 因特网服务提供商（ISP）接入因特网；

  ​	端系统、分组交换机和其他因特网不见都要运行一些列协议（protocol），这些协议控制因特网中信息的接收和发送；

  ​	因特网中最重要的两个协议是 TCP（传输控制协议）和 IP（网际协议）；伊特网的主要协议统称TCP/IP；

* 服务描述：根据为分布式应用提供服务的联网设施基础描述因特网

  ​	因特网系统包括各种各样的应用程序，这些应用程序设计多个相互交换数据的端系统，这些应用程序被称为分布式应用程序

  ​	套接字接口（socket interface）：规定了运行在一个端系统上的程序请求因特网基础设施向另一个端系统上特定目的地程序交付数据的方式

* 协议：定义了在两个或多个通信实体间交换的报文的格式和顺序，以及报文的发送、接收或其他事件所采取的动作

#### 1.2 网络边缘

​	端系统也被称为主机，进一步分为两类：客户（client）和服务器（server）

 * 接入网：指将端系统物理连接到起边缘路由器（edge router）的网络

    * 家庭接入： DSL（数字用户线）、电缆、FTTH（光纤到户）、拨号和卫星
    * 企业（和家庭）接入：以太网和WiFi

 * 物理媒体：通过物理媒体传播电磁波过光脉冲来发送比特信息，

   ​	物理媒体分为两种：导引型媒体（电波沿着固体媒体前行）和非导引型媒体（电波在空气或外层空间中传播）

   ​	导引型媒体：双绞铜线、同轴电缆、光纤、陆地无线电信道、卫星无线电信道（同步卫星和近地轨道）

#### 1.3 网络核心

通过网络链路和交换机移动数据有两种基本方法：分组交换和电路交换。

##### 分组交换

​	在各种网络应用中，端系统彼此交换报文（message），报文能包含协议社记者需要的任何东西；

​	源将长报文划分为较小的数据块，称之为分组（packet），源和目的地之间，每个分组都通过通信链路和分组交换机传送；

​	存储转发传输：交换机能够开始向输出链路传输该分组的第一个比特之前，必须接收到整个分组。

​	排队时延：每台分组交换机有多条链路与之相连，对于每条相连的链路该分组交换机具有一个输出缓存（也称输出队列），如果到达的分组需要传输到某条链路而该链路正忙于传输其他分组，该到达分组必须在输出缓存中等待，因此产生了输出缓存的排队时延。

​	分组丢失（丢包）（packet loss）： 因为缓存空间有限，一个到达的分组可能发现缓存已被其他等待传输的分组完全充满了，因此到达的分组或已经排队的分组之一将被丢弃，出现分组丢失（丢包）

​	转发表和路由选择协议：每台路由器具有一个转发表，用于将目的地址（或目的地址的一部分）映射成为输出链路，路由选择协议用于自动地设置这些转发表

##### 电路交换

​	电路交换网络中，两台主机通信时，该网络会在两台主机间创建一条专用的端到端连接（end-to-end connection）

​	电路交换网络中的复用：频分复用（FDM）、时分复用（TDM）

两种交换的对比：

​	电路交换网络中，端系统间通信期间预留了端系统间沿路径通信所需要的资源（缓存，链路传输速率），分组交换网络中不预留

​	电路交换不考虑需求而预先分配了传输链路的使用，使得已分配而并不需要的链路未被利用，而分组交换按需分配链路的使用。

​	电路交换和分组交换目前都是普遍采用的方式，但未来趋势是朝着分组交换方向发展

#### 1.4 分组交换网络中的时延、丢包和吞吐量

 * 时延类型：
   1. 节点处理时延：检查分组首部、决定分组导向何处、检查比特级别差错的时间等等
   2. 排队时延： 分组在链路上等待传输时，它经受排队时延
   3. 传输实验所有分组的比特推向链路的时间，L/R
   4. 传播时延： 链路起点到路由器传播所需要的时间，与传播距离有关

* 排队时延和丢包

  ​	比率La/R被称为流量强度，设计系统时流量强度不能大于1

* 端到端时延

* 计算机网络中的吞吐量

  在任何时间的瞬时吞吐量是主机接受奥文件的速率（以bps计）

#### 1.5 协议层次及其服务模型

* 分层的体系结构

  1. 协议分层：网络设计者以分层的方式组织协议以及实现这些协议的网络硬件和软件。

     ​	一个协议层能够用软件、硬件或两者结合来实现，协议分层具有概念化和结构化的优点；

     各层的所有协议被称为协议栈（protocol stack），因特网的协议栈有5个层次组成：物理层、链路层、网络层、运输层和应用层；

     1. 应用层：网络应用程序及它们的应用协议存留的地方，位于应用层的信息分组称为报文
     2. 运输层：运输层在应用程序端点之间传送应用层报文，有两种运输协议TCP和UDP，运输层分组称为报文段
     3. 网络层：也叫IP层，将数据报（datagram）的网络层分组从一台主机移到量一台主机，网络层包括网际协议IP
     4. 链路层：链路层提供的服务取决于应用于该连裤的特定链路层协议，链路层分组称为帧（frame）
     5. 物理层：将帧中的一个个比特从一个节点移动到下一个节点

     

  2. OSI模型

     OSI参考模型有7层：应用层、表示层、会话层、运输层、网络层、数据链路层和物理层

* 封装

  ​	数据从发送端系统的协议栈向下，沿着中间的链路层交换机和路由器的协议栈上上下下，然后向上到达接收端系统的协议栈。每一层，一个分组有两种类型字段“：首部字段和有效载荷字段

#### 1.6 面对供给的网络

​	恶意软件：入侵并感染设备，做各种不正当的事情，包括病毒、蠕虫等

​	拒绝服务攻击（DoS）：弱点攻击、带宽洪泛、连接洪泛

​	嗅探分组：通过分组嗅探器接收各种敏感信息、隐私信息等

​	IP哄骗：一个用户冒充另一个用户

#### 1.7 计算机网络和因特网的历史

​	略