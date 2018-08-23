## 对/dev/sdb进行分区
```bash
sudo fdisk /dev/sdb
```

<p>
输入m, 可以查看操作命令 <br>
输入p查看当前磁盘分区，  <br>
输入n新建一个分区， 输入p建立分区 <br>
最后出入w. 回车保存
</p>

##  格式化分区
```bash
mkfs.ext4 /dev/sdb
```

## 挂载分区
```bash
mkdir /yugengde
partprobe /dev/sdb  # 通知系统内核分区表的变化
mount /dev/sdb /yugengde
```

## 查看是否挂载成功
```bash
df -h
```

## 设置开机自动挂载
```bash
sudo blkid  # 查看设备的UUID
```
- 修改/etc/fstab文件(文件末尾新添一行)
```angular2html
UUID=610cd744-84a9-41f6-bd19-e0a3ccf8b3b4 /yugengde
```

## 重启电脑， 查看设置是否成功
```bash
reboot
```

## 卸载及删除分区
```bash
umount /dev/sdb
fdisk /dev/sdb
```

<p>
输入m, 可以查看操作命令. <br>
输入p查看当前磁盘分区.  <br>
输入d删除一个分区 <br>
最后出入w. 回车保存.
</p>

[参考链接](https://www.cnblogs.com/zishengY/p/7137671.html)

