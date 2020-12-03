<a name="index">**Index**</a>
&emsp;<a href="#0">一、类</a>  
&emsp;&emsp;<a href="#1">  1.访问修饰符：公共类修饰符public</a>  
&emsp;&emsp;<a href="#2">2.非访问控制符：抽象类修饰符 abstract 、最终类修饰符 final  </a>  
&emsp;<a href="#3">二、方法修饰符</a>  
&emsp;&emsp;<a href="#4">1.访问控制修饰符</a>  
&emsp;&emsp;<a href="#5">2.非访问控制修饰符</a>  
&emsp;<a href="#6">三、变量修饰符</a>  
&emsp;&emsp;<a href="#7">1.访问控制符</a>  
&emsp;&emsp;<a href="#8">2.非访问控制符</a>  
&emsp;<a href="#9">四、访问控制修饰符总结</a>  
## <a name="0">一、类</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>
### <a name="1">  1.访问修饰符：公共类修饰符public</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

&emsp;	公共类修饰符 public ： Java 语言中类的访问控制符只有 public 即公共的。每个 Java 程序的有且只有一个类是 public，它被称为主类 ，其他外部类无访问控制修饰符，具有包访问性。注意：一个类的内部类可以被其他访问控制修饰符protected、缺省默认(default、friendly)、private修饰，相当于类的成员。  
&emsp;	注意：Java类或属性如果缺省访问控制修饰符，就属于default/friendly类型修饰符，但是实际上Java中并没有名为default或者friendly的访问修饰符(即不能使用default或者friendly定义类或变量)，只是为了方便标识缺省访问控制符的情况。

### <a name="2">2.非访问控制符：抽象类修饰符 abstract 、最终类修饰符 final  </a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

（1）抽象类修饰符 abstract ：用 abstract 修饰符修饰的类，被称为抽象类。  
（2）最终类修饰符 final ：当一个类不能被继承时可用修饰符 final修饰为最终类。被定义为 final 的类通常是一些有固定作用、用来完成某种标准功能的类。  
（3）类缺省访问控制符：如果一个类没有访问控制符，说明它具有缺省的访问控制符特性。此时，这个类只能被同一个包中的类访问或引用。这一访问特性又称为包访问性。  
    
## <a name="3">二、方法修饰符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>
### <a name="4">1.访问控制修饰符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

   公共访问控制符public、保护访问控制符protected、缺省默认访问控制符、私有访问控制符private

### <a name="5">2.非访问控制修饰符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

   抽象方法控制符abstract 、静态方法控制符static 、最终方法控制符final 、本地方法控制符native 、同步方法控制符synchronized

  （1）抽象方法控制符 abstract ： abstract 修饰的方法称为抽象方法。抽象方法仅有方法头，没有方法体和具体实现。

  （2）静态方法控制符 static ：用修饰符 static 修饰的方法称为静态方法。静态方法是属于整个类的类方法；而不使用static 修饰、限定的方法是属于某个具体类对象的方法。 由于 static方法是属于整个类          的，所以它不能操纵和处理属于某个对象的成员变量，而只能处理属于整个类的成员变量，即 static 方法只能处理 static的域。

  （3）最终方法控制符 final ：用修饰符 final修饰的方法称为最终方法。最终方法是功能和内部语句不能更改的方法，即最终方法不能重写覆盖。final固定了方法所具有的功能和操作，防止当前类的子类对父类          关键方法的错误定义，保证了程序的安全性和正确性。所有被 private 修饰符限定为私有的方法，以及所有包含在 final 类 ( 最终类) 中的方法，都被认为是最终方法。
  
   （4）本地方法控制符 native ：用修饰符 native 修饰的方法称为本地方法。为了提高程序的运行速度，需要用其它的高级语言书写程序的方法体，那么该方法可定义为本地方法用修饰符 native 来修饰。
   
   （5）同步方法控制符 synchronized ：该修饰符主要用于多线程程序中的协调和同步。
    
    
## <a name="6">三、变量修饰符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>
### <a name="7">1.访问控制符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

   公共访问控制符public 、保护访问控制符protected 、缺省默认访问控制符、私有访问控制符private。

  （1）公共访问控制符 public：用 public 修饰的域称为公共域。由于 public 修饰符会降低运行的安全性和数据的封装性，所以一般应减少 public 域的使用。
  （2）私有访问控制符 private：private 修饰的成员变量只能被该类自身所访问，不能被其它任何类 ( 包括子类 ) 访问。
  （3）保护访问控制符 protected：用 protected 修饰的成员变量可以被三种类所引用：①该类自身；②同一个包中的其它类；③其它包中的子类。使用修饰符 protected 的主要作用是允许其它包中的子类来访问父          类的特定属性。
  （4）缺省默认修饰符 ：没有访问控制符或者是用default修饰的成员变量可以被该类本身或同一包中的其他类访问。

### <a name="8">2.非访问控制符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

   静态域修饰符static 、最终域修饰符 final 、易失 ( 共享 ) 域修饰符volatile 、暂时性域修饰符transient。

  （1）静态域修饰符 static ：用 static修饰的成员变量仅属于类的变量，而不属于任何一个具体的对象，静态成员变量的值是保存在类的内存区域的公共存储单元，而不是保存在某一个对象的内存区间。该类的任          一对象访问它时取到的都是相同的数据；该类的任一对象修改它时 , 也都是对同一个内存单元进行操作。

  （2）最终域修饰符 final ：最终域修饰符 final 是用来定义常量的。一个类的域 ( 成员变量 ) 如果被修饰符 final 说明，则它的取值在程序的整个执行过程中都是不变的。

   [关于修饰符final 更多细节请参考：](https://blog.csdn.net/u012723673/article/details/80580011)  

  （3）易失 ( 共享 ) 域修饰符 volatile ：易失 ( 共享 ) 域修饰符 volatile是用来说明这个成员变量可能被几个线程所控制和修改。也就是说在程序运行过程中，这个成员变量有可能被其它的程序影响或改变          它的取值。通常 volatile 用来修饰接受外部输入的域。

   [关于修饰符volatile更多细节请参考：](https://blog.csdn.net/u012723673/article/details/80682208)  

  （4）暂时性域修饰符 transient ：暂时性域修饰符 transient 用来定义一个暂时性变量。其特点是：用修饰符transient 限定的暂时性变量，将指定 Java虚拟机认定该暂时性变量不属于永久状态，以实现不同          对象的存档功能。否则，类中所有变量都是对象的永久状态的一部分，存储对象时必须同时保存这些变量。

   [关于修饰符transient更多细节请参考：](https://blog.csdn.net/u012723673/article/details/80699029)
   
   
## <a name="9">四、访问控制修饰符总结</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>
| 访问级别 | 访问控制修饰符 | 同类 | 同包 | 子类(不同包) | 不同包(其他类) |
| ---- | ---- | ---- | ---- | ----| ---- |
|公共|	public|	允许|	允许|	允许|	允许|
|受保护|	protected|	允许|	允许|	允许|   不允许|
|默认|	缺省修饰符|	允许|	允许|	不允许|	不允许|
|私有|	private|	允许|	不允许|	不允许|	不允许|

