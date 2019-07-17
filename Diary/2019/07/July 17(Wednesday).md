## **Daily Sentence**
#### <u>**</u>
> 

## **Plan**
|                  标签                  | 记录  | 评价  |
| :------------------------------------: | :---: | :---: |
|  echarts事件点击、新提出需要修改的bug  |       |  ⭐⭐⭐   |
| iconfont在小程序中的使用、去掉冗余代码 |       |       |
|                                        |       |       |

## **Record**
> 今天关于echarts饼图在手机端点击图例事件显示在环形饼图中间的需求，终于得到解决，在同事的帮助下，将源码的`legendSelectActionHandler`方法注掉，且修改了` itemGroup.on('click', curry$2(dispatchHighlightAction, null, name, api, excludeSeriesId))`,便实现了点击的显示效果，不过后来又出现地图的渐变颜色消失的bug，原来是因为我在定制echarts插件的时候丢掉了visualMap而导致。通过这次小小的需求修改，源码的理解肯定还是很浅，但是对于echarts定制使用这块算是有了点点的心得。

> iconfont的使用相对来说比较简单，此刻准备晚上花些时间写写关于iconfont的使用，为了达到下次再次使用时，如鱼得水、信手拈来。

