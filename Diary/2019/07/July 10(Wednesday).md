## **Daily Sentence**
#### <u>*Limitations live only in our minds. But if we use our imaginations, our possibilities become limitless.*</u>
> 局限只存在于我们的大脑中。可是如果我们运用自己的想象力，就会获得无限的可能性。

## **Record**

> | 今日计划  | 完成过程说明 | 星级评价 |
> | :-----   |  :----- | ------   |
> | 账单模式数据、病种显示等bug | 对接口数据反复试错、弄清字段含义 | ⭐⭐⭐⭐⭐ |
> | 小程序云开发继续简单学习、写demo |        写了一点点                          |⭐⭐  |
> | 关于Github-Licence的科普文 |        改bug没时间                         |  |
> | 关于一个项目提到多端的配置 |                   改bug没时间               |  |

## Sumary

> First of all,再学习一段关于小程序云开发的API。
###### 更新数据
> 更新数据主要有两种方法：`update`和`set`
> 局部更新：`update`：

        test.doc("xcwqcwqcwq").update({
            data:{
                done:true
            },
            success:function(res){
                console.log(res.data)
            }
        })
> 更新指令：更新指令通过db.commond取得：
> | 更新指令 | 说明 |
> |:--------:|:-----:|
> | set | 设置字段为指定值|
> | remove | 删除字段 |
> | inc |原子自增字段值|
> | mul |原字段乘字段值|
> | push | 如字段为数组，往数组尾部增加指定值|
> | pop | 如字段为数组，从数组尾部删除一个元素|
> | shift| 如字段为数组，从数组头部删除一个元素|
> | unshift| 如字段为数组，往数组头部增加指定值|

##  **Daily Picture**
![work](https://github.com/liugezhou/liugezhouImage/blob/master/Diary/2019/07/0710licence.jpg)
---
![work](https://github.com/liugezhou/liugezhouImage/blob/master/Diary/2019/07/0710PMP.png)

