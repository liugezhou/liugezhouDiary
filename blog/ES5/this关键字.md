<!--
 * @Description: this关键字你真的会了吗
 * @Author: 刘明周
 * @Date: 2020-03-20 22:21:47
 -->
### this关键字


#### 一、含义
> + this用在构造函数中，表示实例对象。  
> + this总是返回一个(属性或方法所在的)对象。  
> + JavaScript 支持运行环境动态切换，也就是说，this的指向是动态的，没有办法事先确定到底指向哪个对象，这才是最让初学者感到困惑的地方。 

#### 二、实质
> + JavaScript语言之所以有this的设计，跟内存里面的数据结构有关系。  
> + 由于函数可以在不同的运行环境执行，所以需要有一种机制，能够在函数体内部获得当前的运行环境。  
> + 因此，this出现，它的设计目的就是在函数体内部，指代函数当前的运行环境。  

#### 三、使用场合
> + 全局环境 ,this指向顶层对象window。  
> + 构造函数，this指向实例对象。   
> + 对象的方法，this指向方法运行时所在的对象。 

#### 四、使用注意点
> + 避免多层this。  
> + 避免数组处理方法中的this。  
> + 避免回调函数中的this。  

#### 五、绑定this的方法
> JavaScript提供了`call` `apply` `bind`这三个方法，来切花/固定this的指向。  

> Function.prototype.call():call方法的第一个参数就是this所要指向的那个对象，后面可以接收多个参数，后面的参数是函数调用时所需的参数。  

> Function.prototype.apply():与call的唯一区别为，它后面接收的参数是数组。 
> 应用一：找出数组最大的元素  
> ```
> var array = [1,56,23,8,90]
> Math.max.apply(null,array)
>```
> 应用二：将数组的空元素变为undefined:空元素与undefined的区别是，数组的forEach方法会跳过空元素，但不会跳过undefined。 
> ```
> var array = [1,,,,,90]
> Array.apply(null,array)
>```
> 应用三：转换数组类似的对象
> ```
> Array.prototype.slice.apply({0:1,length:1})
>```
> 应用四：绑定回调函数的对象

> Funtion.prototype.bind():bind方法用于将函数体内的this绑定到某个对象，然后返回一个新函数。 

