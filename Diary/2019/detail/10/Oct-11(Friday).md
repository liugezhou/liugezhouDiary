## **Daily Sentence**
#### <u>*No other misfortune can be compared with the loss of time.*</u>

## **Summary**

### Java变量类型 ⭐⭐⭐⭐⭐
> 在Java语言中，所有的变量在使用前必须声明。type identifier = value
> Java语言支持的变量类型有:
> + 局部变量：类的方法中的变量。
> 声明位置：方法、构造方法或者语句块中。
> 存在周期：被执行的时候创建，当它们执行完成后，变量将会被销毁； 
> 访问修饰符：不能用于局部变量；  
> 分配位置：局部变量是在栈上分配的。  
> 局部变量没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。
```
package com.runoob.test;
 
public class Test{ 
   public void pupAge(){
      int age = 0;
      age = age + 7;
      System.out.println("小狗的年龄是: " + age);
   }
   
   public static void main(String[] args){
      Test test = new Test();
      test.pupAge();
   }
}
```

> + 实例变量：独立于方法之外的变量，不过没有 static 修饰。
> 声明位置：声明在一个类中，但是在方法、构造方法和语句外。  
> 存在周期：在对象创建的时候创建，在对象被销毁的时候销毁； 
> 访问修饰符：可以修饰。  
> 实例变量可以声明在使用前或者使用后。  
> 实例变量对于类中的方法、构造方法或者语句块是可见的。一般情况下应该把实例变量设为私有。通过使用访问修饰符可以使实例变量对子类可见； 
> 实例变量具有默认值。数值型变量的默认值是0，布尔型变量的默认值是false，引用类型变量的默认值是null。变量的值可以在声明时指定，也可以在构造方法中指定;  
> 实例变量可以直接通过变量名访问。但在静态方法以及其他类中，就应该使用完全限定名：ObejectReference.VariableName。
```
import java.io.*;
public class Employee{
   // 这个实例变量对子类可见
   public String name;
   // 私有变量，仅在该类可见
   private double salary;
   //在构造器中对name赋值
   public Employee (String empName){
      name = empName;
   }
   //设定salary的值
   public void setSalary(double empSal){
      salary = empSal;
   }  
   // 打印信息
   public void printEmp(){
      System.out.println("名字 : " + name );
      System.out.println("薪水 : " + salary);
   }
 
   public static void main(String[] args){
      Employee empOne = new Employee("RUNOOB");
      empOne.setSalary(1000);
      empOne.printEmp();
   }
}
```

> + 类变量：也称`静态变量`，独立于方法之外的变量，用 static 修饰。
> 静态变量除了被声明为常量外很少使用。常量是指声明为public/private，final和static类型的变量。常量初始化后不可改变。  
> 静态变量储存在静态存储区。经常被声明为常量，很少单独使用static声明变量。 
> 与实例变量具有相似的可见性。但为了对类的使用者可见，大多数静态变量声明为public类型。
```
import java.io.*;
 
public class Employee {
    //salary是静态的私有变量
    private static double salary;
    // DEPARTMENT是一个常量
    public static final String DEPARTMENT = "开发人员";
    public static void main(String[] args){
    salary = 10000;
        System.out.println(DEPARTMENT+"平均工资:"+salary);
    }
}
```


### Java修饰符 ⭐⭐⭐⭐⭐
> Java语言主要提供了两种修饰符：访问修饰符和非访问修饰符。  
> 修饰符用来定义`类`、`方法`或者`变量`。通常放在语句最前端。
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