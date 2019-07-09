## **Daily Sentence**
#### <u>*There are no secrets to success,It is the result of preparation,hard work and learning from failure*</u>
> 成功没有秘诀。它源自充分的准备，努力的工作，来自从失败中吸取教训。

## **Record**

> | 今日计划  | 完成过程说明 | 星级评价 |
> | :-----   |  :----- | ------   |
> | 代码备份（账单模式第一个icon） | 经评估，需要接口修改，前端再修改 | ⭐⭐ |
> | 小程序云开发简单学习 | 对照例子写了几个demo | ⭐⭐⭐ |

## Sumary

> 今天来做点笔记，学学这个云开发，这么长时间了，必须记忆点什么：

#####   1.初始化的app.js中有如下代码：

		wx.cloud.init({
	
	 	  traceUser: true,
	
		 })

> 用户管理中会显示使用云能力的小程序的访问用户列表,这里代码就是在控制台查看谁访问了小程序的
>
##### 2.上手数据库
######  1️⃣ 权限控制：数据库的权限分为`小程序端`和`管理端`
######  2️⃣ 约定：
> 在小程序中创建的每个数据库记录都会带有该记录创建者（即小程序用户）的信息，以 
> _openid 字段保存用户的 openid 在每个相应用户创建的记录中.

######  3️⃣ 数据库初始化：使用小程序API进行增删改查之前，需要先获取数据库的引用：

		`const db = wx.cloud.database()`

 		`const db = wx.cloud.database({
 		
 		 env:"test"
 		 
  	 })`
 ######  4️⃣ 操作集合：获取数据库后，接着要先获取它的引用，便可操作集合

		`const coll = db.collection("fileid")`
######  5️⃣ 插入数据
> 可以通过在集合对象上调用add方法在集合中插入一条记录。

		`coll.add({data:{},success:function(res){}})`
	
		`coll.add({data:{}).then(res => {})`
 ######  6️⃣ 查询数据
> 获取一个记录的数据：

		`coll.doc('f1006ad85d24588c03f8074313101639').get({success: function(res){}})`

> 获取多个记录的数据：

		`coll.where({_openid:"12dasadsdverwqsdded"}).get(success: function(res){})`
>
> 获取一个集合的数据：
> 约定：小程序端不能超过 20 条，云函数端不能超过 100 条，
> 可以在集合上调用 get 方法获取

######  7️⃣ 指令
> 数据库API提供了大于、小于等多种查询指令，这些指令都暴露在`db.commond`对象上
> |查询命令|说明|
> |-----|-----|
> |eq|等于|
> |neq|不等于|
> |lt|小于|
> |lte|小于等于|
> |gt|大于|
> |gte|大于等于|
> |in|字段值在给定数值中|
> |nin|字段值不在给定数组中|
> |逻辑指令|说明|
> |and|同时满足多个条件|
> |or|方法用于指定一个“或”条件|

> ##  **Daily Picture**

> Oh，今天也没有照片，为什么照片不是生活的一部分了，why？It‘s  It's so sad！

