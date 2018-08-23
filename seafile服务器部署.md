1 . 部署目录结构
cd /path/to/wangpan  
mkdir haiwen
cd haiwen
cp seafile-server ./
tar -xvf seafile-server.tar.gz

2. 安装依赖
sudo apt-get install python-imaging
sudo apt-get install python-mysqldb
sudo apt-get install python-ldap
sudo apt-get install python-urllib3
sudo apt-get install python-memcache

3. 安装
cd seafile-server-6.2.5/
./setup-seafile-mysql.sh

4. 启动
./seafile.sh start   # 启动seafile服务
./seahub.sh start <port>   # 启动seahub网站

5. 停止
./seahub.sh stop
./seafile.sh stop


参考文档:
https://manual-cn.seafile.com/deploy/using_mysql.html
下载地址:
https://www.seafile.com/download/




