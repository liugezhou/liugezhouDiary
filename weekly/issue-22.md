## 每周总结第二十二期
> 这里记录过去一周，我的一些小总结。
 ![weekly-22](http://img.liugezhou.online/20191206weekly.jpeg)
<!--more-->
#### Feeling
> 推出一个新产品很难，组建一个能够持续推出新产品的团队更难。    
> 我最引以为傲的产品，就是苹果公司和我在苹果公司建立的团队。    
> <cite>史蒂夫·乔布斯</cite>

#### 消费者办手机号全面开启人脸比对
> 据工信部的相关规定，自12月1日起，电信企业需在实体渠道全面实施人像比对技术措施，人像比对一致方可办理入网手续。 
> 这意味着，今后，中国所有注册新SIM卡的手机用户都必须接受面部识别扫描。同时，规定要求电信企业部署“人工智能和其他技术方法”以检查注册SIM卡的人员的身份。  
> 今年以来，人脸识别技术在国内出现了一系列的负面新闻，比如曾红极一时的换脸软件——ZAO，还有一位大学教授起诉动物园违规采集面部信息的“中国人脸识别第一案”。这些事件背后，说明中国人脸识别行业缺乏统一标准，管理仍然比较混乱，对用户的隐私保护做得不到位。就像“办手机卡”这件事，已经有一些声音开始担心：电信运营商真的能保证我们的人脸数据不外泄吗,不会用于其他的某方面用途吗？

#### [华为作过的恶](https://github.com/evil-huawei/evil-huawei)
> Gitub上，本周star数凑凑上涨的一个项目：   
> 项目介绍：「由于部分内容被控评和删帖，已经无法在中文互联网搜索到，所以本项目将收集华为作过的恶，记录这些不应该被遗忘的历史。」

#### [一键抠图神器](http://www.picup.ai/#/)
> 识别图像中的人体轮廓，与背景进行分离.有人体抠图和物体抠图。   

#### 沙拉查词
> 一款浏览器插件，推荐。
> ![查词](https://user-gold-cdn.xitu.io/2019/10/21/16dec06bb7790bd3?imageView2/2/w/800/q/85)

#### [Grid 代码生成器](https://cssgrid-generator.netlify.com/)
> 可视化地配置 Grid，你可以设置行与列的个数、指定每个格子的类、长宽占比、行间距与列间距大小等，再一键生成 Grid 的 CSS 代码. 
> ![演示](https://user-gold-cdn.xitu.io/2019/12/6/16eda0f218272486?imageView2/2/w/800/q/85)

#### [GitHub中文排行榜](https://github.com/kon9chunkit/GitHub-Chinese-Top-Charts)
> GitHub中文排行榜，帮助你发现高分优秀中文项目、更高效地吸收国人的优秀经验成果；榜单每周更新一次.   

#### [浏览器中的页面](https://www.liugezhou.online/2019/12/03/No5.%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E7%9A%84%E9%A1%B5%E9%9D%A2/)
> 前段时间在《极客时间》上学了一个专栏，通篇略过，干货不少，但理解相当不够透彻，于是计划用几周的时间，对本专栏内容用作者的总结以及自己的相对逐字理解，来个通篇的文字记录学习，书读百遍，其义自现。  
> 本篇是这个专栏的第四章：[浏览器中的页面](https://www.liugezhou.online/2019/12/03/No5.%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E7%9A%84%E9%A1%B5%E9%9D%A2/)。本章分为八讲。

#### HTTP请求中的Form Data和Request Payload的区别
> 前端开发中经常会用到AJAX发送异步请求，对于POST类型的请求会附带请求数据。而常用的两种传参方式为：Form Data 和 Request Payload。    

> 方式一： Form Data形式    
> 当POST请求的请求头里设置Content-Type: application/x-www-form-urlencoded(默认), 参数在请求体以标准的Form Data的形式提交，以&符号拼接，参数格式为key=value&key=value&key=value...   
> 方式二：Request Payload形式   
> 如果使用AJAX原生POST请求,请求头里设置Content-Type:application/json，请求的参数会显示在Request Payload中，参数格式为JSON格式：{"key":"value","key":"value"...}，这种方式可读性会更好. 后端可以使用getRequestPayload方法来获取.     
> `Form Data 和 Request Payload 区别`
> 如果请求头里设置Content-Type: application/x-www-form-urlencoded，那么这个请求被认为是表单请求，参数出现在Form Data里，格式为key=value&key=value&key=value...      
> 原生的AJAX请求头里设置Content-Type:application/json，或者使用默认的请求头Content-Type:text/plain;参数会显示在Request payload块里提交。