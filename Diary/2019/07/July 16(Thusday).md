## **Daily Sentence**
#### <u>*Living without an aim is like sailing without a compass.*</u>
> 生活没有目标，犹如航海没有罗盘

## **Plan**
|       标签       | 记录  | 评价  |
| :--------------: | :---: | :---: |
|     日常bug      | resolve it|  ⭐⭐   |
| 小程序云开发文档 |       |       |
|                  |       |       |

## **小程序云开发文档嘚啵嘚**
##### 存储
> 该服务高可用、高稳定、强安全。
###### 上传文件：

     wx.cloud.uploadFile({
      cloudPath:'example.png',
      filePath:' ',//小程序临时文件路径
     success: res => {},
     fail:console.error
     })

###### 下载文件：

    wx.cloud.downloadFile({
     fileID: '', // 文件 ID
     success: res => {
      // 返回临时文件路径
      console.log(res.tempFilePath)
     },
     fail: console.error
    })

###### 删除文件：

    wx.cloud.deleteFile({
      fileList: ['a7xzcb'],
      success: res => {
      // handle success
       console.log(res.fileList)
     },
     fail: console.error
    })

##### 云函数
 - 第一个云函数
> 1. project.config.json 文件，新增 cloudfunctionRoot 字段，指定本地已存在的目录作为云函数的本地根目录。
> 2. 云函数根目录上右键，在右键菜单中，可以选择创建一个新的 Node.js 云函数,并命名该云函数名字。
> 3. event为传入的参数，编写云函数代码，并右键将该云函数部署到云端
> 4. 在业务代码中调用该云函数

 - 获取小程序用户信息
> 云函数使得小程序端可获取天然可信任的用户登录态（openid）：
> 开发者可以直接在云函数内使用wx-server-sdk提供的getWXContext方法获取到每次调用的上下文（appid、openid等）

 - 异步返回结果
> 这里好像先需要npm install 一下然后才能代码才会执行。
> 函数部分主要的代码为；
> 
    exports main = async (event,context) => {
        return new Promise((resolve,reject)=>{
            setTimeout(()=>{
                resolve(event.a + event.b)
            },2000)
        })
    }

 - 云函数中调用数据库
>假设数据中有`test`集合，我们可以通过如下方式获得`test`集合的数据

    const cloud = require('wx-server-sdk')
    cloud.init()
    const db = cloud.database()
    exports main = async (event,context) => {
        return db.collection('test').get()
    }

 - 定时触发器
> 略
 - 运行机制
> 略
- 注意事项
> 略
- 管理云函数
> 略
- 云调用
>略


