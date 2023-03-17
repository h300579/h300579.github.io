---
title: QByteArray 的使用方法与技巧
data: 2022-2-14 11:00:00
tags: [Qt, 技术, ]
---

最近做了个芯片烧录的上位机，因为功能设计到串口连续数据读取打包解析等内容，需要用到 QByteArray，且存着原始二进制数据。关于 QByteArray 的详细介绍，有空可以阅览一下 Qt 的 help，这里记录下常用的相关操作，方便使用查阅用法。

## 访问与赋值  
访问数据有四种方式， [] at() data[] constData[]，其中 [] 和 at 为可读可写，at 和 constData[] 为只读，因此访问效率最高。

## 在末尾追加字符数据
```
QByteArray a("free");
QByteArray b("dom");
a.append(b);
```
还有 a+=b，听导师说这样会有拼接遗漏数据的可能？  
还有 memcpy 拷贝的方法，虽然我没试成功过。  
  
## 查找某个字符的位置
indexOf，返回对应数字的第一个位置。  
```
QByteArray a("abcd");
int c = a.indexOf('b');
```
  
## 从左向右截取字符串
```
QByteArray a("pineapple");
QByteArray b = a.left(4);
b = "pine";
```
  
## 从右向左截取字符串
```
QByteArray a("pineapple");
QByteArray b = a.right(5);
b = "apple";
```

## 截取部分字符串
```
QByteArray a("hello world");
QByteArray b = a.mid(6,3);  //第一个参数代表从哪里开始，0对应h，5对应空格，第二个参数代表开始后多少长度
b = "wor";
QByteArray c = a.mid(6);    //一个参数就只代表从哪里开始，截取剩下所有内容。
c = "world";
```

## 删除某段字符
```
QByteArray a("hello world);
a.remove(6,3);
a = "hello ld";
```
<text class="color:red;"> 这个讲道理和截取左右字符串是不是互补关系呢？如果是的话效率是一样的吗？有待观察验证。</text>
  
## 指定位置插入字符串
```
QByteArray a("helloworld");
a.insert(5,QByteArray(" "));
a = "hello world";
```

## 字符替换  
```
QByteArray a("GoodBye world");
QByteArray b("hello");
a.replace(0, 7, b); // 0表示从第0个字符开始，7表示替换长度为7的内容，b表示替换的内容，长度可以不同。
a = hello world;
```
  
## Leader教的转换方法  
```
QByteArray a = QSerialPort.readAll();
QString tt = a.toHex();
QByteArray tt2 = QByteArray().fromHex(tt.toLatin1());
```
这里需要好好学习下各个函数的作用，列出来，不然直接copy拿去用就好。  
  

------
## 参考资料：  
QByteArray常见使用方式：https://blog.csdn.net/weixin_38931060/article/details/117992884?spm=1001.2014.3001.5502  
QT中常见QByteArray，QString，char,10进制，16进制之间转换：https://blog.csdn.net/weixin_38931060/article/details/117994816?spm=1001.2014.3001.5502