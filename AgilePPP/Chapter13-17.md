### 常见设计模式

#### Chapter 13  Command模式和Active Object模式

1. Command模式（命令模式）

   命令模式是最简单、最优雅的模式之一。常见用法是创建和执行事物操作，因为它很容易实现对请求的撤销和重做，并且易于扩展，增加新的命令对已有的命令不会产生影响

2. Active Object模式（主动对象模式）

   Active Object模式是实现多线程控制的一项古老技术

#### Chapter 14 Template Method模式和Strategy模式

​	两种模式都可以用来分离高层的算法和底层的具体实现细节，都允许高层的算法独立于它的具体实现细节重用

1. Template Method模式（模板方法模式）

   模板方法是当问题的解决方法都是同样的步骤，只是实现细节有所差别时，把解决方法放到一个抽象的基类中，让子类去真正实现解决方法的细节

2. Strategy模式（策略模式）

   策略模式是将问题的解决方法封装在不同的类中，这样可以以相同而方式调用所有的解决方法，减少各个方法之间的耦合

#### Chapter 15 Facade模式和Mediator模式

​	两种模式的作用都是把某种策略事假到另外一组对象，Facade模式是从上面施加策略，Mediator模式是从下面施加策略

1. Facade模式（外观模式）

   外观模式可以让复杂的东西看起来简单，将这种复杂的关系隐藏起来，使系统对外暴露的接口变少，调用一个接口可以实现很多方法，但不需要关注这些方法的实现细节，使功能的调用更加简单

2. Mediator模式（中介模式）

   中介模式是用一个中介对象封装一系列对象的交互，是对象间不需要显式的互相引用，从而使耦合松散

   #### Chapter 16 

#### Chapter 16 Singleton模式和Monostate模式

​	两种模式都是强制对象单一性的模式

1. Singleton模式（单例模式）

   好处：跨平台，适用于任何类，可以通过派生类创建，延迟求值

   坏处：摧毁（destory）方法未定义，不能继承，效率问题，不透明性

2. Monostate模式

   好处：透明想，可派生性，多态性

   坏处：不可转换性，效率问题，内存占用，平台局限性

   

#### Chapter 17 Null Object模式

​	该模式会消除对null的检查，有效防止空指针（NullPointException）检查对整个系统的影响，并且有助于简化代码。

​	Java8中可以使用Optional类有效避免NPE问题