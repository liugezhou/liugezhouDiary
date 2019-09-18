## **Daily Sentence**
#### <u>*Any application that can be written in JavaScript will eventually be written in JavaScript. *</u>
> 

## **Plan**
>这里记录我的一天，需要去留意的事。

> ES5基础语法回顾、背景、影响、语法、概念等的查漏补缺。
## **Summary**
#### 脚本语言
> JavaScript 是一种轻量级的脚本语言:指的是不具备开发操作系统的能力，而是只用来编写控制其他大型应用程序（比如浏览器）的“脚本”.

#### JavaScript的核心语法
> 只包括两个部分：基本的语法结构（比如操作符、控制结构、语句）和标准库（具有各种功能的对象如Array、Date、Math等）。

#### 标识符
> 标识符命名规则： 
> 第一个字符可以是任意Unicode字母（包括英文字母和其它语言字母），以及美元符号`$`和下划线`_`。
> 第二个字符以及后面字符，除了第一条提到的，还可以用数字0-9。
> 另：中文所合法的标识符，可以用作变量名。【关键字不能用作标识符】

#### JavaScript有三种方法，可以确定一个值到底是什么类型
> + typeof : 可以识别 Number、String、Boolean、Object({}、[]、null)、undefined
> + instance : 可以区分数组和对象
> + Object.prototype.toString.call([]) // "[object Array]"

#### Null和undefined的区别
> null是一个表示“空”的对象，转为数值时为0；undefined表示“此处无定义”的原始值，转为数值时为NaN。


