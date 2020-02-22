---
title: 每周总结第三十一期
date: 2020-02-22 18:48:00
categories:
- 每周分享
tags: 每周分享
---
> 本周是2020年的第八个周末。    
> 这里记录过去一周，我的一些总结。

![weekly-31](http://img.liugezhou.online/weekly30.png)

<!--more-->

### Feeling 
> 读书与电影会扩展我们的生活半径,唯有读书人是最自由，唯有看电影人是最畅想。   
> 看一部电影，读一本书都有身临其境、思想解放的感受。   
> 而由于新时代下电影审查的严苛，读书便成为了另一个选择。    

### 指路明灯
> 世界上最长的电视剧《指路明灯》，该剧最初该剧由ABS在1937年1月25日首次播出,于2009年9月播出最后一集，合计播出18262集，该剧从电台广播剧开始，已播放了72年。吉尼斯纪录称它是世界上最长的电视剧。

### 视频号
> 微信公灰度发布视频号，目前进入视频号，视频不能暂停、不能快进、不能静音，只能点赞和评论。

### [拉里～特斯勒](https://www.bbc.com/zhongwen/simp/science-51569946?at_campaign=64&at_custom2=twitter&at_custom1=%5Bpost+type%5D&at_custom3=BBC+Chinese&at_medium=custom7&at_custom4=1B94F308-53C9-11EA-8759-A0FEC28169F1)
> 早期计算机科学标志性人物拉里·特斯勒（Larry Tesler）--“复制粘贴剪切”功能发明人,于2020年2月17日去世，终年74岁。    

### [MacOS中如何快读调出终端](https://www.zhihu.com/question/20692634)
> MacOS中没有快捷键打开终端的快捷键，这篇文章总结了通过 Automator.app设置快捷键打开终端。

### Commond + T  
> Commond + T快捷键可以在浏览器或者终端中开启一个新的标签、终端。

### IDEA过期
> 本周IDEA又一次过期(还可以打开，只有过期提示)，此次更新步骤是：    
> 菜单栏依次打开：help、register、Licence、server：     
>  根据提示，将之前licence-server address , 
> 由http://jetbrains-license-server改为     
> http://fls.jetbrains-agent.com    
>
> 若不是上述步骤，又看到了一篇过期激活教程：https://mp.weixin.qq.com/s/WwLSaNCHL7FeB2mOxNt2dw

### https://www.npmjs.com/
> 查看npm包基本信息，包括周下载量、版本号、证书类型、包大小、文件数量、Issues、仓库地址、包使用介绍等等。

### 包管理工具  
![packagetools](http://img.liugezhou.online/blog%2Fpackagetools.png)

### [How to Install MongoDB on CentOS 7](https://linuxize.com/post/how-to-install-mongodb-on-centos-7/)
> 一篇在CentOS7上安装MongoDB的最简单教程。 步骤如下： 
> 1. `vi /etc/yum.repos.d/`       
> 2. 编辑内容如下： 
```[mongodb-org-4.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.0/x86_64/
gpgcheck=1  
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.0.asc
``` 
> 3. `yum install mongodb-org(验证安装结果：rpm -qa |grep mongodb)`    
> 4. 启动服务：`sudo systemctl start mongod`、    
>    停止服务：`sudo systemctl stop mongod`、   
>    修改配置文件后重启：`systemctl restart mongod`     
> 5. MongoDB默认端口上27017，检查端口是否开启：`netstat -natp | grep 27017`
> 6. `mongo`，验证服务开启，进入命令行可查看版本：db.version();     
> 7. 想要修改mongo默认端口，`vi /etc/mongd.conf`      

### 本周产出
> 本周总结了两篇博文：  
> + [ssh远程登录服务器的一些问题](https://www.liugezhou.online/2020/02/18/ssh%E8%BF%9C%E7%A8%8B%E7%99%BB%E5%BD%95%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E4%B8%80%E4%BA%9B%E9%97%AE%E9%A2%98/) 
> + [从本地发布上线和更新服务器的Node.js项目](https://www.liugezhou.online/2020/02/21/%E4%BB%8E%E6%9C%AC%E5%9C%B0%E5%8F%91%E5%B8%83%E4%B8%8A%E7%BA%BF%E5%92%8C%E6%9B%B4%E6%96%B0%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84Node.js%E9%A1%B9%E7%9B%AE/)
