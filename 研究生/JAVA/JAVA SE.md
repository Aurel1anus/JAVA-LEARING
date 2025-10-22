**java se 基础版 桌面应用开发**

java me 网站开发（网站=网页➕后台服务器）

java有跨平台工作能力，因为java代码运行在jvm这个虚拟机上，所以需要在系统上安装对应的jvm虚拟机（java可以跨平台，jvm不可以）

jre：java运行环境，有了这个就不需要单独安装jvm

jdk包含jre，提供了代码的编译工具和运行工具

JRE、JDK、JVM的作用

![[Pasted image 20250929111822.png]]

项目 -》模块-〉包-》类


TODO注释：待完成清单

小驼峰命名法：方法和变量
大驼峰命名法：类

int 最多只能记录10位数据，long数据定义时需要在数字后面加“L”
float类型数据定义时需要在数字后面加“f”

字符串的+：此时时字符串的连接符，而不是算数运算

System.out.println("it"+6666);  // it6666
System.out.println(6666+1+"nian"); // 6667nian

隐式转换：小的转成大的
强制转换：大的转成小的，会有精度的损失

扩展运算符自带强制转换 // b+=a

&&双与符号，带有短路效果，如果符号左边为false则右边不执行
||双或符号，带有短路效果，如果符号左边为ture则右边不执行

栈内存存放方法，包括方法中创建的变量
堆内存存放成员变量 

this指针就是当前对象的地址

public变量、方法可以在任意地方访问，意味着整个项目都可以访问
default只能在同一个包里访问
new关键字，作用是在堆空间中开辟内存
对象在方法中作为参数传递，传递的都是对象的地址

![[Pasted image 20251003173200.png]]


API：应用程序编程接口（已经写好的类）

java.long 包不需要导包

java里的break和continue可以通过标号进行控制，
```java
	abs: for (int i=0;i<8;i++){
		for(int j=0;j<4;j++){
			if(j==2)break abs;
			else if(j==1) continue abs;
		}
	}
```


java的键盘输入：
```java
 Scanner sc = new Scanner(System.in);
 int num = sc.nextInt();
```

java的打印：
```java
System.out.println
//ide里直接打sout
```

java支持单继承，但不支持多继承，支持多层继承
继承
```java
//父类
public class A{}
//子类
public class B extends A{}


//调用父类成员变量
super.a;
//父类构造函数
super();

```

子类中方法与父类中有方法一摸一样，调用的是子类方法（方法重写）

子类的所有构造方法（带参，不带参）都会调用父类的默认构造方法，而且是在构造方法的第一行、最开始时调用。
如果父类没有不带参构造方法，则需要手动的用super调用父类带参构造方法。
但是==最好最好==在父类上手动写上无参构造方法。

java所有类默认都继承了一个object类

final--(const)
final修饰基本数据类型，变量的值不能改
final修饰引用数据类型，变量名指向的地址不能改变
final修饰方法，该方法不能被重写
final修饰类，该类不能被继承

java 中的抽象方法
```java
abstract

public abstract class E{
	public abstract void abs();
}
```
抽象父类中的抽象方法，要在子类中进行重写。
抽象方法一定早在抽象类中
抽象类有（隐含的）构造函数，作用是给子类访问、重写。
抽象类可以没有抽象方法
抽象类的子类必须重写所有抽象方法

接口，就是抽象类，不允许实例化
```java
//接口定义
public interface name{}
//类实现接口
public class classname implements interA1, interA2{
	//重写接口中的抽象方法
}
```
接口可以多实现（不能多继承，但是可以多继承）
接口中的成员变量一定是常量，不管有没有加final。系统默认加public static final 
接口中没有（隐含的）构造方法。
接口中的成员方法只能是抽象方法。系统默认加public abstract


子类可以继承一个类，同时实现多个类
接口与接口之间可以单继承也可以多继承（而普通子类不能多继承）



## 多态
![[Pasted image 20251009184030.png]]
 ![[Pasted image 20251009184059.png]]
 什么叫做“有父类引用指向子类对象”，见下 
 ```java
 Employee e=new Coder;
 //new Coder代表了创建出来一个子类对象，
 //而Employee e代表了一个父类引用
 ```

多态创建对象后成员访问特点：
访问成员变量，编译看父类，运行也看父类。
访问成员方法，编译看父类，运行看子类。


==多态的出现可以提高代码的拓展性：==
在定义方法的时候，可以把该方法的形参定义成父类，在传入实参的时候传入子类对象。 

==多态的弊端是，不能使用子类的特定内容（方法，变量）==

父类引用可以强制转换回子类对象


判断一个对象是什么类的实例的关键字：
```java
if(A instanceof Dog){}
```

## 事件
动作监听，鼠标监听，键盘监听
```java
KeyListener// 键盘监听接口
MouseListener//鼠标监听接口
ActionListener//动作监听接口
```