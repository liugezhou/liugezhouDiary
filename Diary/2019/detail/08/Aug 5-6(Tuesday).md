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




