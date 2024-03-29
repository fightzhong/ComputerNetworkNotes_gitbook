#### 单播
```
单播用于发送数据包到单个目的地，且每发送一个一份单播报文都使用一个
单播IP地址作为目的地址。是一种点对点传输方式
```
#### 广播
```
广播是指发送数据包到同一广播域或子网内的所有设备的一种传输方式，是一种
点对多点传输方式
```
#### 组播(多播)
```
当网络中的某些用户需要特定数据时, 组播数据发送者仅发送一次数据, 借助组播
路由协议为组播数据包建立组播分发树, 被传递的数据到达用户端尽可能尽可能近的
节点后才开始复制和分发, 是一种点对多点传输方式。需要组播路由器的支持(运行组播协议的路由器)
```
### IP组播
```
IP组播地址范围：224.0.0.0-239.255.255.255(D类地址), 一个D类地址表示一个组播组, 
               只能用作分组的目标地址。源地址总是单播地址
注意：
    <1> 组播数据报也是“尽最大努力交付”，不提供可靠交付，应用于UDP
    <2> 对组播数据报不产生ICMP差错报文
    <3> 并非所有D类地址都可以作为组播地址

因特网范围内组播
    IGMP协议：让路由器知道本局域网上是否有主机(的进程)参加或者退出了某个组播组
    组播路由选择协议：目的是找出以源主机为根节点的组播转发树

硬件组播         
    同单播地址一样，组播IP地址也需要相应的组播MAC地址在本地网络中实际传送帧。
    组播MAC地址以十六进制值01-00-5E, 余下的6个十六进制位是根据IP组播组地址的最后23位转换得到的
    TCP/IP协议使用的以太网多播地址的范围是：01-00-5E-00-00-00到01-00-5E-7F-FF-FF
    收到多播数据包的主机，还要在IP层利用软件进行过滤，把不是本主机要接收的数据包丢弃
```