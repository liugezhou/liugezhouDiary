# dangerousSumary
> 人生一世，草木一秋！

# Content
#### Nov 27,2019
+ [9. vconsole](https://github.com/Tencent/vConsole/blob/dev/doc/tutorial_CN.md)
#### Nov 14,2019
+ [8. TypeScript入门教程](https://ts.xcatliu.com/)
#### Nov 13,2019
+ [7. 使用VS Code时你应该熟记的一些操作](https://juejin.im/post/5cb87c6e6fb9a068a03af93a)
#### Nov 4,2019
+ [6.即使是如今的多进程架构，我偶尔还会碰到一些由于单个页面卡死最终崩溃导致所有页面崩溃的情况，请问这是什么原因呢]
> ##### 即使是如今的多进程架构，我偶尔还会碰到一些由于单个页面卡死最终崩溃导致所有页面崩溃的情况，请问这是什么原因呢
> 是这样的，通常情况下是一个页面使用一个进程，但是，有一种情况，叫"同一站点(same-site)"，具体地讲，我们将“同一站点”定义为根域名（例如，geekbang.org）加上协议（例如，https:// 或者http://），还包含了该根域名下的所有子域名和不同的端口，比如下面这三个：
```
https://time.geekbang.org
https://www.geekbang.org
https://www.geekbang.org:8080
```
> 都是属于同一站点，因为它们的协议都是https，而根域名也都是geekbang.org。你也许了解同源策略，但是同一站点和同源策略还是存在一些不同地方，在这里你需要了解它们不是同一件事就行了。
> Chrome的默认策略是，每个标签对应一个渲染进程。但是如果从一个页面打开了新页面，而新页面和当前页面属于同一站点时，那么新页面会复用父页面的渲染进程。官方把这个默认策略叫process-per-site-instance。
> 直白的讲，就是如果几个页面符合同一站点，那么他们将被分配到一个渲染进程里面去。
> 所以，这种情况下，一个页面崩溃了，会导致同一站点的页面同时崩溃，因为他们使用了同一个渲染进程。
> 为什么要让他们跑在一个进程里面呢？
> 因为在一个渲染进程里面，他们就会共享JS的执行环境，也就是说A页面可以直接在B页面中执行脚本。因为是同一家的站点，所以是有这个需求的。

#### Oct 14,2019
+ [5. 当然我在扯淡](http://www.yinwang.org/)
#### Oct 13,2019
+ [4. 前端面试每日3+1](https://github.com/haizlin/fe-interview)
#### Oct 08,2019
+ [3. GitHub Wiki 页面的添加和设置](https://juejin.im/post/5a3216c8f265da43333e6b54)
#### Oct 05,2019
+ [2. 前端入门和进阶学习笔记，超详细的Web前端学习图文教程。从零开始学前端，做一个Web全栈工程师。持续更新...](https://github.com/qianguyihao/Web)
#### Oct 01,2019
+ [1. iPhone 为什么不加大内存？](https://www.zhihu.com/question/276578129/answer/829637068)

