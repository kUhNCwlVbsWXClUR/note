#### step 1

```sh
ifconfig
```

#### step 2
```sh
cat /etc/network/interfaces
```

```
source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.199.17
netmask 255.255.255.0
gateway 192.168.199.1
```

#### step 3 刷新IP

```sh
sudo ip addr flush eth0
sudo systemctl restart networking.service
```

