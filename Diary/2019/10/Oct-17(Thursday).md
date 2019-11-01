## **Daily Sentence**
#### <u>*【主线程】*</u>
> 是杭州一对离职夫妻档自己创业而进行开发的一款小程序，此小程序开发功能比较完善，可当作，一款产品看待。 
> 此小程序注册记录为2019年6月21日，开发者为阜阳市读路网络科技有限公司，公司注册日期约为19年6月12日，可以关注一下这个16届毕业生的创业路。

## **Plan**
> 这里记录我的一天，需要去留意的事。

> 每日3+1问题查看、思考、解答.(Night Goal)  
> 小程序云开发文档再过一遍--比较深入的API并未继续研究。  
> 


## **Summary**
|       标签       |               记录                | 评价 |
|:----------------:|:---------------------------------:|:----:|
| 小程序云开发文档 |     比较深入的API并未继续研究     |  ⭐⭐  |
|   每日3+1问题    | optgroup/tranlate/面向对象/potman |  ⭐⭐  |

## Record
##### 聚合
> 云开发聚合文档看的有点不透彻。
##### 索引
> 根据官网描述：我们应为所有需要成为查询条件的字段建立索引。
##### 小程序端API 
| 语法                                    | 说明                                                       |
|:----------------------------------------|:-----------------------------------------------------------|
| wx.cloud.init({})                       | //初始化                                                   |
| wx.cloud.callFunction({})               | 调用云函数                                                 |
| wx.cloud.uploadFile({})                 | 本地资源上传至云存储空间                                   |
| wx.cloud.downloadFile({})               | 从云存储空间下载文件                                       |
| wx.cloud.deleteFile({})                 | 从云存储空间删除文件                                       |
| const db = wx.cloud.database({})        | 获取默认数据库的引用                                       |
| collection                              |                                                            |
| db.collection("test")                   | 获取集合的引用                                             |
| db.collection("test").doc("id")         | 获取记录的引用                                             |
| db.collection("test").get()             | 获取集合数据|获取根据查询条件筛选后的集合数据              |
| db.collection("test").add({data:{}})    | 在集合上新增记录                                           |
| db.collection("test").watch({})         | 监听集合中符合查询条件的数据更新事件 ，只要where语句会生效 |
| db.collection("test")...count()         | 统计集合记录数，一个用户仅能统计其有读权限的记录数         |
| db.collection("test").where({})         | 指定筛选条件                                               |
| db.collection("test").orderby('','')    | 指定查询排序条件                                           |
| db.collection("test").limit()           | 指定查询结果集数量上限                                     |
| db.collection("test").skip()            | 指定查询返回结果时从指定序列后的结果开始返回，常用于分页   |
| db.collection("test").filed({})         | 指定返回结果中记录需返回的字段                             |
| doc                                     |                                                            |
| db.collection("test").get()             | 获取记录数据，或获取根据查询条件筛选后的记录数据           |
| db.collection("test").update({data:{}}) | 更新一条记录                                               |
| db.collection("test").set({data:{}})    | 替换更新一条记录                                           |
| db.collection("test").remove()          | 删除一条记录                                               |
| db.command                              | 获取数据库查询及更新指令                                   |
| 后期略                                  |                                                            |
##### 服务端API
> 在 wx-server-sdk 中不再兼容 success、fail、complete 回调，总是只会返回 Promise。
```
const cloud = require('wx-server-sdk')
cloud.init({
  env: cloud.DYNAMIC_CURRENT_ENV
})

exports.main = async (event) => {
  const { ENV, OPENID, APPID } = cloud.getWXContext()

  // 如果云函数所在环境为 abc，则下面的调用就会请求到 abc 环境的数据库
  const dbResult = await cloud.database().collection('test').get()

  return {
    dbResult,
    ENV,
    OPENID,
    APPID,
  }
}
```
| 语法         | 说明                                             |
|:-------------|:-------------------------------------------------|
| getWXContext | 在云函数中获取微信调用上下文，该方法无需传入参数 |

