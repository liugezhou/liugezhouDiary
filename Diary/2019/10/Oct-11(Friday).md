## **Daily Sentence**
#### <u>*No other misfortune can be compared with the loss of time.*</u>

## **Summary**

### Java变量类型
> 在Java语言中，所有的变量在使用前必须声明。
> Java语言支持的变量类型有:
> + 类变量：独立于方法之外的变量，用 static 修饰。

> + 实例变量：独立于方法之外的变量，不过没有 static 修饰。

> + 局部变量：类的方法中的变量。
> 访问修饰符不能用于局部变量；  
> 局部变量是在栈上分配的。  
> 局部变量没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。

### Java修饰符 ⭐⭐⭐⭐⭐
> Java语言主要提供了两种修饰符：访问修饰符和非访问修饰符。  
> 修饰符用来定义类、方法或者变量。通常放在语句最前端。
> 访问控制修饰符：  
+ default（即默认，什么也不写）：在同一包内可见，不使用任何修饰符。使用对象：类、接口、对象、方法。
+ private：在同一类内可见，使用对象：变量、方法。注意不能修饰类。
+ public：对所有类可见。使用对象：类、方法、接口、变量。
+ protected：对同一包内的类和所有子类可见。使用对象：方法、变量，注意不能修饰类。
##### 默认访问修饰符--不使用任何关键字
> 使用默认访问修饰符声明的变量和方法，对同一个包内的类是可见的。接口里的变量都隐式声明为 public static final,而接口里的方法默认情况下访问权限为 public。
```
String version = "1.5.1";
boolean processOrder() {
   return true;
}
```
##### 私有访问修饰符-private
> 私有访问修饰符是最严格的访问级别，所以被声明为 private 的方法、变量和构造方法只能被所属类访问，并且类和接口不能声明为 private。  
> 声明为私有访问类型的变量只能通过类中公共的 getter 方法被外部类访问。  
> Private 访问修饰符的使用主要用来隐藏类的实现细节和保护类的数据。
```
public class Logger {
    private String format;
    public String getFormat() {
        return this.format;
    }
    public String setFormat(String format) {
        this.format = format;
    }
}
```
##### 公有访问修饰符-public
> 被声明为 public 的类、方法、构造方法和接口能够被任何其他类访问。  
> 如果几个相互访问的 public 类分布在不同的包中，则需要导入相应 public 类所在的包.
##### 受保护的控制修饰符-protected
> protected 需要从以下两个点来分析说明：
> + 子类与基类在同一包中：被声明为 protected 的变量、方法和构造器能被同一个包中的任何其他类访问；  
> + 子类与基类不在同一包中：那么在子类中，子类实例可以访问其从基类继承而来的 protected 方法，而不能访问基类实例的protected方法。  

> protected 可以修饰数据成员，构造方法，方法成员，不能修饰类（内部类除外）。
> 接口及接口的成员变量和成员方法不能声明为 protected。