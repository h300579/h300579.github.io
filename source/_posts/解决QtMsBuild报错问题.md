---
title: 解决QtMsBuild could not locate qt.targets, qt.props; project may not build corr
date: 2022-1-17 16:39:25 
tags: [Qt , 技术,]
---

最近项目需要使用 Visual Studio 2013 配合 Qt 进行开发，结果项目移动后，环境重新搭建却疯狂报错：  
``` 
QtMsBuild could not locate qt.targets, qt.props; project may not build correctly
```
查找了各种方法都是说，把 QtMsBuild 文件 copy 过来再配个环境变量就好了。  
然而网上却没有免费的 QtMsBuild 供大伙使用。  
这里就放个连接出来吧。。

https://github.com/h300579/toolsBackup/tree/publish  

# 就这东西困扰了我一个下午，绝了。国内外都没有可以免费下载的地方，会不会有什么问题啊？  

版本：  
Qt 5.7.1 msvc  
visual stduio 2013  

有空了可能会回来把 qt 的软件包啥的也整整？不过估计以后用 visual studio 2013 的会越来越少吧  

参考连接：  
https://blog.csdn.net/u014095878/article/details/104900432
