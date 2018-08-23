```sh
apt-get update
apt-get install git
git clone git clone https://github.com/inconshreveable/ngrok
apt-get install golang   # 安装Go语言开发环境
```
5. 添加ngrok域名 
	将*.ngrok于ngrok都指向你的IP [可以参考: aliyun绑定域名.md]

```sh
export GOPATH=/usr/local/ngrok/
export NGROK_DOMAIN="ngrok.ccccccc.cn"  #cccccc改成你的一级域名
```

8. 为域名生成证书

```sh
openssl genrsa -out rootCA.key 2048
openssl req -x509 -new -nodes -key rootCA.key -subj "/CN=$NGROK_DOMAIN" -days 5000 -out rootCA.pem
openssl genrsa -out server.key 2048
openssl req -new -key server.key -subj "/CN=$NGROK_DOMAIN" -out server.csr
openssl x509 -req -in server.csr -CA rootCA.pem -CAkey rootCA.key -CAcreateserial -out server.crt -days 5000
```

9. 将证书拷贝到指定位置
```ssh
cp rootCA.pem assets/client/tls/ngrokroot.crt
cp server.crt assets/server/tls/snakeoil.crt
cp server.key assets/server/tls/snakeoil.key
```

10. 编译
```ssh
make release-server  # 生成服务器文件
make release-client  # 生成客户端文件
```
[参考文档](https://blog.csdn.net/zhangguo5/article/details/77848658)

