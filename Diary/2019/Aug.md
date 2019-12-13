# Aug-01,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### 博弈论相关讨论
> 今天看到一道非常有意思的关于博弈论的题目，感觉非常非常的有意思。在此之前先讲个故事，以下的故事情节设计主要是为了说清楚这个题目。

> 那么我就开始讲故事了：

> 那是在某年某月的某一日，你所在的村子里突然国王来视察了，国王来视察主要因为听说你们村有三个骁勇善战的士兵逃避在家。

> 国王偷偷的进村后，发现三个士兵聚在一起斗地主。

> 桌子上零零碎碎的有几百个金币，看得出这个逃兵士兵玩的很嗨。

> 国王看着他们玩了一会，思索了一阵后，于是上前问道：能不能加上我一块玩啊，看你们好嗨哦。

> 士兵三个看着这个不速之客，穿的花枝招展的想必非常有钱，其中一人问道：斗地主三个玩最有意思，加上你我们玩还有什么意思啊？

> 国王说道：那要不这样吧，我出一万金币，你们不用出钱，我制定一个规则，咱们一起玩怎么样？

> 三个士兵均感叹这么好的事，且先听听这个不差钱的人怎么说。

> 国王吩咐下人往桌上摆了一万金币，说道：

> 这里是一万金币，你们三个人中自己讨论如何分配这一万金币，但是有以下条件：

> 1.你们必须是依次按顺序出金币的分配方案。
> 2.全部人员进行分配方案的投票（包含自己也能对自己投票）。
> 3.投票人数直到大于你们总人数的1/2（不包含1/2）的人同意金币的分配方案后，则游戏结束。若小于等于1/2，则分配方案的人被处死，游戏继续，被处死的自然不能进行后续的投票。

> 国王说完之后，这三个士兵便陷入了深思之中......

> 那么问题来了：如果你是三个士兵中的一员，你会选择第几个进行金币的方案分配？你会怎么分配？

> 这是一道很有意思的博弈论题，在进行如上思考之前，我们有两个条件也是必须要遵循的（这两个条件很重要，请牢记在心在代入思考）：

> 1. 这三个士兵都是绝顶聪明的人，且他们是理性的。
> 2. 这三个士兵的人性都是丑恶的。

> 然后到此为止，题目讲解完毕，你现在可以完全忽略刚才那个不怎么样的故事，对这个金币分配方案进行思考。

> 如果是你，你会怎么选择呢？
</p>
</details>

---

# Aug-02,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Some people hear theirs own inner voices with great clearness.And they live by what they hear.Such people become crazy,or they become legends*</u>
> 有些人能清楚的听清自己内心深处的声音，并以此行事。这些人要成了疯子，要么变成了传奇。

## **Plan**
|      标签      | 记录  | 评价  |
| :------------: | :---: | :---: |
| 学习TypeScript |   简单瞅了一眼    |  ⭐⭐   |

</p>
</details>

---
# Aug-05~06,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Today is a begin!*</u>
> Today is a begin

## **Plan**
|        标签         |    记录    | 评价  |
| :-----------------: | :--------: | :---: |
| aiyouH5项目开发记录 | 一点点填坑 |  ⭐⭐   |

## **Record**
##### stylus记录
> + 语法方面、不用括号、层层嵌套
> + 全局引入css样式，$
> + 也可以全局引入一个CSS方法

#### 1像素边框问题
> 引入了border.css之后,可以直接使用class。比如`<div class="border-bottom"></div>`

#### 引入iview-UI组件库
> 出现一个问题：npm install iview的时候，总是不正确，后来发现是版本的问题。  
> 然后，新建了一个工具类文件，将iview的按需引入组件，减少体积。

#### 引入vue-awesome-swiper
> 使用很简单，直接看swiper官方文档就好了。

