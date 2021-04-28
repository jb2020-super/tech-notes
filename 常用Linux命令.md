### 登录远程Linux服务器
ssh jshi@192.168.82.205
### 查看Nvidia显卡信息
nvidia-smi
# 文件操作

## 删除文件夹

`rm -rf folder-name`

## 移动文件夹

`mv srcPath dstPath`

### 离线运行任务
screen
screen -ls # 列出正在运行的任务列表
screen -r taskname # 切换到正在运行的某个任务
screen -S 8886 -X quit # 从list中杀掉一个Screen
### 杀进程
kill -9 PID
### htop
查看和管理进程列表，资源使用情况等。

### set git proxy
git config --global http.proxy http://[domain]\[user]:[password]@[ProxyIP]:[Port]

### set apt-get proxy 
sudo vim /etc/apt/apt.conf
edit apt.conf with the following:
Acquire::http::Proxy "http://[domain]\[user]:[password]@[ProxyIP]:[Port]";
Acquire::https::Proxy "http://[domain]\[user]:[password]@[ProxyIP]:[Port]";

### set wget proxy
cd /
sudo vim /etc/wgetrc
add following:
https_proxy = http://[domain]\[user]:[password]@[ProxyIP]:[Port]
http_proxy = http://[domain]\[user]:[password]@[ProxyIP]:[Port]
use_proxy = yes
### Vim command
i start to edit
Esc end edit mode
:w save file
:q exit file

### 安装luarocks
1. https://luarocks.org/#quick-start
2. set wget proxy
3. 按照下面的提示一路操作下来；遇到没有安装的包就按照提示安装。
```
$ wget https://luarocks.org/releases/luarocks-3.5.0.tar.gz
$ tar zxpf luarocks-3.5.0.tar.gz
$ cd luarocks-3.5.0
$ ./configure && make && sudo make install
$ sudo luarocks install luasocket
$ lua
Lua 5.3.5 Copyright (C) 1994-2018 Lua.org, PUC-Rio
> require "socket"
```
### 安装torch
Torch can be installed to your home folder in ~/torch by running these three commands:
```
# in a terminal, run the commands WITHOUT sudo
git clone https://github.com/torch/distro.git ~/torch --recursive
cd ~/torch; bash install-deps;
./install.sh
```
- sudo apt-get install software-properties-common
- sudo vim install-deps; replace python-software-properties with software-properties-common

### 显示文件夹大小
du -sh [folder-name]

### 文件传输
pscp -P 22 1.jpg jshi@192.0.0.0:/home/username

docker cp /home/username/1.jpg container_name:/usr/dst