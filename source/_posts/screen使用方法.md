---
title: screen使用方法
date: 2021-5-15 10:52:31 
tags: [screen , 技术]
img: /images/linux.jpg
---



创建：screen -S ###  
<br>

<!--more-->

查看有多少会话：screen -ls  

恢复：screen -r ###  

如果不能恢复：先screen -d ###  

再screen -r ###  
 
删除 screen -S ### -X quit  
