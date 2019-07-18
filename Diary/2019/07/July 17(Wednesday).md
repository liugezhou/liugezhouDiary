## **Daily Sentence**
#### <u>*It's never too late to be who you wanna be,to say what you wanna say*</u>
> 你想成为什么样的人，你想说什么话，从来都不算是迟。

## **Plan**
|                  标签                  | 记录  | 评价  |
| :------------------------------------: | :---: | :---: |
|  echarts事件点击、新提出需要修改的bug  |主要是echarts插件的定制使用|  ⭐⭐⭐   |
| iconfont在小程序中的使用、去掉冗余代码 | 夜深人静、简单技能博客一篇 |  ⭐⭐⭐ |

## **Record**
> 今天关于echarts饼图在手机端点击图例事件显示在环形饼图中间的需求，终于得到解决，在同事的帮助下，将源码的`legendSelectActionHandler`方法注掉，且修改了` itemGroup.on('click', curry$2(dispatchHighlightAction, null, name, api, excludeSeriesId))`,便实现了点击的显示效果，不过后来又出现地图的渐变颜色消失的bug，原来是因为我在定制echarts插件的时候丢掉了visualMap而导致。通过这次小小的需求修改，源码的理解肯定还是很浅，但是对于echarts定制使用这块算是有了点点的心得。

> iconfont的使用相对来说比较简单，为了达到下次再次使用时，如鱼得水、信手拈来。
> 夜深人静的时候，写了一篇小小的简单文章：[iconfont在小程序端的使用](https://www.liugezhou.online/2019/07/17/icofont/)

> 关于我要写的小程序还是没有一个很好的需求、设计、开发，在思量中。

