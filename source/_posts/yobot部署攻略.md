---
title: yobot部署攻略
date: 2021-04-21 14:48:47
tags: [yobot , 教程]
top: true
---


## 关于在云服务器上通过centos7部署go-cqhttp 和 yobot
<!--more-->
前言：  
yobot官方使用教程与安装教程[点击这里](https://yobot.win/install/mirai/)

博主自己在云服务器上搭建时遇到部分问题，解决后总结在本博文，希望对有需要的人起到帮助。  
博主云服务器：腾讯云 centos7.6  阿里云 centos 8.3  
记得要将服务器开启9222端口
<br>

# yobot部分

安装依赖

```bash
yum install -y gcc python3 screen wget
```
如果提示 unable to find a match : screen 就通过
```bash
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
```
配置yum源  
请使用 python3 -V 命令确认 python 版本，yobot 支持的 python 版本为 3.6 ~ 3.8

使用终端复用器  
这里我们用 screen 作为终端复用工具，[详细用法](http://h300579.vicp.hk/2021/05/15/screen%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95/)
<br>
官方这里没有细说，大概用法就是 screen -s 新建一个窗口，每次用完窗口通过<kbd>Ctrl</kbd>+<kbd>A</kbd> <kbd>Ctrl</kbd>+<kbd>d</kbd>来使当前窗口detach，然后screen -ls来看已经detach的窗口，通过screen -r 名字或者id来恢复到目标窗口。由于yobot部署需要yobot+go-cqhttp两个软件，所以建议开启两个窗口，分别命名qqbot和miraiqq（可自行命名）
<br>  
现在新建一个 screen 终端
```bash
screen -S qqbot
```
部署yobot

```bash
mkdir -p ~/qqbot/yobot
cd ~/qqbot/yobot

# 下载源码，使用 stable 稳定版分支
git clone https://github.com/pcrbot/yobot.git -b stable

```
注意这里git指令多半会报错没有git  通过
```bash
yum install git
```
来安装git使git可用  

然后 git clone 在国内现在速度非常慢不够看，所以建议直接使用国内镜像，代码如下
```bash
git clone https://github.com.cnpmjs.org/pcrbot/yobot.git
```
clone完成后继续
```bash
cd yobot/src/client/

# 安装依赖
pip3 install -r requirements.txt --user
# 国内可加上参数 -i https://pypi.tuna.tsinghua.edu.cn/simple

# 生成 yobotg
python3 main.py

# 启用 yobot
sh yobotg.sh
```

这里会提示 
```bash
Traceback (most recent call last):
  File "main.py", line 36, in <module>
    from aiocqhttp import CQHttp
ModuleNotFoundError: No module named 'aiocqhttp'
```
我们通过pip3进行aiocqhttp的安装
```bash
pip3 install aiocqhttp[all]
```
这里可能会提示我们缺少python.h  
我们通过下方命令安装python-devel
```bash
yum install python3-devel
```
如果提示与已存在的python-devel冲突，通过 yum remove 名字  来卸载已安装的python-devel后再进行安装  

安装完devel后再次安装aiocqhttp，成功安装后再次运行安装依赖，应该就能顺利执行完毕。  
代码如下:
```bash
pip3 install aiocqhttp[all]
pip3 install -r requirements.txt --user
```

<br>
安装完依赖不出错的话再次启动yobot  

``` bash
# 启用 yobot
sh yobotg.sh
```
出现这个界面就表明yobot已经成功安装了。
```
==============================
              _           _
             | |         | |
  _   _  ___ | |__   ___ | |_
 | | | |/ _ \| '_ \ / _ \| __|
 | |_| | (_) | |_) | (_) | |_
  \__, |\___/|_.__/ \___/ \__|
   __/ |
  |___/
==============================
正在初始化...
设置已初始化，发送help获取帮助
yobot[v3.6.11]源码版
初始化完成，启动服务...
Running on https://0.0.0.0:9222 (CTRL + C to quit)
[2021-04-21 09:55:52,474] ASGI Framework Lifespan error, continuing without Lifespan support
刷新日服日程表成功
刷新台服日程表成功
刷新国服日程表成功
```
完成后就可以<kbd>Ctrl</kbd>+<kbd>A</kbd> <kbd>Ctrl</kbd>+<kbd>d</kbd>把yobot挂到后台运行了。

# go-cqhttp部分

通过screen新建一个窗口
```bash
screen -S miraiqq
```
然后
```bash
mkdir -p ~/qqbot/mirai
cd ~/qqbot/mirai
```
由于国内众所周知的原因，在国内连接不上github，下载速度很感人，所以这里我们直接将文件通过sftp上传到服务器  /root/qqbot/miraiqq/ 下。  
文件是博主从github上直接下的最新版  
[下载连接](https://pan.baidu.com/s/1jQQsVmIjhxgLrs5CqBUpaA)  
提取码：20w1  
上传完毕后继续操作
```bash
tar zxvf go-cqhttp_linux_amd64.tar.gz
rm go-cqhttp_linux_amd64.tar.gz
```
修改go-cqhttp配置文件
```bash
cd ~/qqbot/mirai

# 先执行
./go-cqhttp
# 此时会生成一个 config.yml 文件
# 修改这个文件
```
这里可以直接下载我调好的config.yml模板，在里面修改qq账号密码然后就可以启动登录了  
[下载链接](https://pan.baidu.com/s/1p5roH3w2NJkr0kii_e_8Fw)  
提取码：94ai  
下载后修改config.yml中的qq账号和qq密码两栏  
将其上传至/root/qqbot/mirai/覆盖已存在的config.yml  
启动go-cqhttp  
```bash
cd ~/qqbot/mirai
chmod +x go-cqhttp
./go-cqhttp
```
部署完成，<kbd>Ctrl</kbd>+<kbd>A</kbd> <kbd>Ctrl</kbd>+<kbd>d</kbd>将mirai也挂起到后台  
# 验证安装
向mirai登录的qq号发送version，回复当前版本号说明配置成功