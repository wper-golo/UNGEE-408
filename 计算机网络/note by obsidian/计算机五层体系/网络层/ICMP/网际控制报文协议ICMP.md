# ICMP功能

- 确认IP包是否成功送达目标地址
- 通知在发送过程中IP包被废弃的具体原因
- 改善网络设置等

**有了这些功能以后，就可以获得网络是否正常，设置是否有误以及设备有何异常等信息，从而便于进行网络上的问题诊断**

# ICMP报文分类

主机或路由器使用ICMP来发送
- [[ICMP差错报告报文]]
- [[ICMP询问报文]]
另外，ICMP报文被封装在IP数据包中发送

# ICMP报文

ICMP不是高层协议，只是封装在IP数据报中，作为其中的数据部分，属于IP层的协议

## 格式

![[image-20221115093440431.png]]

# ICMP的应用

[[PING]]
[[TraceRoute]]
