## **Daily Sentence**
#### <u>* Let's take a look at Vue's official English documentation today. *</u>

## Summary
### Installation
#### Compatibility Note
> Vue does not support IE8 and below,because it uses ECMAScript 5 features that are un-shimmable in IE8.However it supports all ECMAScript 5 compliant browsers.    
#### Release Notes
> Latest stable version:2.6.10. 
> Detailed release motes for each version are available on Github.  
### Vue Devtools
> When using Vue,we recommend also installing the Vue Devtools in your browser,allowing you to inspect and debug your Vue aplications in a more user-friendly interface.    
### Direct `<script>` Include   
> Simply download and include with a script tag.Vue will be registeres as a global varible. 
> Don't use the minified version during development.You will miss out on all the nice warnings for common mistakes. 
### CDN
> For prototyping or learning purposes,you can use the latest version with:XXX  
> For prodution, we recommend linking to a specific version number and build to avoid unexpected breakage from newer versions.  
> If you are using native ES Modules,ther is also an ES Modules compatible build.   
> You can browse the source of the NPM package at cdn.ksdelivr.net/npm/vue.
> Vue is aslo available on unpkg and cdnjs. 
> Make sure to read the different builds of Vue and use the production. 
> version in your published site,replacing vue.js with vue.min.js.This is a smaller build optimized for speed instead of development experience.
### NPM
> NPM is the recommended installation method when building large scale applications with Vue.It pairs nicely with module bundlers such as Webpack or Browserify.Vue also provides accompanying tools for authoring Single File Components.
### CLI
> Vue provides an offcial CLI for quickly scaffolding ambitious Single Page Applications.It provides batteries-included build setups for a modern frontend workflow.It takes only a few minutes to get up and running with hot-reload,lint-on-save,and production-ready builds.See the Vue CLI docs for more details.   
### Runtime + Compiler vs Runtime-only
> If you need to compile templates on the client(eg passing a string to the template option,or mounting to an element using its in-DOM HTML as the template).you will need the compiler and thus the full build.    
> When using vue-loader or vueify,template inside *.vue files are pre-compiled into JavaScript at build time.You don't really need the compiler in the final bundle,and can therefore use the runtime-only build.