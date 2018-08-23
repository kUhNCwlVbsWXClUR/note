
#  软件安装的路径
mkdir /usr/local/vim

# 下载vim
git clone https://github.com/vim/vim.git


# 配置
./configure --enable-multibyte  --enable-rubyinterp=dynamic --with-python3-config-dir=/usr/lib/python3.6/config-3.6m-x86_64-linux-gnu/  --with-python-config-dir=/usr/lib/python2.7/config-x86_64-linux-gnu/ --enable-pythoninterp  --enable-cscope --enable-gui=auto --with-features=huge --with-x --enable-fontset --with-compiledby=yugengde --enable-fail-if-missing --prefix=/usr/local/vim
make && make install

# 生成软链接
ln -s /usr/local/vim/bin/vim /usr/bin/vim

cd .vim/bundle/YouCompleteMe && ./install.py -all

