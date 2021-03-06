### No3.V8工作原理

###### 前段时间在《极客时间》上学了一个专栏，通篇略过，干货不少，但理解相当不够透彻，于是计划用几周的时间，对本专栏内容用作者的总结以及自己的相对逐字理解，来个通篇的文字记录学习，书读百遍，其义自现。  

###### 本篇是这个专栏的第三章：《V8工作原理》。本章分为三节。
<!--more-->
#### 12｜栈空间和堆空间：数据是如何存储的？
---
##### JavaScript是什么类型的语言
> 在使用之前就需要确认其变量数据类型的语言称为`静态语言`，相反地，我们把运行过程中需要检查数据类型的语言称为`动态语言`。    
> 我们把变量直接可以偷偷进行转换的操作称为隐式类型转换，支持隐式类型的语言称为`弱类型语言`，不支持隐式类型转换的语言称为`强类型语言`。      

> 显然，JavaScript是动态弱类型语言。    

##### JavaScript的数据类型
> JavaScript的数据类型一共有八种：  
> 基本数据类型：Boolean、Undefined、Null、String、Number、Bigint、Symbol      
> 引用数据类型：Object  

##### 内存空间
> 在JavaScript的执行过程中，主要有三种类型内存空间：代码空间、栈空间、堆空间。   
> 原始类型的数据值都是直接保存在栈中的，引用类型的值都是保存在堆空间中的。  
> 通常情况下，栈空间都不会设置太大，主要用来存放一些原始类型的小数据。堆空间很大，能存放很多大的数据。  
> 原始类型的赋值会完整复制变量值，而引用类型的赋值是复制引用地址。    

##### 产生闭包的核心
> 第一步是需要预扫描内部函数。
> 第二步是把内部函数引用的外部变量保存到堆中。  

#### 13 ｜ 垃圾回收：垃圾数据是如何自动回收的？ 
---
> 对一些不需要的数据，我们称之为垃圾数据，由于内存是有限的，为了释放内存，我们需要对这么垃圾数据进行回收。  
##### 不同语言的垃圾回收策略
> 通常情况，垃圾回收分为手动回收到自动回收两种策略。    
> 如C/C++C++使用的是手动回收策略，何时分配内存、何时销毁内存都是由代码控制的。  
> 如JavaScript、Java、Python等语言使用的是自动回收策略，产生的垃圾数据是由垃圾回收器来释放的。  
##### 调用栈中的数据是如何回收的    
> 栈中的垃圾回收相对比较简单：JavaScript引擎会通过向下移动ESP来销毁该函数保存在栈中的执行上下文。 
> ESP：记录当前执行状态的指针。
##### 堆中的数据是如何回收的
> 要回收堆中的数据，需要用到JavaScript中的垃圾回收器。

> 在介绍V8如何实现回收之前，首先要了解下`代际假说`内容。这是垃圾回收领域一个重要的术语，代际假说有两个特点：    
> + 第一个是大部分对象在内存中存在的时间很短，简单来说，就是很多对象一经分配内存，很快就变得不可访问.  
> + 第二个是不死的对象，会活得更久.  
> 这两个特点不仅仅适用于JavaScript，同样适应于大多数动态语言，如Java、Python等。    

> 在V8中会把堆分为新生代(支持1-8M容量)和老生代(容量大很多)两个区域，新生代中存放的是生存时间短的对象，老生代中存放的是生存时间久的对象。  
> + 副垃圾回收器，主要负责新生代的垃圾回收。    
> + 主垃圾回收器，主要负责老生代的垃圾回收。   

##### 垃圾回收器的工作流程
> 不论是主垃圾回收器还是副垃圾回收器，它们都有一套共同的执行流程。  
> + 第一步为标记活动对象与非活动对象。活动对象为还在使用的对象，非活动对象为要准备进行垃圾回收的对象。  
> + 第二步是回收非活动对象所占用的内存。既在标记后统一清理被标记为可回收的对象的内存。    
> + 第三步是内存整理。这是因为在频繁回收对象后，内存中会存在不连续空间，把这些不连续空间称为内存碎片。因此需要整理这些碎片，这是为了当那些较大连续内存出现时可以方便分配。【这步是可选的，副垃圾回收器不会产生内存碎片】。  
> 然后按照上述流程来分析新生代垃圾回收器（副垃圾回收器）和老生代垃圾回收器（主垃圾回收器）是如何处理垃圾回收的。    

