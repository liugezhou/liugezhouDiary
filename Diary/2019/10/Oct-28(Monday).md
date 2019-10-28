## **Daily Sentence**
#### <u>*Give a man a fish,and you feed him for a day.Teach a man to fish,and you get rid of him the weekends.*</u>
> 给他一条鱼，你可以喂他一天；教他钓鱼，周末就不会来烦你。

## **Plan**
>这里记录我的一天，需要去留意的事。

> Vue面试题。

## **Summary**
| 标签  | 记录  | 评价  |
| :---: | :---: | :---: |
|       |       | ⭐⭐  |

## **Record**
#### 从0到1自己构架一个vue项目，说说有哪些步骤、哪些重要插件、目录结构你会怎么组织
> 使用Vue-cli脚手架搭建、安装fastclick、better-scroll、1边框显示问题的border.css、引入reset样式文件，Vue-router、axios、根据开发业务挑选一个UI框架按需引入、目录结构的话，封装axios，统一调用风格和基本配置。

#### 你知道vue的模板语法用的是哪个web模板引擎的吗？说说你对这模板引擎的理解
> 模板引擎是以`业务逻辑层`和`表现层分离`为目的的，将规定格式的模板代码转换为业务数据的算法实现。    
> 它可以是一个过程代码、一个类，甚至是一个类库。不同的模板引擎其功用也不尽相同，但其基本原理都差不多。  
> 模板引擎的基本机理就是替换（转换）.

#### 你知道v-model的原理吗？
> v-model只是一个语法糖，真正实现靠的是 v-bind:绑定响应式数据，出发input事件并传递数据（核心和重点）。  
> `<input :value="msg" @input="msg =$event.target.value">`

#### 如何给vue定义全局方法
> + 通过prototype、通过插件Vue.use(plugin)、通过mixin，Vue.mixin(minxins);



