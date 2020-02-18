---
title: ssh远程登录服务器的一些问题
date: 2020-02-18 01:35:00
categories:
- 服务端
tags: zsh
---
### 一、zsh
#### 1.zsh切换
> 首先确保本地终端shell是zsh。更改详见[每周总结第二十七期](https://www.liugezhou.online/2020/01/10/%E6%AF%8F%E5%91%A8%E6%80%BB%E7%BB%93%E7%AC%AC%E4%BA%8C%E5%8D%81%E4%B8%83%E6%9C%9F/)
> <!--more-->
#### 2.zsh配置连接服务端别名
> 这篇短文要解决的是这么一个小问题：购买了ECS，获得了公网IP，知晓密码。 
>
> 这个时候不想在sheel中每次输入`ssh root@47.104.85.127`去连接服务器。   
>
> 这个时候就可以更改.zshrc配置文件(`vi ~/.zshrc`).    
> 在该配置文件中加入以下一段声明即可：  
> `alias ssh_liugezhou="ssh root@47.104.85.127"`
> 
> 更改完成后，执行`source ~/.zshrc`命令。   
> 这个时候在终端直接输入:`ssh_liugezhou`,接着输入服务器密码即可。   

### 二、服务器信息
#### 数据盘与磁盘空间
> 如果买了新的数据盘,数据盘需要额外挂载，没有购买情况下，默认是挂载了一个系统盘，系统盘是用来安装操作系统的，如果网站应用都跑在系统盘上，一旦重装系统，所有网站数据资料都会丢失，若挂载在数据盘上，可以提高安全性，重装系统用户资料也不会丢失，查看是否含有数据盘的命令是：       
> `fdisk -l`    
> 如果只有一个 Disk /dev/xvda 则说明没有新的数据盘。    
>
> 查看磁盘空间的命令是：    
> `df -h`

### 三、配置root用户管理
#### 1.增加用户
> 通过命令,创建新的用户liugezhou。  
> `useradd liugezhou`   
> 添加完用户后可在  /home下看到用户名。 
> 然后输入 `passwd liugezhou`为用户设置密码。
> 回车输入该用户的密码(两次)。  

#### 2.删除用户
> 语法：`userdel [-rf] liugezhou`   
> userdel可删除用户账号与相关文件，若不加参数，则仅删除用户账号，而不删除相关文件。 
> -r: 删除用户登入目录以及目录中所有文件。  
> -f: 强制删除用户(甚至当用户已登入Linux系统时此选项依旧生效)

#### 3.查看用户信息(uid、gid、组)
> `id liugezhou`

#### 4.为新用户添加sudo权限
> #首先登录 root 账户   
> `visudo `   
> #找到如下行数   
> `root  ALL=(ALL)   ALL`   
> 添加 `liugezhou  ALL=(ALL)  ALL`

#### 5.切换用户
> `su username`

#### 6.相关文件
> /etc/passed文件：用户的配置文件，记录用户的各种信息。 
> /etc/shadow文件：口令的配置文件   
> /etc/group文件：组的配置文件，记录Linux包含的组的信息。   

#### 7.[更多Linux用户和用户组的管理](https://www.runoob.com/linux/linux-user-manage.html)

### 四、配置本地无密码ssh登录
#### 1.查看本地是否已配置私钥、公钥。   
> 进入本地用户的根目录：cd /Users/liumingzhou   
> 该目录下，查看是否包含id_rsa和id_rsa.pub    
> 如果不包含，在本目录下依次执行以下命令：  
>`mkdir .ssh`   
>`cd .ssh`
> `ssh-keygen -t rsa -b 4096 -C "abc@gmail.com"`    
> `eval "$(ssh-agent -s)"`  
> `ssh-add ~/.ssh/id_rsa`

#### 2.服务器根目录下配置
> 登入服务器，进入/root目录下，首先查看是否有.ssh目录，若没有： 
> 遵从步骤一。之后：      
> `vi .ssh/authorzed_keys`  
> 将本地的公钥放进到`.ssh/authorzed_keys`.  
> `chomd 600 authorzed_keys`    
> `sudo service ssh restart`    
> 这个时候，直接输入ssh_liugezhou,即可以直接登入到服务器。

### 五、修改服务器默认登录端口[未进行实战]
> Linux默认登录的端口是22[0-65536],0-1024端口尽量不使用，可能会被系统占用
> 更改端口，输入：`vi /etc/ssh/sshd_config` 
> 修改端口Port字段即可，也可以修改 PermitRootLogin(是否允许root登录)。  

### 六、配置iptables和Fail2Ban增强安全防护[未进行实战]
> 暂不总结。

### 七、ECS服务器是否设置连接超时时间   
> 用SSH客户端连接linux服务器时，经常会出现与服务器会话连接中断现象，造成这个问题的原因便是SSH服务有自己独特的会话连接机制。 
> 解决方案：    
> 1、设置服务器向SSH客户端连接会话发送频率和时间    
> `#vi /etc/ssh/sshd_config，添加如下两行`  
> `ClientAliveInterval 60`     
> `ClientAliveCountMax 86400`    
> 注：ClientAliveInterval选项定义了每隔多少秒给SSH客户端发送一次信号；ClientAliveCountMax选项定义了超过多少秒后断开与ssh客户端连接  
> 2、重新启动系统SSH服务    
> ~~`service sshd restart`~~    
> 云服务器 ECS Linux CentOS 7 下重启服务不再通过 service 操作，而是通过 systemctl 操作。    
> + 查看：systemctl status sshd.service     
> + 启动：systemctl start sshd.service      
> + 重启：systemctl restart sshd.service    
> + 自启：systemctl enable sshd.service  

### 八、借助pm2让nodejs服务常驻
> 服务器下载pm2后，如果要启动一个app.js的项目(该文件内为一个连接http服务的段代码);    
> 如果使用`node app.js`，退出文件或者关闭终端，则该文件就不能访问了，这个时候可以使用pm2.   
> 启动项目：`pm2 app.js`    
> pm2启动列表：`pm2 list`   
> pm2查看某信息：`pm2 show app` 
> 查看pm2在线日志：`pm2 logs`   
> 关闭服务：`pm2 stop app`

##### 小技巧
> 在终端下或者VSCode中，或者idea中，如果想让光标回到行首，可以使用 ctrl + a，回到行尾，使用ctrl + e。
 