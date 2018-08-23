win10环境下使用mstsc远程连接kali

```sh
sudo apt-get install xrdp
sudo apt-get install vnc4server tightvncserver
sudo apt-get install xfce4   [安装是有个配置选项:选择默认即可, 好像是kdm，具体不记得了]
```

vim ~/.xsession      #添加如下内容

```html
xfce4-session   
```

```sh
service xrdp restart
```
mstsc连接时候使用  session xorg

username linux下用户 
password linux用户密码
