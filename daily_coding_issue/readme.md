## Introduce
> 一天下班前，突然被问到一个关于JS的问题，此问题因之前见到过，蒙对了答案，但是其中的缘由并不知情。    
> 想到面试题漫漫，知识的海洋那么大，看过的文章又是不计其数，翻来覆去重要的也就那么点点，遇到一个不知其中缘由的问题倘若看看就过，下次依然丈二和尚摸不着头脑。  
> 所以对一些基础一定要记录下来，顶礼膜拜。    
> 这里记录我从开始顶礼膜拜到不屑一顾的题、概念或者小知识。  

## Content
##### 8.

##### 7.获取DOM节点、attribute与property等有关DOM
<details>
<summary><b>Answer</b></summary>
<p>

###### 获取DOM节点
> const div1 = document.getElementById('div1')//元素
> const divList = document.getElementByTagName('div') //集合
> const containerList = document.getElementByClassName(".container')//  集合
> const pList = document.querySelectorAll('p') // 集合
###### property与attribute
> property：修改对象属性，不会体现到html结构中。    
> attribute:修改html属性，会改变html结构。
###### 新增/插入节点
```
 const div1 = document.getElemengtById('div1)
//添加新节点
const p1 = docuemnt.createElement('p')
p1.innerHTMl = 'this is p1'
div1.appendChild(p)
//移动已有节点。注意是移动
const p2 = document.getElementById('div2')
div1.appendChid(p2);
//获取父元素
p2.parentNodes
//获取自元素列表
p2.childNodes
```
###### 将频繁操作改为一次性操作
```
 const listNode = documentGetElementById('list')
 //创建一个文档片段，此时还没有插入到DOM树中
 const frag = docuement.creatDocumentFragement()
 //执行插入
 for(let i=0;i<10;i++){
     const li = docuement.createElement('li');
     li.innerHTML = 'List item ' + i;
     frag.appendChild(li)
 }
 listNode.appendChild(frag)
```
</p>
</details>

##### 6.手写一个Promise加载图片

<details><summary><b>Answer</b></summary>
<p>

```
 const url = "https://img.liugezhou.online/blog/wechatDangerous.png";

 function  loadImag(src) {
     return new Promise((resolve,reject)=>{
         const img = document.creatElement("img");
         img.onload = ()=>{
             resolve(img)
         }
         img.error = ()=> {
             const err = new Error(`图片加载失败${src}`)
             reject(err)
         }
     })
 }
 loadImg(url).then(img => {
     console.log(img.width)
     return img
 }).then(img=>{
     console.log(img.height)
 }).catch(err =>{
     conosle.log(err)
 })
```

</p>
</details>

##### 5.深拷贝
> 通过深拷贝，考察四个知识点：  
> + typeof用来判断值类型。  
> + instanceof用来判断一个对象是否为数组    
> + hasOwnProperty():原型、原型链   
> + 递归

<details><summary><b>Answer</b></summary>
<p>

```
const obj1 = {
    age:18,
    name:'xxx',
    address: {
        city:'beijing'
    },
    arr:['a','b','b']
}

const obj2 = deepClone(obj1);
obj1.arr[0] ='c';
obj2.address.city = 'shaghai';
function deepClone(obj={}){
    if(typeof obj !=='object' ||  obj == null) {
        return obj;
    }
    let result;
    if (obj instanceof Array){
        result = [];
    }else{
        result = {}
    }
    for (let key in obj) {
        if(obj.hasOwnProperty(key)){
            //递归
            result[key] = deepClone(obj[key]);
        }
    }
    return result;
}
```
</p>
</detail>

##### 4.给定一个字符串，请你找出其中不含有重复字符的 最长子串 的长度。

```
示例 1:

输入: "abcabcbb"
输出: 3 
解释: 因为无重复字符的最长子串是 "abc"，所以其长度为 3。
```
<details><summary><b>Answer</b></summary>
<p>

> Answer1:  

```
var str = "abcabcbb";
var lengthOfLongestSubstring = function(s) {
    var num=0,res=0;
    let m='';
    for(n of s ){
        if(Object.is(m.indexOf(n),-1)){
            m+=n;
            num++;
            res = res <num ? num : res;
        }else{
            m+=n;
            m = m.slice(m.indexOf(n)+1);
            num = m.length;
        }
    }
    return res;
};
console.log(lengthOfLongestSubstring(str));
```

> Answer2:  
```
var str = "abcabcbb";
var lengthOfLongestSubstring = function(s) {
    var num=0,res=0;
    let tempObject=[];
    for(var i=0;i<s.length;i++){
        if(Object.is(tempObject.indexOf(s[i]),-1)){
            tempObject.push(s[i]);
        }else{
             tempObject.shift();
             continue;
        }
        res = Math.max(res, tempObject.length);
        num++;
    }
    return res;
};
console.log(lengthOfLongestSubstring(str));

```

</p>
</details>

##### 3.LeetCode
> 给出两个 非空 的链表用来表示两个非负的整数。其中，它们各自的位数是按照 逆序 的方式存储的，并且它们的每个节点只能存储 一位 数字。   
> 如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。    
> 您可以假设除了数字 0 之外，这两个数都不会以 0 开头.  
> 示例：
>
> 输入：(2 -> 4 -> 3) + (5 -> 6 -> 4)
> 输出：7 -> 0 -> 8
> 原因：342 + 465 = 807
<details><summary><b>Answer</b></summary>
<p>

> 未看答案之前我是这么写的，执行到第三行报错(Chrome控制台可以正确打印)，猜测这里不让用join方法吧：  
```
const l1 = [2,4,3],l2=[5,6,4];
var addTwoNumbers = function(l1, l2) {
   var count1 = l1.join("");
   var count2 = l2.join("");
   let sum = parseInt(count1) + parseInt(count2)
    return sum.toString().split("").reverse();
};
addTwoNumbers(l1,l2);
```

</p>
</details>

##### 2.[LeetCode]
>  给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。
> 示例:
>
> 给定 nums = [2, 7, 11, 15], target = 9    
> 因为 nums[0] + nums[1] = 2 + 7 = 9    
> 所以返回 [0, 1]   
<details><summary><b>Answer</b></summary>
<p>

###### Answer:直接给出写法
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

##### 1. parseInt ｜ 以下代码会输出什么？

```
'use strict';

var arr = ['1','2','3'];
var r;
r = arr.map(parseInt);

console.log(r);
```


<details><summary><b>Answer</b></summary>
<p>

###### Answer: [1,NaN,NaN]
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