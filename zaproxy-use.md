ZAProxy USE
### 要求
- 硬件要求: 1. 无线网卡, 用于提供wifi;  2.有线网卡, 用于网络(一般电脑应该都有)
- 软件要求: kali 系统自带 zaproxy 软件， 无须再安装  [zarpxy下载地址](https://github.com/zaproxy/zaproxy/)

### 设置
- Settings -> WiFi -> Turn On Wi-Fi Hotspot   开启wifi功能
- 根据网络ID和密码, 将android手机连接到这个wifi中

### 此时各个设备IP
```html
路由地址                192.168.10.1             
KALI 物理地址           192.168.10.*
KALI 无线网卡           10.42.0.1

Android手机局域网地址    10.42.0.*

```

####  zaproxy软件设置

- Tools -> Local Proxies -> Local Proxy 
- 输入地址 address 192.168.10.23* , 端口 port :8080 -> 确定 ok

####  Android手机设置
- 无线网络 -> proxy设置  IP: 192.168.10.*  PORT: 8080(也就是你电脑的地址) 

### 完成！ 此时可以进行手机抓把包了 .

