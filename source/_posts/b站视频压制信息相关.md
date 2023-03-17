---
title: b站视频压制
data: 2023-3-17 11:00:00
tags: [视频压制, 技术 ]
---
# 前言
这是一篇关于如何获取b站最优画质的上传探索文章。  
b站曾经还是小破站的时候，需要用渣浪的服务器来传视频，那时候为了获取极佳的画质，就有了留后黑来降低平均码率获得高画质的方法。  
后来啊b富有了，有一段视频码率很夸张的时代，可以说基本不用考虑二压。  
然后啊b又穷了，二压线又又又来了！  

# 啊b二压门槛
根据b站up 我真的没有天分丶 的 [BV1ne411G7qy](https://www.bilibili.com/video/BV1ne411G7qy/?vd_source=f30bfaa2341a62352679272ad1d09fb7) 统计数据，现在啊b的二压线为：  
  
1080P高清：2600Kbps  
1080P60帧：5200Kbps  
4K超清：18500Kbps  

鉴于啊b现在没有2k分辨率档位，为了获取更高的码率上限，都可以将1080p和2k拉到4k分辨率来骗高码率。  
这里还有高阶技巧就是用最短边分辨率骗假4k。  
详见 其棱无也 的 [BV1q44y127rB](https://www.bilibili.com/video/BV1q44y127rB/?spm_id_from=333.788.recommend_more_video.1&vd_source=f30bfaa2341a62352679272ad1d09fb7)，有详细介绍。  


# 压制软件对比
博主浅薄的字幕组生涯解除过几款视频压制软件，分别是 大众无脑之王——小丸工具箱，开始追求一定效率的——ShanaEncoder，追求无脑显卡压制的——消极压制，参数众多看的头大的——MediaCoder ，效率最高的开源命令行软件——FFMPEG。  
其余没有提到的就不管了，顺便把那个说格式工厂的叉出去。

下为测试视频压制记录与对比：  
原视频：  
分辨率 2k  
码率   50Mbps  
时长   10min  

小丸工具箱压制：  
参数设置：分辨率 4k，码率18Mbps，2-pass，耗时 1h10m  
上传结果：[BV1YY4y1Q7YH](https://www.bilibili.com/video/BV1YY4y1Q7YH/?spm_id_from=333.880.my_history.page.click&vd_source=f30bfaa2341a62352679272ad1d09fb7)

Shana压制：  

消极压制：  

FFMPEG：  
