- [面向对象三大特性](#面向对象三大特性)
  - [一 封装](#一-封装)
    - [概念](#概念)
    - [优点](#优点)
    - [方法](#方法)
  - [二 继承](#二-继承)
    - [概念](#概念-1)
    - [优点](#优点-1)
    - [方法](#方法-1)
  - [三 多态](#三-多态)
    - [概念](#概念-2)
    - [优点](#优点-2)
    - [方法](#方法-2)
- [面向对象五大原则](#面向对象五大原则)
- [重写与重载](#重写与重载)
  - [概念](#概念-3)
  - [规则](#规则)
    - [重写](#重写)
    - [重载](#重载)
    - [区别](#区别)
- [==和equals的区别](#和equals的区别)
- [一个static方法内不可以调用非static方法](#一个static方法内不可以调用非static方法)
- [静态变量和实例变量的区别？](#静态变量和实例变量的区别)
- [String、StringBuilder、StringBuffer：](#stringstringbuilderstringbuffer)
- [Try catch finally的问题](#try-catch-finally的问题)
  - [当在try、catch中有return时，finally是否会执行？](#当在trycatch中有return时finally是否会执行)
- [final、finally、finalize](#finalfinallyfinalize)
- [Java中的异常分为两大类：](#java中的异常分为两大类)
- [List、Set、Map的区别？Map是否继承Conllection接口](#listsetmap的区别map是否继承conllection接口)
- [ArrayList和LinkedList的区别？](#arraylist和linkedlist的区别)
- [HashMap的工作原理介绍下，是线程安全的吗？](#hashmap的工作原理介绍下是线程安全的吗)
  - [底层数据结构](#底层数据结构)
  - [哈希表的优势：](#哈希表的优势)
  - [哈希表：](#哈希表)
  - [如何实现快速的存取？](#如何实现快速的存取)
- [java 中 IO 流分为几种?](#java-中-io-流分为几种)
  - [Java I0流的40多个类都是从如下4个抽象类基类中派生出来的](#java-i0流的40多个类都是从如下4个抽象类基类中派生出来的)
- [BIO,NIO,AIO 有什么区别?](#bionioaio-有什么区别)


# 面向对象三大特性

## 一 封装
### 概念
&emsp;&emsp;隐藏对象的属性和实现细节，仅公布接口。

&emsp;&emsp;封装最主要的功能在于我们能修改自己的实现代码，而不用修改那些调用我们代码的程序片段。

&emsp;&emsp;适当的封装可以让程式码更容易理解与维护，也加强了程式码的安全性。

### 优点
1. 良好的封装能减少耦合
2. 类的内部结构可以自由修改
3. 可以对成员变量进行更精确的控制
4. 隐藏信息实现细节 

### 方法
1. 修改属性的可见性来限制对属性的访问（一般限制为private）
2. 对每个值属性提供对外的公共方法访问，也就是创建一对赋取值方法，用于对私有属性的访问

## 二 继承
### 概念
&emsp;&emsp;继承就是子类继承父类的特征和行为，使得子类对象（实例）具有父类的实例域和方法，或子类从父类继承方法，使得子类具有父类相同的行为。
&emsp;&emsp;子类拥有父类的非private属性，方法
&emsp;&emsp;Java 的继承是单继承，但是可以多重继承，单继承就是一个子类只能继承一个父类，多重继承就是，例如 B 类继承 A 类，C 类继承 B 类，所以按照关系就是 B 类是 C 类的父类，A 类是 B 类的父类
提高了类之间的耦合性（继承的缺点，耦合度高就会造成代码之间的联系越紧密，代码独立性越差）

### 优点
代码复用

### 方法
使用 extends 关键字

super关键字：引用父类对象


## 三 多态
### 概念
&emsp;&emsp;多态是同一个行为具有多个不同表现实行或形态的能力
&emsp;&emsp;多态是一个接口，使用不同的实例而执行不同的操作

### 优点

1. 消除类型之间的耦合关系
2. 可替换性
3. 可扩充性
4. 接口性
5. 灵活性
6. 简化性

### 方法
- 继承
- 重写
- 父类引用指向子类对象：Parent p = new Child();


# 面向对象五大原则
1. 单一职责原则SRP(Single Responsibility Principle)
    　SRP是指一个类的功能要单一，不能包罗万象。如同一个人一样，分配的工作不能太多，否则一天到晚虽然忙忙碌碌的，但效率却高不起来。
2. 开放封闭原则OCP(Open－Close Principle)
    　一个模块在扩展性方面应该是开放的，而在更改性方面应该是封闭的。比如：一个网络模块，原来只提供服务端功能，而现在要加入客户端功能，那么应当在不用修改服务端功能代码的前提下，就能够增加客户端功能的实现代码，这要求在设计之初，就应当将服务端和客户端分开，公共部分抽象出来。
3. 里式替换原则LSP(the Liskov Substitution Principle)
    　子类应当可以替换父类并出现在父类能够出现的任何地方。比如：公司搞年度晚会，所有员工可以参加抽奖，那么不管是老员工还是新员工，也不管是总部员工还是外派员工，都应当可以参加抽奖，否则公司就不和谐了。
4. 依赖倒置原则DIP(the Dependency Inversion Principle)
   1. 高层模块不应该依赖低层模块，两者都应该依赖抽象
   2. 抽象不应该依赖细节
   3. 细节应该依赖抽象
   
   依赖倒置原则在java语言中的表现是：
    - 模块间的依赖通过抽象发生，实现类之间不发生直接的依赖关系，其依赖关系是通过接口或抽象类产生的。
    - 接口或抽象类不依赖实现类
    - 实现类依赖接口或抽象类
  
5. 接口分离原则ISP(the Interface Segregation Principle)
    模块间要通过抽象接口隔离开，而不是通过具体的类强耦合起来。
    设计时采用多个与特定客户类有关的接口比采用一个通用的接口要好。就比如一个手机拥有打电话，看视频，玩游戏等功能，把这几个功能拆分成不同的接口，比在一个接口里要好的多。

# 重写与重载
## 概念

- 重写（Override）
&emsp;&emsp;重写是子类对付类的允许访问的方法的实现过程进行重新编写，返回值和形参都不能改变。
子类根据需要实现自己的方法
- 重载（Overload）
&emsp;&emsp;是在一个类里面，方法名字相同，而参数不同（个数和类型不同），返回类型可以相同也可以不同
&emsp;&emsp;最常用的就是构造器的重载

## 规则
### 重写
- 参数列表与被重写方法的参数列表必须完全相同。

- 返回类型与被重写方法的返回类型可以不相同，但是必须是父类返回值的派生类（java5 及更早版本返回类型要一样，java7 及更高版本可以不同）。

- 访问权限不能比父类中被重写的方法的访问权限更低。例如：如果父类的一个方法被声明为 public，那么在子类中重写该方法就不能声明为 protected。

- 父类的成员方法只能被它的子类重写。

- 声明为 final 的方法不能被重写。

- 声明为 static 的方法不能被重写，但是能够被再次声明。

- 子类和父类在同一个包中，那么子类可以重写父类所有方法，除了声明为 private 和 final 的方法。

- 子类和父类不在同一个包中，那么子类只能够重写父类的声明为 public 和 protected 的非 final 方法。

- 重写的方法能够抛出任何非强制异常，无论被重写的方法是否抛出异常。但是，重写的方法不能抛出新的强制性异常，或者比被重写方法声明的更广泛的强制性异常，反之则可以。

- 构造方法不能被重写。

- 如果不能继承一个类，则不能重写该类的方法。

### 重载
- 被重载的方法必须改变参数列表(参数个数或类型不一样)；
- 被重载的方法可以改变返回类型；
- 被重载的方法可以改变访问修饰符；
- 被重载的方法可以声明新的或更广的检查异常；
- 方法能够在同一个类中或者在一个子类中被重载。
- 无法以返回值类型作为重载函数的区分标准。

### 区别
|区别点 | 重载 | 重写 |
| ---- | ---- | ---- |
|参数列表|必须修改|一定不能修改|
|返回类型|可以修改|一定不能修改|
|异常|可以修改|可以减少或删除，一定不能抛出新的或者更广的异常|
|访问|可以修改|一定不能做更严格的限制（可以降低限制）|


# ==和equals的区别
两个操作用于对象的比较，检查对象的相等性，但是区别在与equals是方法，而== 是操作符
一般使用== 比较原生类型如：boolean、int、char等等，使用equals比较对象
如果两个引用指向相同的对象== 返回true，equals方法的返回结果依赖于具体的实现，一般重写equals方法，也重写hashcode方法，
字符串的对比使用的是equals代替==操作符

# 一个static方法内不可以调用非static方法
因为非静态方法是与对象关联在一起的，必须创建一个对象后，才可以在该对象上进行方法调用，而静态方法调用不需要创建对象，也就是说，当一个静态方法被调用时，如果从一个static方法中发出对非static方法的调用，那么非静态方法关联到哪个对象上呢？这个逻辑无法成立。

static方法是静态方法，是属于类的方法；非static方法是属于对象的方法，所以要想在static方法中调用非static方法要先创建一个对象，再由这个对象来调用。
本质是JVM加载顺序决定的，加载static方法的时候非静态方法还没有初始化，当然不能调用了

# 静态变量和实例变量的区别？
1. 在语法定义上的区别：静态变量前要加static关键字，而实例变量前则不加
2. 在程序运行时的区别：实例变量是属于某个对象的属性，必须创建了实例对象，其中的实例变量才会被分配内存空间，才可以使用这个实例变量
   
&emsp;&emsp; 静态变量不属于某个实例对象，而是属于类，所以也称为类变量，只要程序加载了类的字节码，不用创建任何实例对象，静态变量就会分配内存空间，而且只分配一次，静态变量就可以被使用了。总之，实例变量必须创建后才可以通过这个对象来使用，静态变量则直接可以使用类名来调用。


# String、StringBuilder、StringBuffer：
1. 执行速度方面 ，StringBuilder大于StringBuffer大于String
String最慢的原因：String为字符串常量，而StringBuilder和StringBuffer均为字符串变量，即String对象一旦被创建后该对象是不可更改的，但后两者的对象是变量，是可以更改的

2. 线程安全：StringBuilder是线程不安全的，而StringBuffer是线程安全的（StringBuffer中很多方法带有synchronized关键字）–同步关键字

3. 总结：
   - String：适用于少量字符串操作的情况；
   - StringBuilder：适用于在单线程下在字符缓冲区进行大量操作的情况；
   - StringBuffer：适用于在多线程下在字符缓冲区进行大量操作的情况

String中的常用方法有哪些：
length()、isEmpty()、split()、toLowerCase()、toUpperCase()
subString()、trim()、concat(“abc”)、contains(“a”)

# Try catch finally的问题
## 当在try、catch中有return时，finally是否会执行？
总结：
1.不管有没有异常，finally中的代码都会执行
2.当try、catch中有return语句时，finally中的代码依然会继续执行
3.finally是在return后面的表达式运算之后执行的，此时并没有返回运算后的值，而是把值保存起来，不管finally对该值做了任何改变，返回的值都不会改变，依然返回保存起来的值，也就是说方法的返回值是在finally运算之前就确定了的。

4.如果return的数据是引用数据类型，而在finally中对该引用数据类型的属性值的改变起作用，try 中return返回的就是finally中改变后的属性值

5.finally代码最好不要包含return，程序会提前退出，也就是说返回的值不是try catch中的值

先执行try中的语句，包括return后面的表达式
有异常时，先执行catch中的语句，包括return 后面的表达式；
然后执行fianlly中的语句，如果finally里面有return语句，会提前退出
最后执行try 中的return，有异常执行catch中return；

在执行try catch 中的return之前一定会执行finally中的代码（如果finally存在），如果finally中有return语句，就会执行finally中的return方法，所以finally中的return语句一定会被执行的


# final、finally、finalize
final是最终的意思，表示不能被改变，可用于成员变量、方法和类
修饰变量：变量一旦被初始化不可改变
修饰方法：方法不能被覆盖
修饰类：类不能够被继承

finally：异常处理关键字，finally中的主体总会执行，无论异常发生与否
finalize:类的finalize方法，可以告诉垃圾回收器应该执行的操作，该方法从Object继承而来，在从堆中永久删除对象之前，调用该对象的finalize方法
注意：无法确切的保证垃圾回收器何时调用该方法，也无法保证调用不同对象方法的顺序，


# Java中的异常分为两大类：
　　

1. Checked Exception（非Runtime Exception）
2. Unchecked Exception（Runtime Exception）

    - 算数异常类：ArithmeticExecption
    - 空指针异常类型：NullPointerException
    - 类型强制转换类型：ClassCastException
    - 数组负下标异常：NegativeArrayException
    - 数组下标越界异常：ArrayIndexOutOfBoundsException
    - 违背安全原则异常：SecturityException
    - 文件已结束异常：EOFException
    - 文件未找到异常：FileNotFoundException
    - 字符串转换为数字异常：NumberFormatException
    - 操作数据库异常：SQLException
    - 输入输出异常：IOException
    - 方法未找到异常：NoSuchMethodException
    - 下标越界异常：IndexOutOfBoundsExecption
    - 系统异常：SystemException
    - 创建一个大小为负数的数组错误异常：NegativeArraySizeException
    - 数据格式异常：NumberFormatException
    - 安全异常：SecurityException
    - 不支持的操作异常：UnsupportedOperationException
    - 网络操作在主线程异常：NetworkOnMainThreadException  


# List、Set、Map的区别？Map是否继承Conllection接口

1. List :可以允许重复的对象
可以插入多个null元素
是有序的，保持了每个元素的插入顺序，输出的顺序就是插入的顺序
常用的List有ArrayList 、LinkedList，ArrayList最为流行，它提供了使用索引的随意访问，而LinkedList则对于经常需要从List添加或删除元素的场合更为合适

2. Set：不允许重复对象，
无序容器，你无法保证每个元素的存储顺序，TreeSet通过Comparator维护了一个排序顺序
只允许一个null元素
Set最流行的几个接口是HashSet、LinkedSet以及TreeSet

List、Set、Queue继承Connection接口，Map不是

3. Map：
Map不是connection的子接口或者实现类，Map是一个接口
Map的每一个Entry都是一个键值对，Map可能会有持有相同值对象但键对象不同（键对象必须是唯一的，否则会覆盖）
TreeMap也通过Comparator或者Comparable维护了一个排序顺序
Map里边可以拥有随意多个null值，但是只能有一个null键
Map最常用的几个实现类：HashMap、LinkedMap、HashTable、TreeMap （HashMap和TreeMap最为常见）

# ArrayList和LinkedList的区别？
1. ArrayList是基于动态数组实现的数据结构，动态扩容（默认初始大小是10），而LinkedList是基于链表的数据结构（Node内部类，next、pre、elemnet）
2. 对于随机访问get和set，ArrayList要优于LinkedList，因为LinkedList要移动指针，
3. 对于添加和删除操作add和remove，LinkedList要比ArrayList要快的多（数据多的情况下很明显）

# HashMap的工作原理介绍下，是线程安全的吗？
## 底层数据结构
HashMap底层用的是哈希表，哈希表是由数组和链表组成

## 哈希表的优势：
数组是存储空间连续的，占用内存严重，故空间复杂度很大，但数组的二分查找时间复杂度小，为o(1),数组的特点：寻址容易，插入和删除数据难
链表：链表存储空间离散，占用内存较为宽松，故空间复杂度很小，但时间复杂度很大，达到O（n），链表的特点：寻址困难，但是插入和删除元素较为简单

## 哈希表：
那我们能不能综合两者的特性，做出一种寻址容易，插入删除也方便的数据解耦，答案是肯定的，这就是我们提到的哈希表
HashTable既满足了数据的查找方便，同时也不用占用多态的内容空间，使用也十分方便
哈希表有多种不同的实现方法：最常用的就是拉链法可以理解为链表的数组，数组和链表的结合体

数组中每一个元素产生链表–发生碰撞的时候，就会在hashcode后面存储链表

另外一个说法：大家遇到的时候要知道:HashMap采用位桶（bucket）+链表实现
对于HashMap以及子类而言，它们呢采用Hash算法来决定集合中元素的存储位置，当系统开始初始化HashMap时，系统会自动创建长度为capacity长度的Entry数组，这个数组里可以存储元素的位置被称为桶（Bucket），每一个bucket都有其指定索引，系统可以根据索引快速访问该bucket里存储的元素。
无论何时，HashMap的每个桶只能存储一个元素，也就是一个Entry，由于Entry对象可以包含一个引用变量，就是 Entry构造器的最后一个参数，用于指向下一个Entry数组，因此可能出现的情况是：HashMap的bucket中只有一个Entry，但这个Entry指向另一个Entry，这就形成了一个Entry链

## 如何实现快速的存取？
HashMap的get实现
当HashMap的每个bucket里存储的Entry只是单个Entry，也就是没有通过指针产生Entry链时，此时的HashMap具有最好的性能，当程序通过key值取出对应的value值时，系统 只要先计算出该key的hashcode的返回码，在根据hashCode返回值找出该key在table数组中的索引，然后取出该索引处的Entry，最后返回该key值对应的value值即可。

HashMap的put操作：
对key的hashCode()做hash，然后在计算index，
如果没有碰撞则直接放到bucket，
如果碰撞了，以链表的形式存在buckets之后，
如果节点已经存在就替换old value(保证key的唯一性)
不存在时如果buckets满了，（超过load factor * current capacity）就要resize（扩容）
说明：当key值出现hash冲突的时候，链表中的第一个元素都是最后面添加进来的元素，之前的责备next变量引用着


# java 中 IO 流分为几种?
1. 按照流的流向分，可以分为输入流和输出流；
2. 按照操作单元划分，可以划分为字节流和字符流；
3. 按照流的角色划分为节点流和处理流。

## Java I0流的40多个类都是从如下4个抽象类基类中派生出来的
- InputStream/Reader: 所有的输入流的基类，前者是字节输入流，后者是字符输入流。
- OutputStream/Writer: 所有输出流的基类，前者是字节输出流，后者是字符输出流。


# BIO,NIO,AIO 有什么区别?
- 简答
1. BIO：Block IO 同步阻塞式 IO，就是我们平常使用的传统 IO，它的特点是模式简单使用方便，并发处理能力低。
2. NIO：Non IO 同步非阻塞 IO，是传统 IO 的升级，客户端和服务器端通过 Channel（通道）通讯，实现了多路复用。
3. AIO：Asynchronous IO 是 NIO 的升级，也叫 NIO2，实现了异步非堵塞 IO ，异步 IO 的操作基于事件和回调机制。
   
- 详细回答
1. BIO (Blocking I/O): 同步阻塞I/O模式，数据的读取写入必须阻塞在一个线程内等待其完成。在活动连接数不是特别高（小于单机1000）的情况下，这种模型是比较不错的，可以让每一个连接专注于自己的 I/O 并且编程模型简单，也不用过多考虑系统的过载、限流等问题。线程池本身就是一个天然的漏斗，可以缓冲一些系统处理不了的连接或请求。但是，当面对十万甚至百万级连接的时候，传统的 BIO 模型是无能为力的。因此，我们需要一种更高效的 I/O 处理模型来应对更高的并发量。
2. NIO (New I/O): NIO是一种同步非阻塞的I/O模型，在Java 1.4 中引入了NIO框架，对应 java.nio 包，提供了 Channel , Selector，Buffer等抽象。NIO中的N可以理解为Non-blocking，不单纯是New。它支持面向缓冲的，基于通道的I/O操作方法。 NIO提供了与传统BIO模型中的 Socket 和 ServerSocket 相对应的 SocketChannel 和 ServerSocketChannel 两种不同的套接字通道实现,两种通道都支持阻塞和非阻塞两种模式。阻塞模式使用就像传统中的支持一样，比较简单，但是性能和可靠性都不好；非阻塞模式正好与之相反。对于低负载、低并发的应用程序，可以使用同步阻塞I/O来提升开发速率和更好的维护性；对于高负载、高并发的（网络）应用，应使用 NIO 的非阻塞模式来开发
3. AIO (Asynchronous I/O): AIO 也就是 NIO 2。在 Java 7 中引入了 NIO 的改进版 NIO 2,它是异步非阻塞的IO模型。异步 IO 是基于事件和回调机制实现的，也就是应用操作之后会直接返回，不会堵塞在那里，当后台处理完成，操作系统会通知相应的线程进行后续的操作。AIO 是异步IO的缩写，虽然 NIO 在网络操作中，提供了非阻塞的方法，但是 NIO 的 IO 行为还是同步的。对于 NIO 来说，我们的业务线程是在 IO 操作准备好时，得到通知，接着就由这个线程自行进行 IO 操作，IO操作本身是同步的。