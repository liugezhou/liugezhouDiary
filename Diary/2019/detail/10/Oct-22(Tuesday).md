## **Daily Sentence**
#### <u>*There's no place like home*</u>
> 没有一个地方可以和家相提并论。(《绿野仙踪》1939)

## **Plan**
> 这里记录我的一天，需要去留意的事。

> 小程序服务端接口调用流程梳理。

## **Summary**
|      标签       | 记录 | 评价 |
|:---------------:|:----:|:----:|
| running morning | 4km  | ⭐⭐⭐  |


## Record
#### 登录
> 登录凭证校验。通过 wx.login 接口获得临时登录凭证 code 后传到开发者服务器调用此接口完成登录流程。  
> `GET https://api.weixin.qq.com/sns/jscode2session?appid=APPID&secret=SECRET&js_code=JSCODE&grant_type=authorization_code`   
> 返回：openid、session_key、在满足 UnionID 下发条件的情况下会返回unionid。

#### access_token
> 获取小程序全局唯一后台接口调用凭据（access_token）。调调用绝大多数后台接口时都需使用 access_token，开发者需要进行妥善保存。   
> `GET https://api.weixin.qq.com/cgi-bin/token?grant_type=client_credential&appid=APPID&secret=APPSECRET`.  
> 注意：
> + access_token 的存储至少要保留 512 个字符空间.   
> + access_token 的有效期目前为 2 个小时，需定时刷新，重复获取将导致上次获取的 access_token 失效；  
> + 这个字段值要手动保存、定时刷新、全局引用。  

#### templateMessage.send
> 组合模板并添加至帐号下的个人模板库（请注意，小程序模板消息接口将于2020年1月10日下线，开发者可使用订阅消息功能）.  
> so，这个不看了。

#### [订阅消息](https://developers.weixin.qq.com/miniprogram/dev/framework/open-ability/subscribe-message.html)
> 流程一二三。  
> subscribeMessage.send:发送订阅消息。  
> `POST https://api.weixin.qq.com/cgi-bin/message/subscribe/send?access_token=ACCESS_TOKEN` 
> 所需参数：接收者（用户）的 openid、所需下发的订阅模板id。 

#### 微信支付
> + 微信支付要求商户订单号保持唯一性（建议根据当前系统时间加随机序列来生成订单号）. 
> + 重新发起一笔支付要使用原订单号，避免重复支付；已支付过或已调用关单、撤销（请见后文的API列表）的订单号不能重新发起支付。 
> + key为商户平台设置的密钥key:key设置路径：微信商户平台(pay.weixin.qq.com)-->账户设置-->API安全-->密钥设置.    


