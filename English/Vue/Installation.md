> 本章[来源](https://vuejs.org/v2/guide/installation.html)  

## Installation(安装) 
### Compatibility Note(对兼容性的注释) 
> Vue does not support IE8 and below,because it uses ECMAScript5 features that are un-shimmable in IE8.However it supports all ECMAScript 5 compliant browers.  

> [Vue 不支持 IE8 及以下版本，因为 Vue 使用了 IE8 无法模拟的 ECMAScript 5 特性。但它支持所有兼容 ECMAScript 5 的浏览器。]

### Releases Notes(更新日志) 
> Latest stable version:2.6.10.
> Detailed release notes for each version are available on Github. 

> 最新稳定版本：2.6.10  
> 每个版本的更新日志见 GitHub。

## Vue Devtools
> When using vue,we recommend also installing the Vue Devtools in your broswer,allowing you to inspect and debug your Vue applications in a more user-friendly interface.   

> 在使用 Vue 时，我们推荐在你的浏览器上安装 Vue Devtools。它允许你在一个更友好的界面中审查和调试 Vue 应用。 

## Direct `<script>` Include
> Simply download and include with a script tag. Vue wiil be registered as a global variable.   
> Don't use the minified version during development.You will miss out on all the nice warnings for common mistakes. 

> 直接下载并用 script 标签引入，Vue 会被注册为一个全局变量。    
> 在开发环境下不要使用压缩版本，不然你就失去了所有常见错误相关的警告!

### CDN
> For prototyping or learning purposes,you can use the latest version with: 

```
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```
> For production,we recommend linking to a specific version number and build to avoid unexpected breakage from newer versions:  
```
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.0"></script>
```
> If you are using native ES Modules,there is also an ES Modules compatible build:   
```
<script type="module">
  import Vue from 'https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.esm.browser.js'
</script>
``` 
> You can browes the source of the NPM package at cdn.jsdelivr.net/npm/vue. 
> Vue is also available on unpkg and cdnjs(cdnjs takes some time to sync so the latest release may not be available yet).   
> Make sure to read about the different builds of vue and use the production version  in your published site,replacing vue.js with vue.min.js. This is a smaller build optimized for speed instead of development experience。   


> 对于制作原型或学习，你可以这样使用最新版本：  
> 对于生产环境，我们推荐链接到一个明确的版本号和构建文件，以避免新版本造成的不可预期的破坏：    
> 如果你使用原生 ES Modules，这里也有一个兼容 ES Module 的构建文件：    
> 你可以在 cdn.jsdelivr.net/npm/vue 浏览 NPM 包的源代码.    
> Vue 也可以在 unpkg 和 cdnjs 上获取 (cdnjs 的版本更新可能略滞后)。     
> 请确认了解不同构建版本并在你发布的站点中使用生产环境版本，把 vue.js 换成 vue.min.js。这是一个更小的构建，可以带来比开发环境下更快的速度体验。

### NPM
> NPM is the recommended installation method when building large scale applications with Vue.It pairs nicely with module bundlers such as Webpack or Browerify.Vue also provides accompanying tools for authoring Single File Components.   
```
# latest stable
$ npm install vue
``` 

> 在用 Vue 构建大型应用时推荐使用 NPM 安装。NPM 能很好地和诸如 webpack 或 Browserify 模块打包器配合使用。同时 Vue 也提供配套工具来开发单文件组件。

### CLI
> Vue provides an official CLI for quickly scaffolding ambitious Single Page Applications. It provides batteries-included build setups for a modern frontend workflow. It takes only a few minutes to get up and running with hot-reload,lint-on-save,and production-ready builds.See the Vue CLI docs for more details.    
> The CLI assumes prior knowledge of Node.js and the associated build tools. If you are new to Vue or front-end build tools,we strongly suggest going through the guide without any build tools before using the CLI. 

> Vue 提供了一个官方的 CLI，为单页面应用 (SPA) 快速搭建繁杂的脚手架。它为现代前端工作流提供了 batteries-included 的构建设置。只需要几分钟的时间就可以运行起来并带有热重载、保存时 lint 校验，以及生产环境可用的构建版本。更多详情可查阅 Vue CLI 的文档。    
> CLI 工具假定用户对 Node.js 和相关构建工具有一定程度的了解。如果你是新手，我们强烈建议先在不用构建工具的情况下通读指南，在熟悉 Vue 本身之后再使用 CLI。

### Explanation if Different Builds
> In the dist/ directory of the NPM package you will find many different buidls of Vue.js,Here is an overview of the different between them:   

|            -             |        UMD         |       CommonJS        | ES Module(for bundles) | ES Module(for browsers) |
|:------------------------:|:------------------:|:---------------------:|:----------------------:|:-----------------------:|
|           Full           |       Vue.js       |     vue.common.js     |       vue.esm.js       |   vue.esm.browser.js    |
|       Runtime-only       |   vue.runtime.js   | vue.runtime.common.js |   vue.runtime.esm.js   |            -            |
|     Full(production)     |     vue.min.js     |           -           |           -            | vue.esm.browser.min.js  |
| Runtime-only(production) | vue.runtime.min.js |           -           |           -            |            -            |

> 在 NPM 包的 dist/ 目录你将会找到很多不同的 Vue.js 构建版本。这里列出了它们之间的差别：    

|            -             |        UMD         |       CommonJS        | ES Module (基于构建工具使用) | ES Module (直接用于浏览器) |
|:------------------------:|:------------------:|:---------------------:|:----------------------------:|:--------------------------:|
|          完整版          |       Vue.js       |     vue.common.js     |          vue.esm.js          |     vue.esm.browser.js     |
|      只包含运行时版      |   vue.runtime.js   | vue.runtime.common.js |      vue.runtime.esm.js      |             -              |
|    完整版 (生产环境)     |     vue.min.js     |           -           |              -               |   vue.esm.browser.min.js   |
| Runtime-only(production) | vue.runtime.min.js |           -           |              -               |             -              |

### Terms
> + Full: builds that contain both the compiler and the runtime.    
> + Compiler: code that is responsible for compiling template strings into JavaScript render functions. 
> + Runtime: code that is responsible for creating Vue instances,rendering and patching virtual DOM,etc,Basically everything minus the compiler.    
> + UMD: UMD builds can be used directly in the browser via a script tag .The default file from jsDelivr CDN at https://cdnjs.jsdelivr.net/npm/vue is the Runtime + Compiler UMD build vue.js). 
> + CommonJS: CommonJS build are intended for use with older bunlders like browserify and webpack1. The default file for there bundlers (pkg.min) is the Runtime only CommonJS build (vue.runtime.common.js)。  
> + ES Module:staring in 2.6 Vue provides two ES Module (ESM) builds: 
> 1. ESM for bundlers: intended for use with modern bundlers like webpack2 and Rollup. ESM format is designed to be statically analyzable so the bundlers can take advantage of that to perform "tree-shaking" and eliminate unused code from your final bundle.The default file for these bundles(pkg.module) is the Runtime only ES Module build(vue.runtime.esm.js). 
> 2. ESM for browsers (2.6+only)"intended for direct imports in modern browsers via `<script type="module">`. 

> + 完整版：同时包含编译器和运行时的版本。  
> + 编译器：用来将模板字符串编译成为 JavaScript 渲染函数的代码。  
> + 运行时：用来创建 Vue 实例、渲染并处理虚拟 DOM 等的代码。基本上就是除去编译器的其它一切. 
> + UMD：UMD 版本可以通过 `<script>` 标签直接用在浏览器中。jsDelivr CDN 的 https://cdn.jsdelivr.net/npm/vue 默认文件就是运行时 + 编译器的 UMD 版本 (vue.js)。   
 > + CommonJS：CommonJS 版本用来配合老的打包工具比如 Browserify 或 webpack 1。这些打包工具的默认文件 (pkg.main) 是只包含运行时的 CommonJS 版本 (vue.runtime.common.js)。    
 > + ES Module：从 2.6 开始 Vue 会提供两个 ES Modules (ESM) 构建文件：  
 > 1. 为打包工具提供的 ESM：为诸如 webpack 2 或 Rollup 提供的现代打包工具。ESM 格式被设计为可以被静态分析，所以打包工具可以利用这一点来进行“tree-shaking”并将用不到的代码排除出最终的包。为这些打包工具提供的默认文件 (pkg.module) 是只有运行时的 ES Module 构建 (vue.runtime.esm.js).  
 > 2. 为浏览器提供的 ESM (2.6+)：用于在现代浏览器中通过 <script type="module"> 直接导入。

 ### Runtime + Compiler VS Runtime-only
 > If you need to compile templates on the client(e.g. passing a string to the template option. or mounting to an element using its in-DOM HTML as the template),you will need the compiler and thus the build:  
 > ```
 // this requires the compiler
new Vue({
  template: '<div>{{ hi }}</div>'
})

// this does not
new Vue({
  render (h) {
    return h('div', this.hi)
  }
})
>```

 ### 运行时 + 编译器 vs. 只包含运行时
 > 如果你需要在客户端编译模板 (比如传入一个字符串给 template 选项，或挂载到一个元素上并以其 DOM 内部的 HTML 作为模板)，就将需要加上编译器，即完整版：