#### better-scroll
> + npm install better-scroll --save  
> + 在我的现在开发的这个项目中，home页面：
>
>    .main
>   position absolute
>    top 0
>    left 0
>   right 0
>    bottom 0
>    overflow hidden
>   ……………………
>   import Bscroll from 'better-scroll'
>   ……………………
>   this.scroll = new Bscroll(this.$refs.mainwapper)----mounted中

</p>
</details>

---

# Aug-07,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Dont't foget the things you once owned.Treasure the things you cann't get. Dont't give up the things that belong to you and keep those lost things in memeory.*</u>
> 曾经拥有的，不要忘记。不能得到的，更要珍惜。属于自己的，不要放弃。已经失去的，留作回忆。

## **Plan**
|      标签       | 记录  | 评价  |
| :-------------: | :---: | :---: |
| aiyouH5项目构建 |       |  ⭐⭐   |
|                 |       |       |


## **Record**
---
#### 关于iview的按需引用
> Yesterday night,那个ivew的下拉就是整不出来，今天终于试了出来，原因是这样的:  
> 从官网上我们可以看到按需引用是这么说的：
> + 借助插件 babel-plugin-import可以实现按需加载组件，减少文件体积。首先安装，并在文件 .babelrc 中配置：  
> + 然后这样按需引入组件，就可以减小体积了：  
>     
>     import { Button, Table } from 'iview';
>    Vue.component('Button', Button);
> +`特别提醒`：按需引用仍然需要导入样式，即在 main.js 或根组件执行 import 'iview/dist/styles/iview.css';

> 而我因为使用了`import iview from './assets/utils/iview'`这样的方法，上面的特别提醒说好了在main.js中引入，而我却在ivew.js中引入了，故而产生了问题。

> 没有想到的：后来又有问题了，点击又无缘无故没有反映了，然后我把之前的那个fastclick注释掉的东西放开就可以了。

#### axios学习
> + axios请求方法：get\post\put\patch\delete\
> `get`: 获取数据  
> `post`: 提交数据（表单提交、文件上传）  
> `put\patch`: 更新数据，`put`将所有数据推送到后端，`patch`只将修改的数据推送  
> `delete`: 删除数据

> + 数据上传的两种方式：`form data`(表单提交图片、文件上传) 和`application json`
> 
> + axios并发请求
>
>     axios.all([
>         axios.get('/index.json'),
>         axios.get('/home/json')]
>     ).then(axios.spread((dataindex,datahome) =>{
>       console.log(dataindex)
>       console.log(datahome)
>     }))
> 
> + axios创建实例--用于请求不同的域名或者超时时间的时候有用
> 
>   let instance = axios.create({
>       baseURL:'https://locahost:8080',
>       timeout:1000
>   })
>   instance.get('./data.json').then( res=> {})
> 
> + axios配置参数
>   `baseURL`:请求的域名或者基本地址。
>   `timeout`:接口超时时间设置
>   `url`: 请求的路径
>   `method`: 请求方法（五个）
>   `headers`:设置请求头
>   `params`:请求参数拼接在url上
>   `data`: 请求参数放在请求体上
> 
> + axios:全局配置、实例配置、请求配置
> 全局配置：axios.default.beseURL、axiso.default.timeout
> 实例配置如上代码
> 请求配置如上代码
>  
> + 拦截器
> 在请求或响应被处理前拦截他们处理，可分为`请求拦截器`和`响应拦截器`
> axios.interceptors.request(response).use( config => {
>   //在发送请求前做些什么
>   return config
> },err => {
>   //请求错误的时候做点什么
>   return Promise.reject(err)
> })
> 
> 
> 
> 引申一：路由组件采用按需加载。
>  

</p>
</details>

---
# Aug-08,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*It doesn't matter if the guy is perfect or the girl is perfect, as long as they are perfect for each other.*</u>
> 那个小伙子是否完美，或者那个姑娘是否完美都不重要，只要他们珠联璧合。

