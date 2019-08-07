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

