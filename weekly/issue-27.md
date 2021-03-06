---
title: 每周总结第二十七期
date: 2020-01-10 20:41:00
categories:
- 每周分享
tags: 每周分享
---
> 本周是2020年的第二个周末。    
> 这里记录过去一周，我的一些总结。  
> 
> ![weekly-27](http://img.liugezhou.online/weekly27.jpeg)       
> <center>小狗钱钱</center>
>
<!--more-->

### Feeling
##### 阿坡坡（APP）
>
> 从前车马很慢,    
> 书信很远.
> 
> 如今，信息爆炸的网络时代,  
> 纵使刀山火海,    
> 阿坡坡都会找上门来。   
>    
> 他们千奇百怪, 
> 却又扮的一样的冬日可爱,
> 你不禁眼花缭乱。  
> 
> 它们和你相亲相爱,    
> 跟你说着恭喜发财, 
> 你喜逐颜开. 
>  
> 呀，这样的两小无猜,  
> 你情窦初开.
>    
> 一切，正中下怀. 
> 
> 然后，从这开始, 与阿坡坡的喜怒哀乐就掉了链子，纵使我才华横溢，也写不下去了。  
>
> 阿坡坡作为一名小三、四、五、六， 
> 焦虑了我的生活。 
> 当然这不是阿坡坡的错,    
> 是由于我内心的躁动零落,   
> 闲时的昏昏噩噩。    
>
> 记得，合理使用阿坡坡，幸福生活a o e(阿喔额).

### 小狗钱钱
> 《小狗钱钱》是由四川少年儿童出版社出版的一本图书。    
> 由王钟欣、余茜合译的一部来自德国作家博多～舍费尔(Bodo Schaffer)的作品。 
> 
> 这是一部很有意思的理财启蒙书籍，短小精悍，很值得花几个小时一看。  
> 我跟着书中的思路游走，发现了一件特别有意思的事：
>  
> 开始小狗钱钱让我们的小女主人公列出十个愿望，于是我也随之去想我的十个愿望，想了很长时间，天马行空的去做梦，最后也才想到八个。  
> 这其中很有韵味、很有意思的一件事就是去想这十个愿望的过程。    
> 在每想一个愿望的历程中，都在无比的考验你对这个世界、对自己的一些认知，发散思维激发想象力。
>
> 书中讲到的愿望相册、成功日记、理财的一些小知识、一些鸡汤等等都非常的耐人寻味。    
> 
> 推荐我的朋友们读一读。

### [vlog达人张子贺](https://space.bilibili.com/89944567?spm_id_from=333.788.b_765f7570696e666f.1)
> 「每30天学会一个新技能、新知识，并用文字和视频分享教程和指南。」   
> 
> 本周看了这个vlog博主的几个视频，里面讲到Rap、冥想、谷歌面试、远离手机等等挑战以及他之前的一些分享。        
> 获益匪浅，很是漂亮。期待下一个30天挑战。
> <cite>公众号《张子贺》</cite>

### [北京公积金提取申请人可以网上办理](http://www.gov.cn/xinwen/2020-01/09/content_5467875.htm)
> 2020年1月10日起，北京公积金提取申请人可以网上办理。   
> 北京住房公积金网：http://gjj.beijing.gov.cn/  
>
> <cite> [官网公告](http://gjj.beijing.gov.cn/web/zwgk/_300583/zxzysx/675803/index.html)</cite>

### [2020微信公开课PRO](https://baijiahao.baidu.com/s?id=1655219878385555103&wfr=spider&for=pc)
> 1月9日，2020微信公开课PRO在广州正式启动。
> + 2020年1月9日，小程序框架正式开放，可支持小程序在硬件运行. 
> + 2020年1月10日，小程序“订阅消息”能力上线，

### [深海网站](https://neal.fun/deep-sea/)
> 这个网站可以不停往下拉，看看每个深度的海底都有些什么生物,可以一直拉到10000多一点米。    
> 对于海洋、水下世界感兴趣的人儿来说，这真是一个不错的网站。      

### isometric Contributions
> 这个插件有点酷 ，Isometric Contributions：它可以让我们 Github 的贡献图变成 3D 效果：
>
> 
>![浏览器插件](http://img.liugezhou.online/weekly27Github.png)


### zsh 和 bash的区别 以及切换
> 从 macOS Catalina Beta 版开始，zsh (Z shell) 是所有新建用户帐户的默认 Shell。 
> zsh完美兼容bash，并且有比bash更强大的功能，用起来也比bash更优雅。
> 
> 切换bash与zsh命令，在终端中输入：`chsh -s /bin/zsh`或者`chsh -s /bin/bash`。    
>
> 切换zsh后，shell由原来的bash变成了zsh，打开终端，发现终端中名字重复显示、或者其他异常显示情况，修改为： 

```
touch ~/.zshrc
echo "export PS1='%n %c $'" >> ~/.zshrc
source ~/.zshrc
```
> 最后，如果你在bash命令行下的`.bash_profile`文件中有maven等的配置，需要添加至`.zshrc`中。


### [Mithril框架入门](https://mithril.js.org/)
> Mithril 是一个前端 JS 框架，只有 9.5KB，如果你感到 React 或 Vue 太重，应该看看这个框架。
> Github Star数：11930.
>
> 周末在家花了一些时间，翻译了一下官方文档的介绍和安装使用模块，提交至:https://github.com/liugezhou/Mithril

### npm init --yes
> npm init 命令用来初始化一个简单的 package.json 文件。 
> 而如果想要偷懒步免去一直按 enter，在命令后追加 --yes 参数即可，其作用与一路下一步相同。
```
npm init --yes
```