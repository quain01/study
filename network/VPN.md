## Client to Site VPN

小网中的linux可以启动l2tp vpn server，从windows中拨号连接vpn server，从而和小网进行通信。

## Site to Site VPN

两个小网，可以通过各自的外网边缘节点间建立vpn隧道，从而实现两个小网之间的互通。

创建ipip隧道参考：http://www.opstool.com/article/183

ServerA配置iptunnel,并给tunnel接口配置上ip：
```
ip tunnel add a2b mode ipip remote 2.2.2.2 local 1.1.1.1
ifconfig a2b 192.168.2.1 netmask 255.255.255.0
```
ServerB配置iptunnel,并给tunnel接口配置上ip：
```
ip tunnel add a2b mode ipip remote 1.1.1.1 local 2.2.2.2
ifconfig a2b 192.168.2.2 netmask 255.255.255.0
```

隧道创建完成之后，相当于在ServerA和ServerB之间拉了一条专线。ServerA有自己的网卡接口（192.168.2.1），ServerB有自己的网卡接口（192.168.2.2）。

接着把ServerA、ServerB的IP转发功能打开，就做成了一个路由器（注意关闭防火墙功能），配置好路由之后，就可以把两边的小网打通了。