##### 副垃圾回收器
> 副垃圾回收器主要负责新生代区的垃圾回收，虽然老生代区域不大，但是垃圾回收比较频繁。    
> 新生代中用Scavenge算法来处理。【Scavenge算法：把新生代空间对半划分为两个区域，一个是对象区域，一个是空闲区域。】  
> 过程大概就是：新加入对象放入都对象区域，快写满时进行垃圾清理操作，副垃圾回收器把这些对象复制到空闲区域，复制后的空闲区域没有内存碎片。完成复制后，对象区域与空闲区域角色翻转。角色翻转的操作能让新生代中的两块区域无限重复使用下去。  
> 因为新生区的空间不大，所以很容易被存活的对象装满整个区域。为了解决这个问题，JavaScript 引擎采用了对象晋升策略，也就是经过两次垃圾回收依然还存活的对象，会被移动到老生区中。

##### 主垃圾回收器
> 主垃圾回收器主要负责老生区中的垃圾回收.   
> 老生区中对象的两个特点：一是存活时间长，二是对象占用空间大。  
> 由特点我们知道采用副垃圾回收器的Scavenge算法显然不满足需求，因此，主垃圾回收器采用的是`标记-清除（Mark-Sweep）`算法进行垃圾回收。碎片过多会导致大对象无法分配到足够的连续内存，于是又产生了另外一种算法——`标记 - 整理（Mark-Compact）` .

#### 14 | 编译器和解释器：V8是如何执行一段JavaScript代码的
---
> 深入了解V8的工作原理，我们需要弄清除一些概念和原理，比如本节要学习的：`编译器(Compiler)`、`解释器(Interpreter)`、`抽象语法树(AST)`、`字节码(Bytecode)`、`即时编译器(JIT)`等概念。 
##### 编译器和解释器
> 编译器和解释器“翻译”代码的流程大致可阐述如下：    
> 1. 在编译型语言的编译过程中，编译器首先会依次对源代码进行词法分析、语法分析，生成抽象语法树（AST），然后是优化代码，最后再生成处理器能够理解的机器码。如果编译成功，将会生成一个可执行的文件。但如果编译过程发生了语法或者其他的错误，那么编译器就会抛出异常，最后的二进制文件也不会生成成功。    
> 2. 在解释型语言的解释过程中，同样解释器也会对源代码进行词法分析、语法分析，并生成抽象语法树（AST），不过它会再基于抽象语法树生成字节码，最后再根据字节码来执行程序、输出结果。    
##### V8是如何执行一段JavaScript代码的  
> V8在执行过程中既有解释器，又有编译器。分解其执行流程如下：    
###### 1.生成抽象语法树(AST)和执行上下文    
> 那么这个抽象语法树AST是什么呢？   
> 首先我们知道高级语言只是开发者可以理解的语言，但是让编译器或者解释器来理解就非常困难了。对于编译器或者解释器来说，他可以理解的是AST，所以无论是解释性语言还是编译型语言，在编译过程中，都会生成一个AST。  
> 一段代码经过javascript-ast站点处理后，AST的结构和代码结构非常之相似，具体结构就不展示了，类似于DOM树。AST的生成需要经过两个阶段： 
> + 第一阶段是`分词`，又称为`词法分析`。其作用是将一行行的源码拆解成一个个 token。所谓 token，指的是语法上不可能再分的、最小的单个字符或字符串。  
> + 第二阶段是`解析`,又称为`语法分析`。其作用是将上一步生成的 token 数据，根据语法规则转为 AST。    
###### 2.生成字节码
> 有了 AST 和执行上下文后，那接下来的第二步，解释器 Ignition 就登场了，它会根据 AST 生成字节码，并解释执行字节码。  
> 字节码就是介于 AST 和机器码之间的一种代码。但是与特定类型的机器码无关，字节码需要通过解释器将其转换为机器码后才能执行.之所以出现字节码，是Chrome团队为了解决内存占用问题而引入的。    
###### 3.执行代码
> 生成字节码之后，接下来就进入了执行阶段。 
> 在执行阶段，通常解释器逐条执行字节码，如果发现有热点代码(一段代码被重复执行多次)，那后台编译器会把该段热点的字节码编译为高效的机器码，然后当再次执行这段被优化的代码时，只需要执行编译后的机器码就可以了。这种字节码配合解释器和编译器的技术就称为`即时编译(JIT)`.