---
title: 每周总结第三十三期
date: 2020-03-01 10:11:00
categories:
- 每周分享
tags: 每周分享
---
> 本周是2020年的第十个周末。    
> 这里记录过去一周，我的一些总结。

![weekly-33](http://img.liugezhou.online/blog/weekly33.png)

<!--more-->

#### Feeling
> DONE IS BETTER THAN PERFECT.

#### [网络信息内容生态治理规定](http://www.cac.gov.cn/2019-12/20/c_1578375159509309.htm)
> 👆 2020年3月1日开始，多条新规开始实行，其中网络条例有一条好消息：以后网络信息内容可能不会有坏消息了。

#### [nprogress](https://github.com/rstacruz/nprogress)
> 👆一个超轻量进度条的开源库，许多大型项目有用。

#### node项目基础第三方包
> 搭建一个node后端项目编写接口的时候，有一些基础第三包可做基础项目的应用：  
> express、mysql、body-parser、boom、express-jwt、jsonwentoken、express-validator、crypto、cors等。

#### 使用nvm安装管理nodejs
> 本周在项目部署中遇到有关nodejs版本切换的问题,终于还是碰到了nvm。    
> 安装过程遇到一个小坑，要先删除之前的node，下面总结一下安装nvm的过程：   
> + 1. sudo rm -rf /usr/local/lib/node_modules # 删除全局 node_modules 目录      
> + 2. sudo rm /usr/local/bin/node  # 删除 node     
> + 3. cd /usr/local/bin && ls -l | grep "../lib/node_modules/" | awk '{print $9}'| xargs rm    # 删除全局 node 模块注册的软链  
> + 4. curl安装：curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash(试了好几次)    
> + 5. nvm --version 查看安装版本       
> + 6. 查看服务器端可用的 Node.js 版本:nvm ls-remote    
> + 7. 安装 8.* LTS 版本 (长久维护版本) 和12版本：nvm install 8.11.2 （12）   
> + 8. 查看本地可用的node.js版本： nvm list 
> + 9. 切换node版本 ：nvm use 8   
> + 10. 设置默认版本：nvm alias default 12

