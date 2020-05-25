---
title: 每周总结第四十二期
date: 2020-05-17 20:13:00
categories:
- 每周分享
tags: 每周分享
---
> 上周是2020年的第二十二个周末。(今天周一)    
> 这里记录过去一周，我的一些总结。

<!-- 制作一张最能反映过去一周的周图片 -->
![weekly-42](http://img.liugezhou.online/blog/weekly42.png)


<!--more-->
<!-- 一周最大感受 -->
#### Feeling
> 好吧，继续拖更。  
> 虽然此号无人问津，但是我却心有不甘。

#### 爱love佑
> 爱love佑小程序，爱佑慈善基金会官方小程序。  
> 如果世界让你感到冷漠，如果生活让你疲惫不堪，如果爱心让你无处释放。  
> 打开小程序，为远方还在忍受病痛折磨的孩子献上一份爱心吧。

#### KTFSR
> 发送KTFSR到10086，可以开通骚扰电话拦截功能，不用额外下载软件。

#### [楼盘真正销售情况](https://mp.weixin.qq.com/s/4rtdQ5gU6w0xY2lqSMEbWg)
> 👆 这篇文章，通过分析武汉楼盘情况，告诉大家：`所有楼盘的销售情况都是在政府网站上全部公开的`。   
> 作者在留言区：`所有城市楼盘销售情况都有的，国家规定必须公开，位置不同而已`。  
> 然而我花了些时间找了一找，还是没有找到。  

#### One Switch
> 一款Mac桌面软件， 可以快速设置隐藏桌面、黑暗模式、保持亮屏、屏幕保护、清理屏幕等小工具。  
> 
> Mac上一些软件在安装时，会显示不能打开的提示，就像这块小工具软件，这个时候只要打开终端输入以下命令，就会开启Mac的安装设置：允许任何来源。  
> `sudo spctl --master-disable`

#### [小技巧：Mac系统调整Launchpad图标大小](https://www.jianshu.com/p/60315dfcda53)
> 👆 Mac的启动台页面默认显示的图标比较大，而在我们使用一段时间后，会安装很多软件，图标看着着实不舒服。 
> 在设置中找不到图标大小的设置，这个时候需要在终端中，执行如下命令：  
>
> 1、调整每一列显示图标数量，7 表示每一列显示7个  
>  `defaults write com.apple.dock springboard-rows -int 7`  
> 
> 2、调整每一行显示图标数量，这里我用的是8  
> `defaults write com.apple.dock springboard-columns -int 8`  
>
> 3、由于修改了每一页显示图标数量，可能需要重置Launchpad  
> `defaults write com.apple.dock ResetLaunchPad -bool TRUE;killall Dock`

#### [柠檬清理](https://lemon.qq.com/)
> 一款Mac清理工具。

#### traditional
>  jquery框架的ajax参数：`traditional`,其默认值是false。  
> 而在请求接口如果需要传递一个参数为数组时，可以添加`traditionla:true`这一设置。

#### [JustAuth](https://github.com/justauth/JustAuth)
> 👆 史上最全的整合第三方登录的开源库。目前已支持Github、Gitee、微博、钉钉、百度、Coding、腾讯云开发者平台、OSChina、支付宝、QQ、微信、淘宝、Google、Facebook、抖音、领英、小米、微软、今日头条、Teambition、StackOverflow、Pinterest、人人、华为、企业微信、酷家乐、Gitlab、美团、饿了么和推特等第三方平台的授权登录。