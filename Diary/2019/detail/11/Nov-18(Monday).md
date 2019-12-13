## **Daily Sentence**
---
#### <u>* Today we'll learn some official vuex documentation .*</u>

## What is Vuex?
---
> Vuex is a state management pattern + library for Vue.js applications. 
> Vuex是用于Vue.js应用的状态管理模式+库。

> It serves as a centralized store for all the components in an application,with rules ensuring that the state can only be mutated in a predictable fashion.    
> 它充当应用程序中所有组件的集中式存储，它的规则确保状态只能以可预测的方式进行突变。

> It also intergrates with Vue's official devtools extension to provide advanced features such as zero-config time-travel debugging and snapshot expore/import. 
> 它还集成了Vue的官方DevTools扩展，以提供诸如零配置、时间旅行、调试和快照Exest/import等高级功能。
## What is a "State Management Pattern"
---
> Let's start with a simple Vue counter app:
```
new Vue({
    //state
    data(){
        return {
            count:0
        }
    },
    //view
    template :`
    <div>{{count}}</div>
    `,
    //actions
    methods:{
        increment () {
            this.count ++
        }
    }
})
```
> It is a self-contained app with the following parts:
> 这是一个自成体系的应用程序，有以下几个部分

> + The state,the source of truth that drives our app;
> + State，是驱动我们应用程序的真理之源；

> + The view,a declarative mapping of the state.    
> + View,状态的声明映射.    

> + The actions,the possible ways the state could change in reaction to user inputs from the view.  
> + Actions,状态对视图中的用户输入作出反应的可能方式。

## When Should I Use It?
---
> Vuex helps us deal with shared state management with the cost of more concepts and boilerplate.   
> Vuex帮助我们用更多的概念和样板来处理共享状态管理。

> It's a trade-off between short term and long term productivity.   
> 这是短期和长期生产力之间的权衡。