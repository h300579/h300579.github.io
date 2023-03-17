---
title: HEXO blog搭建问题汇总
date: 2021-04-22 22:39:29
tags: [blog , 教程 , hexo]
img: /images/20210422.jpg
---

# 安装NodeJS

网上下载NodeJS安装包，对应自己的系统，本教程以linux为准。  
下载后丢到自己想安装的文件夹解压。  
<br>
<!--more-->
安装完成后通过ln -s 命令将刚刚安装位置的nodejs转为全局命令  
格式如下：  
```linux
ln -s /(你安装的位置)/nodejs/bin/npm /usr/local/bin/ 
ln -s /(你安装的位置)/nodejs/bin/node /usr/local/bin/ 
```
然后通过npm -v  和 node -v 来验证是否转为全局。  

或者可以通过修改/root/.bash_profile 的PATH参数，
```bash
PATH=$PATH:<PATH 1>:<PATH 2>:---:/usr/local/src/nodejs/bin
```
将/(你安装的位置)/nodejs/bin添加到路径中，可以一劳永逸  


成功后进行下一步  
<br>  

# 安装cnpm
通过淘宝源进行安装  
```linux
npm install -g cnpm --registry=https://registry.npm.taobao.org
```
如果之前是软连接，这里同样需要ln -s 进行转换全局cnpm，才能使用cnpm  


# 安装hexo

```
cnpm install -g hexo-cli
```

通过mkdir在自己想建blog的地方建一个blog文件夹  
然后转移到blog文件夹下，使用
```
hexo init
```
初始化生成博客环境。再通过
```
hexo s
```
启动博客，开启linux系统的4000端口。
```bash
firewall-cmd --add-port=123/tcp --permanent
firewall-cmd --reload
```
如果是云服务器可以直接通过后台操作开启。  
然后进入  服务器ip地址:4000  就能看到初始化完成的个人博客界面了