## **Plan**
|        标签         | 记录  | 评价  |
| :-----------------: | :---: | :---: |
| axios封装，项目运用 |       |  ⭐⭐   |
| 图片优化文章的学习  |       |       |
| vant组件的引入使用  |       |       |

## **Goals**
> 今天主要首先学会vant-UI组件的灵活使用。   
> 如果还有时间、心情的话对axios的使用进行封装并在醒目中进行测试。  
> 最后实在还有时间的话，对图片优化的文章进行透透的学习。  
> 

</p>
</details>

---

# Aug-09,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*The truth is a beautiful and terrible thing,and should therefore be treated with great caution.*</u>
> 真相是一种美丽又可怕的东西，需要格外谨慎地对待。

## **Record**
> 今日首先主要是解决压缩文件的显示问题。

> 然后调试接口，对axios进行封装，接口数据读取流畅、代码清晰。

> iview-UI组件适合PC端、vant适合移动端但是书写起来总觉不对劲，所以了解一下elmentUI。

## **Summary**
|        标签        |         记录          | 评价  |
| :----------------: | :-------------------: | :---: |
| 压缩文件的显示问题 | 浏览器缓存问题，无bug |  ⭐⭐   |

</p>
</details>

---
# Aug-12,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*I was blessed to hava in my life.When I look back on these days,I'll look and see your face.You were right there for me.*</u>
> 在我的生命中有你是多么的幸运。当我回忆过去，眼前就会浮现你的脸庞，你总在那守候着我。


## **Plan**
>这里记录我的一天，需要去留意的事。

> + 首先对之前遗留的关于jsonp的学习，继续进行。
> + 其次整理一下已经写过的关于Vue2.0音乐的文章，对知识点进行梳理。
> 
## **Summary**

|            标签            |                        记录                        | 评价  |
| :------------------------: | :------------------------------------------------: | :---: |
| Vue-2.0音乐APP文章重新梳理 | 之前写了八章的内容，今天重新整理了四章，做了个回顾 |  ⭐⭐⭐  |
|    JSONP原理语法的掌握     |            简单梳理了一下，对其API了解             |  ⭐⭐⭐  |

</p>
</details>

---

# Aug-13,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Excuse me,Can I change my order please*</u>
> 打扰一下，我能换个菜吗？
#### <u>*I hear what you say.*</u>
> 别再啰嗦了。
 #### <u>*Shake a leg*</u>
>快点，别墨迹了！（hurry）


## **Plan**
>这里记录我的一天，需要去留意的事。

> + 把Vue-2.0音乐APP第四章内容再次整理。
> + 将能用到的功能添加至aiyouH5项目
> 
## **Summary**

|       标签        |                记录                 | 评价  |
| :---------------: | :---------------------------------: | :---: |
| 项目aiyouH5的开发 |   今天主要是对项目接口等做了封装    |  ⭐⭐⭐  |
|    第四章内容     | Tonight对第四章内容做了一个新的补充 |  ⭐⭐⭐  |

</p>
</details>

---
# Aug-14,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
> 英语里面礼貌的口语：
#### <u>*May I have your name ?*</u>
#### <u>*Please have a seat.*</u>
#### <u>*Anything will do.*</u>
#### <u>*What's your question ?*</u>
#### <u>*After you*</u>

## **Plan**
>这里记录我的一天，需要去留意的事。
> 

## **Summary**
| 标签  | 记录  | 评价  |
| :---: | :---: | :---: |
|       |       | ⭐⭐  |
|       |       |       |
|       |       |       |


</p>
</details>

---

# Aug-15~16,2019

<details><summary><b>DETAILS</b></summary>
<p>

#### 昨日跟今日的日志没有写，主要是将aiyouh5的项目进行了一版测试与上线。

> + iOS微信版本中，input框失去焦点、键盘收起后不能再次点击的问题处理 
> + nginx反向代理，不能访问接口的问题处理 
> + 等一系列问题处理。 

> 眨眼之间，今天又来到了周五，时间真的飞快，where is my goal? I still search it!

