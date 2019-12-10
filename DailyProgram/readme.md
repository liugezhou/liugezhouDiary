## Introduce
> Dec 10，2019. 
> 这天下班前，突然被问到一个关于JS的问题，此问题因之前见到过，蒙对了答案，但是其中的缘由并不知情。    
> 想到面试题漫漫，知识的海洋那么大，翻来覆去重要的也就那么点，遇到一个不知其中缘由的问题，一定要记录下来，顶礼膜拜。    
> 这里记录我从开始顶礼膜拜到不屑一顾的题、概念或者小知识。  

## Content

###### 1. parseInt;

```
'use strict';

var arr = ['1','2','3'];
var r;
r = arr.map(parseInt);

console.log(r);
```


<details><summary><b>Answer</b></summary>
<p>

#### Answer: [1,NaN,NaN]
> 具体解题思路：
>
> 我们先来看map的定义和用法： 
> map()方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。   
> map()方法按照原始数组元素顺序依次处理元素。
> 两点需要注意：map()不会对空数组进行检测、map()不会改变原始数组。
> 语法：array.map(function(currentValue[, index[, array]]),thisValue)
>
> 接着，我们来看parseInt函数。  
> parseInt的定义是用于解析一个字符串，并返回一个整数:   
> parseInt(string,radix),其中radix可选（可填写值介于2～36，若省略该参数或者值为0，则数字将以10进制来解析，若小于2或者大于36，返回NaN）。    
>
> 然后查看上述代码 arr.map(parseInt),我们知道这里表示的是： 
> ```
> arr.map(function(currentValue,index,arr){
>    parseInt(currentValue,index.arr)
> })
> ```
> parseInt需要两个参数，会将arr参数忽略掉，因此，最终的处理过程是： 
> parseInt("1",0)、parseInt("2",1)、parseInt("3",2).    
> 根据上面我们的分析第一个正确，第二个由于radix是1，小于2，返回NaN，第三个由于“3”它不是一个合格的二进制，因此同样返回NaN。
>
> 最后我们给出解决方案：
> ```
> 'use strict';
> 
> var arr = ['1', '2', '3'];
> var r;
> r = arr.map(function parseInt2(x) {
>     return parseInt(x);
> });
> console.log(r);
> ```
> 或者：    
> ```
> 'use strict';
> 
> var arr = ['1', '2', '3'];
> var r;
> r = arr.map(Number);
> console.log(r);
> ```
> 以上就是本道题的心路历程。
</p>
</details>