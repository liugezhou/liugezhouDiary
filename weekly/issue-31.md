---
title: 每周总结第三十一期
date: 2020-02-20 13:00:00
categories:
- 每周分享
tags: 每周分享
---
> 本周是2020年的第八个周末。    
> 这里记录过去一周，我的一些总结。
![weekly-31](http://img.liugezhou.online/weekly30.png)

<!--more-->
### Feeling  
> 关注什么就看到什么。自己却还是不知道要干什么。  

### [拉里～特斯勒](https://www.bbc.com/zhongwen/simp/science-51569946?at_campaign=64&at_custom2=twitter&at_custom1=%5Bpost+type%5D&at_custom3=BBC+Chinese&at_medium=custom7&at_custom4=1B94F308-53C9-11EA-8759-A0FEC28169F1)
> 早期计算机科学标志性人物拉里·特斯勒（Larry Tesler）于2020年2月17日去世，终年74岁。    

### [How to Install MongoDB on CentOS 7](https://linuxize.com/post/how-to-install-mongodb-on-centos-7/)
> 一篇在CentOS7上安装MongoDB的简单教程。 步骤如下： 
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