> 就想小学总是盼望着周末的到来一样，不知不觉又回到了最初的起点，每周都在盼望着周末的到来，有时候我想是我想盼望着周末的到来，还是体制让我盼望着周末的到来，我其实挺喜欢工作的啊，但是毕竟很多人工作是厌烦、劳累的，只有那些享受工作带给自己乐趣且拿着高薪的人，感觉生活的充实与美好。

> 我们作为一个个体工作时间久了，可能乐趣不太好找，但是如果想要高薪的话，我觉得还是相对来说容易的，只要见贤思齐焉的努力就好了。

>周末快乐！
</p>
</details>

---
# Aug-19,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Miracles sometimes occur,but one has to work terribly for them.*</u>
> 奇迹有时候是会发生的，但是你得为之拼命。

## **Plan**
>这里记录我的一天，需要去留意的事。

> 什么也没干。

</p>
</details>

---

# Aug-20,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*We all live past,We take a minute to know someone,one hour to like someone,and one day to love someone,but the whole life to forget someone.*</u>

## **Plan**
>这里记录我的一天，需要去留意的事。

> 掘金小册关于《前端性能优化》的学习。


## **Summary**
> 写《刑事附带民事起诉状》文档。
> 关于aiyouH5的项目也没有了下文，两天的时间没有任何的进展，心中不免产生一丝的焦虑，甚至两丝。

> 不知道是否有妄想迫害症，对于未知的事物总是有一种莫须有的不安全感，那个时候，心中的坚定乐观、真诚、诚实、不知怕了什么，不敢出面。

> 归根结底还是没有找到心中的追求。

</p>
</details>

---
# Aug-21,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*The secret of being miserable is to have ieisure to bother about whether you are happy or not*</u>
> 痛苦的秘密在于有闲工夫担心自己是否幸福。

## **Plan**
> 这里记录我的一天，需要去留意的事。

> 完善《刑事附带民事起诉状》文档。
> aiyouH5项目关于爱心轨迹模块、完善。
> Vue.js官方文档的再次学习，总结成一篇博客。
## **Summary**
> 以上全部完成，只是博客写了一些，还需继续总结。

</p>
</details>

---

# Aug-22,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*The important thing in life is to have a great aim and the determination to attain it.*</u>
> 人生重要的事情就是确定一个伟大的目标，并决心实现它。

## **Plan**
>这里记录我的一天，需要去留意的事。

> No.1：继续过Vue.js的官方文档，完善博客内容。
> No.2:《人类简史》

## **Summary**
|    标签    |              记录              | 评价  |
| :--------: | :----------------------------: | :---: |
| Vue.js文档 |   文档过到后面又开始耍无赖了   |  ⭐⭐   |
|  人类简史  | 读史让人明智，但却不能心存怨念 |  ⭐⭐   |



</p>
</details>

---
# Aug-23,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*If a man empries his purse into hie head. no man can take it away from him.An investment in knowleage always pays the best interset.*</u>
> 倾尽所有追求知识，没有人能夺走它；向知识投资，收益最佳。

## **Plan**
>这里记录我的一天，需要去留意的事。

> No1.继续整理Vue2.0APP音乐项目。

## **Summary**
| 标签  | 记录  | 评价  |
| :---: | :---: | :---: |
|       |       | ⭐⭐  |



</p>
</details>

---

# Aug-26,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*如果看够了不对的，质疑的、怀疑的、过于不反常的，那么接下里的一步：应该去追求那些你认为对的，值得去追寻的东西。*</u>

## **Plan**
> 这里记录我的一天，需要去留意的事。
> First of all,最重要的一件事是上周的周分享停滞了一下下，不论如何今天得补上了。
> Second,继续对Vue-2.0APP音乐的学习贯彻到底。

## **Summary**
> 上周的周分享没有什么干货，简单的告诫了一下自己要去追寻对的事情，不要在其它事情上浪费太多脑细胞。

