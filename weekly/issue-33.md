---
title: 每周总结第三十三期
date: 2020-03-01 10:11:00
categories:
- 每周分享
tags: 每周分享
---
> 本周是2020年的第十个周末。    
> 这里记录过去一周，我的一些总结。

![weekly-33](http://img.liugezhou.online/blog/weekly33.jpg)

<!--more-->

#### Feeling
> DONE IS BETTER THAN PERFECT.

#### 飞书
> 飞书被微信屏蔽了  
> 报道飞书被微信屏蔽的媒体被微信屏蔽了  
> 报道报道飞书被微信屏蔽的媒体被微信屏蔽的媒体被微信屏蔽了      
> <p align="right">DIYGOD</p>

#### [网络信息内容生态治理规定](http://www.cac.gov.cn/2019-12/20/c_1578375159509309.htm)
> 👆 2020年3月1日开始，多条新规开始实行，其中网络条例带来的好消息表明：以后网络信息内容可能不会有坏消息了。

#### Github打开新标签页
> Github上存在这一个明显的问题是，很多的第三方网页都是在当前标签页打开，对开发者来说很不友好，作为一个这么大的网站，或许是有其什么设计考虑吧。

#### [nprogress](https://github.com/rstacruz/nprogress)
> 👆一个超轻量进度条的开源库，使用极其简单。

#### node项目基础第三方包
> 搭建一个node后端项目编写接口的时候，下面是在构建基础项目的时候依赖的第三方包：        
> express：基于Node.js平台的web应用开发框架     
> mysql：连接数据库     
> body-parser:body-parser是非常常用的一个express中间件，作用是对post请求的请求体进行解析    
> boom：封装了状态码接口错误的返回信息，使用用例(boom.NotFound(),boom.badRequest(),boom.gatewayTimeout()等)    
> jsonwentoken:后台生成给前端的token数据，通过sign方法生成,通过verify方法解析。
> express-jwt: 除白名单之外的接口，进行token是否过期验证，如果未过期，使用verfify进行token解析。 
> express-validator:是一个功能强大的表单验证器，它是 validator.js 的中间件，使用 express-validator 可以简化 POST 请求的参数验证
> crypto: 加密方式。    
> cors: 解决跨域问题。  
> 等。

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

#### tar命令解压文件造成目录权限修改
> 如果在指定解压时指定参数-no-same-owner(即 tar -no-same-owner -zxvf xxx.tar.gz),则会将执行该tar命令的用户作为解压后的文件目录的所有者。这是因为tar命令在解压时会默认指定参数--same-owner。     
> 简言之，如果使用tar命令导致文件目录权限修改,可添加-no-same-owner参数。

#### END
> 表面上，每个人都在强调自己有独立的人格，但是实际上，只有与他人稍稍有所不同，我们就会怕的要死，时刻都在提醒自己，一定要装的与其他人一致。  
> <p align="right">前方的路^体制与个性</p>