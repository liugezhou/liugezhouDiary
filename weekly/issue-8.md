## 每周分享第八期
>**这里记录过去一周，我的关注以及值得记录的东西。**

#### [在线流程图工具](https://www.zenflowchart.com/)
> 简单好用的在线流程图工具。
> 
> 之前开发项目的时候，画过【流程图】，为此还专门下载软件进行点点熟悉画图。
>
> 这个网站简单、易用，不论你是做什么工作，在需要绘制流程图的时候不必用专有软件，可直接打开此网站，使用此网站提供的服务进行流程图的绘画。

#### 面包多--为创造者创收
> 面包多致力于帮助创造者(开发者，写作者，设计师等)获得收入，创造者可以上传作品到面包多，设置价格，然后获得出售链接，这些链接可以放置于任何地方，以供用户购买这些创造成果.
> 
> 我在此平台发布了一篇文章：[作为一名开发者应该收藏的网站](https://mianbaoduo.com/product/show/mbd-Yp2Ukw==)

> 内容即为本博客的【工具收藏】。

> 未曾想到想到还收到一个付费。

> 大概了解了一下此产品，基于知识付费方面。

#### 今日热榜  APP
> 知乎热搜、微博热搜、微信热搜、澎湃新闻、豆瓣、百度等等等热点。

>此APP便是提供这样一个内容。可通过自己的订阅，查看当下舆论新闻的热搜、热点事件。

#### 华为 HarmonyOS 鸿蒙系统
> 这是本周五的一大热点事件。 
> 根据余承东介绍，“鸿蒙”具备以下特点：
> 
> 1、基于微内核、面向全场景的分布式操作系统。  
> 
> 2、面向的是“下一代”的 IOT 场景，包括已发布的荣耀智慧屏，规划中的PC、手表手环、车机、音箱、耳机、VR 设备，未来还会延伸至工业、航空航天等领域。 
> 
> 3、开源。
> 
>##### 微内核
> “内核”指代的是操作系统中的核心架构，大体可分为“宏内核”与“微内核”，前者代表为 iOS 与安卓，后者代表是谷歌 Fuchsia 与鸿蒙。两者的区别在于：内核越小，涉及的操作系统代码越少，进程越简单。

> 由于宏内核包含的系统服务很多，比如文件系统、进程管理、内存管理、声卡显卡驱动程序等，调用起来需要强大的处理器，所以适用于手机、电脑、PC 等产品；但微内核只提供诸如 CPU 管理、进程调度等最基础的功能，其余服务均以后期叠加的形式完成，因此更适合对于运算需求没那么高的手表、智能家居等 IOT 设备。
> ##### 分布式
> 分布式技术是 IoT 厂商提出“万物互联”的基础。从手机、到手表、到智能家居、汽车，不同设备对于系统的运算需求（本地/云端）、内存处理都不一样，而“分布式”则是用来连接这些设备的操作系统。
>…………
> ###### 更多文章内容： [鸿蒙初问世，华为敛锋芒](https://mp.weixin.qq.com/s/v61phlapZi5sXiOpIGJJaw)

#### Taro与uni-app
> 开发一次，到处运行，是每个程序员的梦想。
> 对Taro与uni-app两个框架做了一个小小的对比，对于框架的选型我已然有了自己的选择。下面为简单结论。
> 
> |描述	|Uni-app：10412	|Taro：20662	|
> |---|---|---|
> |技术栈|	Vue.js|	React.js|	
> 案例|	案例丰富|	案例丰富|
> |微信小程序|	⭕|	⭕	|
> |支付宝小程序|	⭕	|⭕	|
> |百度小程序	|⭕|	⭕|
> |头条小程序	|⭕|	⭕	|
> |H5	|⭕|	⭕	|
> | App	|⭕|	⭕|	

> 公说公有理婆说婆有理,下面为两个框架各自的评测与开发者评测链接：    
> Taro官方评测：[Taro评测](https://juejin.im/post/5c90eb366fb9a070d4199cc9).  
> uni-app官方评测：[uni-app评测](https://ask.dcloud.net.cn/article/35867).  
> 开发者评测：[Taro vs uni-app](https://juejin.im/post/5c4ec383f265da613e229a67). 
>
> ######  开发者评测的简单总结：
> `质量对比`： 
>从两个项目的实际运行来看，uni-app的跨端效果更好（其实不止对比了官方demo，我们自己也写了小demo），特别是在H5平台相比taro要完善不少。  
>taro 的 dist 目录下不区分编译平台，同一时间仅可编译到一个平台，不支持多个平台对比查看运行效果；  
>uni-app 的 dist 目录区分编译平台，故支持同时编译到多个平台，可同时对比查看不同平台运行效果，这个体验是不错的，更有跨端开发的感觉。
另外uni-app的条件编译比较完善，这个在处理平台差异时很有用。
>
> `案例对比`： 
> 两个框架都在官网放上了众多案例，只是taro案例清一色是微信小程序，没看到其他端，难道大家使用taro，只是为了用react开发微信小程序，不需要跨端？  
综合比较，uni-app跨端质量更好，真实跨端案例也更多.

>`运行性能: `  
>taro在性能优化上做的更细致，使用uni-app需要自己注意代码优化。

> `开发体验`:  
> 都挺好。taro官方未特别推荐IDE，但提供了vscode支持的d.ts； uni-app推荐的开发工具是他自家的HBuilderX，用它可以不配环境，开箱即用.  

>`学习交流`:  
>另外文档角度，uni-app的文档比taro要完善，数了数交流群的数量，也是uni-app.

#### 微信小程序PC端内测
> 小程序在PC端的使用，正在内测，这是要移动端、PC端通吃的节奏啊。

> 大约是本周五该新闻被爆料，微信强调，希望通过这一探索，帮助用户在聊天场景中更连贯地使用小程序。

> 小程序的红利应该还未真正到来，一切都在酝酿之中。在我看来，一方面是因为苹果的应用商店在那卡着，另一方面就是生态的布局还在继续，很有可能像微信公众平台、微信读书一样，持续不断的给用户、给开发者一个学习使用的机会，成熟之时，便是爆发之日。

> 在此再插一句：这种垄断巨头做出来的产品是真的好，但是由于垄断天然特性，总是会损害一部分人的利益，大体上看可能会慢慢损害大多数，只是会如温水壶青蛙般不知情。慢慢被同化、无力反驳。垄断者的耐心布局给人方面却又使人感到恐惧。

#### [守望先锋 UI 组件库](https://haixiang6123.github.io/overwatch-ui-doc/#/start)
> 一个《守望先锋》游戏风格的组件库，基于 Vue.js。

####  视频学英语
> 金山词霸APP里面有个【视频学英语】模块，画风与抖音相似，推荐。下面为一个小段子的摘抄：
> [对话场景：一场最终面试，面试者对两个候选人进行面试提问]
>
> Interviewer：  
> 'You both are excellent.'  
> 'But we only have one vacant position.'
> 'Let me ask you three more questions.'  
> 'First of all:'  
> 'What's your hobby?'  

> Candidate 1:
> 'I enjoy delicious food.'  
> 'I know all the good restaurants in the city.'
>
> Candidate 2:
> 'I enjoy working extra hours.'  
> 'I love my work, my work is my hobby.'
> 
> Interviewer：
> 'What do you first thing when you get to work?'
>
> Candidate 1:
> 'I usually make a task list first,'  
> 'so that my whole day is organzied.'
>
> Candidate 2:
> 'I open the door'  
> 'I'm always the first one to work.'
> 
> Interviewer：
> 'What the last thing you do before leaving work?'
>
> Candidate 1:
> 'Close the door'   
> 'I enjoy being the last person to leave work.'
>
> Candidate 2:
> 'I copy the next day's tasks to my USB'  
> 'so I can bring it home and get started on the next day's work.'







