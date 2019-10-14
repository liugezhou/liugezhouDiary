## **Daily Sentence**
#### <u>*Java基础知识的学习--第三天*</u>

### 非访问修饰符 
##### static
> + 静态变量： 
> static 关键字用来声明独立于对象的静态变量，无论一个类实例化多少对象，它的静态变量只有一份拷贝。 静态变量也被称为类变量。局部变量不能被声明为 static 变量。  
> + 静态方法：  
>  static 关键字用来声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法从参数列表得到数据，然后计算这些数据。

>  对类变量和方法的访问可以直接使用 classname.variablename 和 classname.methodname 的方式访问。
##### final
> + final 变量：
>  final 表示"最后的、最终的"含义，变量一旦赋值后，不能被重新赋值。被 final 修饰的实例变量必须显式指定初始值。  
>  final 修饰符通常和 static 修饰符一起使用来创建类常量。  

> + final 方法
>  父类中的 final 方法可以被子类继承，但是不能被子类重写。  
>  声明 final 方法的主要目的是`防止该方法的内容被修改`。  
>  如下所示，使用 final 修饰符声明方法。

> + final 类
> final 类不能被继承，没有类能够继承 final 类的任何特性。 

#### abstract
> + 抽象类：
> 抽象类`不能用来实例化对象`，声明抽象类的唯一目的是`为了将来对该类进行扩充`。  
> 一个类不能同时被 abstract 和 final 修饰。如果一个类包含抽象方法，那么该类一定要声明为抽象类，否则将出现编译错误。  
> `抽象类可以包含抽象方法和非抽象方法`。
实例
```
abstract class Caravan{
   private double price;
   private String model;
   private String year;
   public abstract void goFast(); //抽象方法
   public abstract void changeColor();
}
```
> + 抽象方法
> 抽象方法是一种没有任何实现的方法，该方法的的具体实现由子类提供。  
> 抽象方法不能被声明成 final 和 static。  
> `任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类。`  
> 如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法。   
> 抽象方法的声明以分号结尾，例如：public abstract sample();     
> 实例
```
public abstract class SuperClass{
    abstract void m(); //抽象方法
}
 
class SubClass extends SuperClass{
     //实现抽象方法
      void m(){
          .........
      }
}
```
#### synchronized 修饰符
> synchronized 关键字声明的方法同一时间只能被一个线程访问。