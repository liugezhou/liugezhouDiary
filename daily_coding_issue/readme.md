## Introduce
> 一天下班前，突然被问到一个关于JS的问题，此问题因之前见到过，蒙对了答案，但是其中的缘由并不知情。    
> 想到面试题漫漫，知识的海洋那么大，看过的文章又是不计其数，翻来覆去重要的也就那么点点，遇到一个不知其中缘由的问题倘若看看就过，下次依然丈二和尚摸不着头脑。  
> 所以对一些基础一定要记录下来，顶礼膜拜。    
> 这里记录我从开始顶礼膜拜到不屑一顾的题、概念或者小知识。  

## Content
###### 1.[LeetCode]--给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。
> 示例:
>
> 给定 nums = [2, 7, 11, 15], target = 9    
> 因为 nums[0] + nums[1] = 2 + 7 = 9    
> 所以返回 [0, 1]   
<details><summary><b>Answer</b></summary>
<p>

#### Answer:直接给出写法
```
const nums=[2,7,11,15],target=9;
let twoSum = function(nums, target) {
    let len = nums.length;
    for(let i=0;i<len;i++){
        for(let j=i;j<len;j++){
            if(nums[i]+nums[j] == target){
                return [i,j]
            }
        }
    }
};
console.log(twoSum(nums,target))
```
> 第二种使用map的解法：
```
const nums=[2,7,11,15],target=9;
var twoSum = function(nums, target) {
    const map = new Map();
    let len = nums.length;
    for(let i=0;i<len;i++){
        const otherIndex = map.get(target - nums[i]);
        if(otherIndex!== undefined) return [otherIndex,i];
        map.set(nums[i],i)
    }
}
console.log(twoSum(nums,target))
```
</p>
</details>

###### 2. parseInt ｜ 以下代码会输出什么？

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
> parseInt(string,radix),其中radix可选      
> （radix可填写值介于2～36，若省略该参数或者值为0，则数字将以10进制来解析，若小于2或者大于36，返回NaN）。    
>
> 然后查看上述代码 arr.map(parseInt),我们知道这里表示的是： 
> ```
> arr.map(function(currentValue,index,arr){
>    parseInt(currentValue,index.arr)
> })
> ```
> parseInt需要两个参数，会将arr参数忽略掉，因此，最终的处理过程是：           
> parseInt("1",0)、parseInt("2",1)、parseInt("3",2).     
> 根据上面我们的分析第一个正确，第二个由于radix是1--小于2，返回NaN，第三个由于“3”它不是一个合格的二进制，因此同样返回NaN。
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