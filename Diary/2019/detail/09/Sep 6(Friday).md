## **Daily Sentence**
#### <u>*Life is like a play,play as in life,everyone has played diffrent roles.*</u>
> 人生如戏，戏如人生，每个人都在上演着不同的角色.

## **Plan**
> 每到周五的时候心情总是如此的平和。

> 如今在面对生活、面对工作中都好似处在一个瓶颈，跨越不了。
> 
> 价值观还未定型，工作还未干到满意。

> 我能做些什么呢？ 总得有点能拿出手的东西在必要的时候去展示一把吧。

> 那么，好好在前端的世界上找寻乐趣，发掘、钻研、盘它。

> 今天的学习时间用来再学Vue,我要在Vue的世界里驰骋。

## **Summary**
### 创建一个数组
> Array.of() : 返回由所有参数值组成的数组，不管参数值是什么！

    const a = 1
    const b = '2'
    const c = true
    const d = {name:'liugezhou'}
    const e = ['liu','ge','zhou']
    let arr = Array.of(a,b,c,d,e)

### 改变原数组的方法（7个）
> + push():末尾添加 ----- ⭐⭐⭐
> + pop()：末尾删除 ----- ⭐⭐⭐
> + shift()：首位删除 ----- ⭐⭐⭐
> + unshift()：首位添加 ----- ⭐⭐⭐
> + splice() ：从数组中添加/删除项目,语法 array.splice(index,howmany,item1,.....,itemX) ----- ⭐⭐⭐
> + sort()： 数组排序 ----- ⭐⭐⭐
> + reverse()： 数组反序 ----- ⭐⭐⭐

### 不改变原数组的方法（8个）
> + concat() ：方法用于合并两个或多个数组，返回一个新数组。 ----- ⭐⭐⭐
> + filter() ----- ⭐⭐⭐
> + slice() ：
>   浅拷贝数组的元素。
>   提取字符串的某个部分[start不包含此索引:1指第一个，-1指倒数第一个，end包含此索引:未指定直到结尾，若为负数则从末尾倒数] ----- ⭐⭐⭐
> + join(): 用于数组中的所有元素通过指定的分隔符进行分割到一个`字符串`中去。----- ⭐⭐⭐
> + toLocateString()
> + toString() ----- ⭐⭐⭐
> + indexOf() ----- ⭐⭐⭐
> + lastIndexOf()
> + includes()  ----- ⭐⭐⭐

### 遍历方法
> + forEach()
> + every()
> + some()
> + map()
> + reduce ()
> + reduceRight()
> + entries()