> 在Vue2.0的音乐APP学习中，关于音乐的播放地址拿到后不能播放的问题，困扰了许久，最后还是没有解决。

> 晚上回家本来准备继续整整关于音乐播放没有声音的问题，然后为了学会英语，又看了一遍《功夫熊猫》。之所以回想起这个电影，是因为在金山词霸APP上视频英语中看到龟仙人对Kung FU Panda 的教诲：'Yesterdat is a history,Tomorrow is a mystery,But Today is a gift,This is why it is called today is "Precent"'.

> 细水长流也好，虽然收获不是很多，但是在开始养成一个用碎片时间去贯彻终生英语学习的目标，也算是甚好的！

</p>
</details>

---
# Aug-27,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*But I didn't know who I was.How could I? And how could any of us?*</u>
#### <u>*Because for the first 25years of our lives,we are trained to listen to voices that not our own.*</u>
#### <u>*Parent and professors fill our heads with wisedom and information, and then employers and mentors take their place and explain how this world really works.*</u>
> 《Back to Campus 》---Steven Spielberg.

## **Plan**
> 这里记录我的一天，需要去留意的事。
> 
> 不论如何，播放器的音乐得出声音了。
> 
## **Summary**
> 谁曾想到音乐不出声的原因竟然为监听单词`watch`写错了。

> 然后继续跟着课程嘚吧嘚的学习了会，差不多算是攒出来一章，只是代码跟着敲完了，文章的总结还得后续的跟进啊。

> 今天aliya去学车，晚上我还没想好到底回家还是去小盘子那里，下班！

> 去了小盘子那里。

</p>
</details>

---

# Aug-28,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Only those who have the patience to do simple things perfectly ever acquire the skill to do difficult easily.*</u>
> 只有有耐心圆满完成简单工作的人，才能轻而易举地完成困难的事。

## **Plan**
>这里记录我的一天，需要去留意的事。

> Vue2.0APP音乐首先将第七章代码跟随编写完毕，完后两篇文章用来记录知识点。
> 估计今天也就差不多了。

## **Summary**
> 今天主要是跟着课程写了写代码，播放器的播放还有歌词的显示完毕，推荐客单向music-list数据传送完毕。

> 差不多就是跟着课程敲代码，没有过多的知识总结，也就是第一遍跟着课程走一走。

> 惊讶别人家的前端开发工程师怎么这么牛叉，我还需要多少的时辰与努力还有天赋才能追的上呢？



</p>
</details>

---
# Aug-29,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Life can only be understood backwrads,but it must be lived forwards.*</u>
> 要理解人生，需要向后看，但要更好地活着必须向前看。

## **Plan**
>这里记录我的一天，需要去留意的事。

>继续写写Vue2.0的视频教程吧，处处都是知识点，处处教育我们如何做人。

## **Summary**
> 继续从视频中学习，开始有了一点门路，有了那么一些感觉，翻来覆去其实就是那么几下子。

> 今天主要是将排行页面做了一个学习与代码的开发。

> 今天下班的路上还可以看一看崔老师的《有话说》，敢于写书的人，写出来让别人去评判，这家伙，都是脸皮厚、差不多也算行的正的人。


</p>
</details>

---

# Aug-30,2019

<details><summary><b>DETAILS</b></summary>
<p>

## **Daily Sentence**
#### <u>*Today is a Friday,Nice Day!*</u>

## **Plan**
>这里记录我的一天，需要去留意的事。
> 这家伙，没有想到，整个一周都在学习Vue2.0的视频课，进展竟然是这么的慢，今天得下点功夫去好好学一会了。

## **Summary**
> 说好了的好好学习，到了下午三点多就什么也不想干了。

> 驱动力啊驱动力，年纪也不小了，怎么还是耐不住性子呢？

> 其实也没什么，可能也正常吧，又何必让自己活得太累呢。

</p>
</details>

---
