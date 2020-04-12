---
title: 每周总结第三十八期
date: 2020-04-11 12:55:49
categories:
- 每周分享
tags: 每周分享
---
> 本周是2020年的第十五个周末。    
> 这里记录过去一周，我的一些总结。

<!-- 制作一张最能反映过去一周的周图片 -->
![weekly-38](http://img.liugezhou.online/blog/weekly38.png)


<!--more-->
<!-- 一周最大感受 -->
#### Feeling
> 世界很大，圈子很小。  

#### 大炮
> 接受纪律审查和监察调查。视频弹幕关闭，官媒停止评论，搜索不到。

#### 个人所得税
> 个人所得税北京补退税开通。  
> 【专项附加扣除填报一定要填，特被注意租房一定要填】  

#### 青客长租公寓
> 国内第一家上市长租公寓(19年11月5日登陆纳斯达克挂牌上市)，疫情期间，青客强行解约，拖欠房东租金，导致租客被赶的一系列操作导致再次被推上风口浪尖。

#### [专为程序员编写的英语学习指南 v1.2](https://github.com/yujiangshui/A-Programmers-Guide-to-English)
> Github上一个八千多start的项目--专为程序员编写的英语学习指南 v1.2。  
> 在线版本为：[https://a-programmers-guide-to-english.harryyu.me](https://a-programmers-guide-to-english.harryyu.me/)

#### [DeepL](https://www.deepl.com/translator)
> 一家创业公司推出的机器翻译引擎，据称比谷歌翻译得更好。

#### RCS
> RCS 增强短信（富媒体信息收发）。  
> 简言之类似与安卓版的 iMessage ，只不过主导厂商不再是苹果或者腾讯，而是运营商。  

#### COBOL
> 在抢口罩和呼吸机的同时，美国新泽西州州长在电视台上，公开招聘大龄程序员，要求是：50年程序员经验，掌握COBOL编程语言，时薪 55 美元至 85 美元！   
> 原因为：疫情背景下，美国失业数据飙升，由于国家各项福利保障比较完善，失业人纷纷领取失业保险金，但失业保险系统用COBOL语言开发，由于系统故障，积累了太多的失业金无法发放，于是州长开始在电视台上公开招聘。 
> COBOL 全称为（Common Business Oriented Language），是数据处理领域最为广泛的程序设计语言。它是世界上第一个商用语言，第一个广泛使用的高级编程语言。 
> COBOL 应用的领域特别重要：金融，政府，航空公司。所有的银行，保险公司，金融机构都在大量使用 COBOL 写的程序。

#### 每天前端一道前端面试题
> 本周在哔哩哔哩上注册了一个账号，尝试着录了几个视频《每天一道前端面试题》。  
> 一气呵成，效果不是很好，但，是一次很有意思的尝试。  

#### [DOM变动发出声音](https://gist.github.com/tomhicks/6cb5e827723c4eaef638bf9f7686d2d8)
> 👆 一段 JS 代码，只要插在网页里面，可以让 DOM 变动发出声音。如果 DOM 有改变，你就会听到声音。
```
	const audioCtx = new (window.AudioContext || window.webkitAudioContext)()
const observer = new MutationObserver(function(mutationsList) {
  const oscillator = audioCtx.createOscillator()

  oscillator.connect(audioCtx.destination)
  oscillator.type = "sine"
  oscillator.frequency.setValueAtTime(
    Math.log(mutationsList.length + 5) * 880,
    audioCtx.currentTime,
  )

  oscillator.start()
  oscillator.stop(audioCtx.currentTime + 0.01)
})

observer.observe(document, {
  attributes: true,
  childList: true,
  subtree: true,
  characterData: true,
}) 
```

<!-- 鸡汤一句 -->
#### End
> 即使没有报酬，你也会去干的工作是什么？  

> 每个人心中都有一个火种，不要听任它熄灭，要找到它，点燃它。