点对点协议PPP（Point-to-Point Protocol），目前使用最广的点对点链路层协议（广域网）

>区分：PPP协议与[[P2P]]协议
>PPP协议（Point-to-Point）：为点到点连接传输不同协议的数据包提供了一种标准方法。本质是点-点串行通信协议。属于数据链路层（是一个协议集合）
>P2P协议（Peer-to-Peer）：对等计算机网络，在对等者（Peer）之间分配任务和工作负载的分布式应用架构。本质是一种网络结构的思想，打破了传统的C/S模式。属于应用层。

PPP协议的特点是：简单。只负责检测差错，不纠正；不使用序号，也不流量控制；支持多种网络层协议。

![[image-20221127111019693.png]]
![[image-20221127111032687.png]]


## 帧格式

PPP协议规定了特殊字符作为帧定界符
![[image-20221127111134048.png]]

## 透明传输的实现

主要使用了两种方法来实现透明传输
- 面向字节的异步链路（[[字符填充的首位定界法]]）
- 面向比特的同步链路（[[零比特填充的首位标志法]]）

## 差错检测

使用FCS校验（RFC 1662附录部分给出了C语言实现“查表法”）

## 工作状态

-   当用户拨号接入 ISP 时，路由器的调制解调器对拨号做出确认，并建立一条物理连接。
-   PC 机向路由器发送一系列的 LCP 分组（封装成多个 PPP 帧）。
-   这些分组及其响应选择一些 PPP 参数，并进行网络层配置，NCP 给新接入的 PC 机
-   分配一个临时的 IP 地址，使 PC 机成为因特网上的一个主机。
-   通信完毕时，NCP 释放网络层连接，收回原来分配出去的 IP 地址。接着，LCP 释放数据链路层连接。最后释放的是物理层的连接。
![[image-20221127111756960.png]]

>PPP协议已经不再是纯粹的数据链路层协议，还包含了物理层和网络层的内容