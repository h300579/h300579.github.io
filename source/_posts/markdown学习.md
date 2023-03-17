---
title: markdown学习笔记
date: 2021-6-16 10:52:31 
tags: [markdown , 学习]

---

# markdown学习

## markdown标题

### 1.使用=和-标记一级和二级标题

```
我展示的是一级标题
=====
我展示的是二级标题
--------
```


### 2.使用#号标记
使用 <kbd>#</kbd> 号可表示 1-6 级标题，一级标题对应一个 <kbd>#</kbd> 号，二级标题对应两个 <kbd>#</kbd> 号，以此类推。

## Markdown段落
Markdown 段落没有特殊的格式，直接编写文字就好，<strong>段落的换行是使用两个以上空格加上回车。</strong>  
![test](https://www.runoob.com/wp-content/uploads/2019/03/36A89BDA-A062-4D66-A41B-0EBEE7891AB9.jpg)  
当然也可以在段落后面使用一个空行来表示重新开始一个段落。
![](https://www.runoob.com/wp-content/uploads/2019/03/3F254936-778E-417A-BEF2-467116A55D00.jpg)  

## 字体
Markdown 可以使用以下几种字体：
```
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```
*斜体文本*  
_斜体文本_  
**粗体文本**  
__粗体文本__  
***粗斜体文本***  
___粗斜体文本___  
 
## 分割线
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：  
```
***

* * *

*****

- - -

----------
```
***

* * *

*****

- - -

----------

## 删除线  
如果段落上的文字要添加删除线，只需要在文字的两端加上两个波浪线 <kbd>~~</kbd> 即可，实例如下：  
```
RUNOOB.COM
GOOGLE.COM
~~BAIDU.COM~~
```
RUNOOB.COM  
GOOGLE.COM  
~~BAIDU.COM~~  

## 下划线
下划线可以通过 HTML 的 <kbd>\<u></kbd> 标签来实现：  
<u>test</u>

## 脚注
脚注是对文本的补充说明。

Markdown 脚注的格式如下:  
```
[^要注明的文本]
```
以下实例演示了脚注的用法：
```
创建脚注格式类似这样 [^RUNOOB]。

[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！
```
演示效果如下：
![](https://www.runoob.com/wp-content/uploads/2019/03/md5.gif)  

创建脚注格式类似这样 [^RUNOOB]。  

[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！  


## Markdown 列表
Markdown 支持有序列表和无序列表。

无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容： 
```
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项


- 第一项
- 第二项
- 第三项
```
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项


- 第一项
- 第二项
- 第三项
有序列表使用数字并加上 . 号来表示，如：
```
1. 第一项
2. 第二项
3. 第三项
```
1. 第一项
2. 第二项
3. 第三项
### 列表嵌套
列表嵌套只需在子列表中的选项前面添加四个空格即可：
```
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素
```
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素

## Markdown区块
Markdown 区块引用是在段落开头使用 > 符号 ，然后后面紧跟一个**空格**符号：
```
> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想
```
> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想

另外区块是可以嵌套的，一个 > 符号是最外层，两个 > 符号是第一层嵌套，以此类推：  
```
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
```
> 最外层
> > 第一层嵌套
> > > 第二层嵌套  

## 区块中使用列表
区块中使用列表实例如下：
```
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项
```
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项

## 列表中使用区块

如果要在列表项目内放进区块，那么就需要在 > 前添加四个空格的缩进。

列表中使用区块实例如下：
```
* 第一项
    > 菜鸟教程
    > 学的不仅是技术更是梦想
* 第二项
```
* 第一项
    > 菜鸟教程  
    > 学的不仅是技术更是梦想
* 第二项

## Markdown 代码
如果是段落上的一个函数或片段的代码可以用反引号把它包起来（`），例如：
```
`printf()` 函数
```
`printf()` 函数

### 代码区块
代码区块使用 **4 个空格**或者一个**制表符（Tab 键）**。

实例如下：
```
   test()
```
    test()
你也可以用 \``` 包裹一段代码，并指定一种语言（也可以不指定）：


## Markdown链接
链接使用方法如下：  

    [链接名称](链接地址)

    或者

    <链接地址>

例

    这是[连接](http://www.baidu.com)
这是[连接](http://www.baidu.com)

### 高级链接
我们可以通过变量来设置一个链接，变量赋值在文档末尾进行：
```
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）

  [1]: http://www.google.com/
  [runoob]: http://www.runoob.com/
```
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）

[1]: http://www.google.com/
[runoob]: http://www.runoob.com/


## Markdown图片
Markdown 图片语法格式如下：
```
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

- 开头一个感叹号 !  
- 接着一个方括号，里面放上图片的替代文字  
- 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 属性的文字。  
使用实例:
```
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)

![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")
```
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)

![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")


当然，你也可以像网址那样对图片网址使用变量:  
```
这个链接用 1 作为网址变量 [RUNOOB][1].
然后在文档的结尾为变量赋值（网址）

[1]: http://static.runoob.com/images/runoob-logo.png
```

Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 <img> 标签。
```
<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
```

## Markdown 表格
Markdown 制作表格使用 <kbd>|</kbd> 来分隔不同的单元格，使用<kbd>-</kbd> 来分隔表头和其他行。

语法格式如下：
```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |  

对齐方式   
**我们可以设置表格的对齐方式:**
- <kbd>-:</kbd> 设置内容和标题栏居右对齐。  
- <kbd>:-</kbd> 设置内容和标题栏居左对齐。  
- <kbd>:-:</kbd> 设置内容和标题栏居中对齐。  
```
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```

| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |

## Markdown高级技巧
### 支持的 HTML 元素

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。

目前支持的 HTML 元素有：\<kbd> \<b> \<i> \<em> \<sup> \<sub> \<br>等 ，如：
```
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
```
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑  

### 转义  
Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符，Markdown 使用反斜杠转义特殊字符：
```
**文本加粗** 
\*\* 正常显示星号 \*\*
```
**文本加粗**   
\*\* 正常显示星号 \*\*  
Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
```
\   反斜线
`   反引号
*   星号
_   下划线
{}  花括号
[]  方括号
()  小括号
#   井字号
+   加号
-   减号
.   英文句点
!   感叹号
```


## 小实例实现
<div style="float:left"><a class="fancybox fancybox.image" href="https://i0.hdslb.com/bfs/album/6582ab0f09d86a876f0c7cc1cc072f09771e2d5f.jpg" itemscope="" itemtype="http://schema.org/ImageObject" itemprop="url" data-fancybox="default" rel="default"><img src="https://i0.hdslb.com/bfs/album/6582ab0f09d86a876f0c7cc1cc072f09771e2d5f.jpg" referrerpolicy="no-referrer" width="180px"></a></div>

<div><div class="table-container"><table width="500px"><tbody><tr><td class="title_main" colspan="2" rowspan="2">
<p class="title_cn">佐贺偶像是传奇 第2期</p>
<p class="title_jp">ゾンビランドサガ リベンジ</p></td>
<td class="type_a">原创动画</td></tr>
<tr><td class="type_tag">僵尸/偶像/独特</td></tr>
<tr><td rowspan="2" class="staff">
　　导演：境宗久<br>
　　编剧：村越繁<br>
动画人设：深川可纯<br>
　总作监：崔文英<br>
　　　　　桑原干根<br>
３Ｄ导演：黑岩爱<br>
　　音乐：高梨康治/Funta7<br>
音乐制作：avex pictures<br>
动画制作：MAPPA
</td><td rowspan="2" class="cast">
巽幸太郎：宫野真守<br>
　　源樱：本渡枫<br>
二階堂咲：田野麻美<br>
　水野爱：种田梨沙<br>
绀野纯子：河濑茉希<br>
　　夕雾：衣川里佳<br>
星川莉莉：田中美海<br>
　山田妙：三石琴乃<br>
　警察官：吉野裕行 等
</td><td class="link_a">
<a href="https://zombielandsaga.com/" target="_blank">动画官网</a><br>
<a href="https://www.bilibili.com/bangumi/play/ep376377" target="_blank">PV</a>
<p class="broadcast">4/8周四深夜</p>
</td></tr><tr><td class="link_b">
<a href="https://www.bilibili.com/bangumi/media/md28233251" target="_blank" rel="noopener"><img src="https://i0.hdslb.com/bfs/album/c2c2b4b458991a52260503b0e828831c2b6109f1.jpg" referrerpolicy="no-referrer"><br><font color="red">[独家]</font></a>
</td></tr></tbody></table></div></div>





```
<div style="float:left"><a class="fancybox fancybox.image" href="https://i0.hdslb.com/bfs/album/6582ab0f09d86a876f0c7cc1cc072f09771e2d5f.jpg" itemscope="" itemtype="http://schema.org/ImageObject" itemprop="url" data-fancybox="default" rel="default"><img src="https://i0.hdslb.com/bfs/album/6582ab0f09d86a876f0c7cc1cc072f09771e2d5f.jpg" referrerpolicy="no-referrer" width="180px"></a></div>

<div><div class="table-container"><table width="500px"><tbody><tr><td class="title_main" colspan="2" rowspan="2">
<p class="title_cn">佐贺偶像是传奇 第2期</p>
<p class="title_jp">ゾンビランドサガ リベンジ</p></td>
<td class="type_a">原创动画</td></tr>
<tr><td class="type_tag">僵尸/偶像/独特</td></tr>
<tr><td rowspan="2" class="staff">
　　导演：境宗久<br>
　　编剧：村越繁<br>
动画人设：深川可纯<br>
　总作监：崔文英<br>
　　　　　桑原干根<br>
３Ｄ导演：黑岩爱<br>
　　音乐：高梨康治/Funta7<br>
音乐制作：avex pictures<br>
动画制作：MAPPA
</td><td rowspan="2" class="cast">
巽幸太郎：宫野真守<br>
　　源樱：本渡枫<br>
二階堂咲：田野麻美<br>
　水野爱：种田梨沙<br>
绀野纯子：河濑茉希<br>
　　夕雾：衣川里佳<br>
星川莉莉：田中美海<br>
　山田妙：三石琴乃<br>
　警察官：吉野裕行 等
</td><td class="link_a">
<a href="https://zombielandsaga.com/" target="_blank">动画官网</a><br>
<a href="https://www.bilibili.com/bangumi/play/ep376377" target="_blank">PV</a>
<p class="broadcast">4/8周四深夜</p>
</td></tr><tr><td class="link_b">
<a href="https://www.bilibili.com/bangumi/media/md28233251" target="_blank" rel="noopener"><img src="https://i0.hdslb.com/bfs/album/c2c2b4b458991a52260503b0e828831c2b6109f1.jpg" referrerpolicy="no-referrer"><br><font color="red">[独家]</font></a>
</td></tr></tbody></table></div></div>

```


# 引用
[菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)

[长门有C的blog](https://yuc.wiki/)