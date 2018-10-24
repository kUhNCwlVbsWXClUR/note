
# 设置 Port Forwarding Rules

![image]()
Name    Protocol    HostIP          HostPort    GuestIP     GuestPOrt
Rule1   TCP         192.168.1.107   33333       10.0.2.15   22


<p>
 biscsib 宿主机用户名
 33333 宿主机的端口
 192.168.1.107 宿主机的IP地址
</p>

ssh biscsib@192.168.1.107 -p 33333
