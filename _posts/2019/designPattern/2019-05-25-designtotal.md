---
layout: post
title: 设计模式总览
copyright: designpattern 
category: designpattern
tags: [designpattern]
keywords: designpattern,设计模式
---
###  概念
设计模式是一种经大量实践总结抽象出的代码通用设计技巧；能够让代码设计变得简洁、优雅、健壮、易扩展和维护；设计模式被广泛应用于经典的程序设计中，例如Spring、Mybatis等。

### 六大原则
总原则：开闭原则（Open Close Principle）
开闭原则就是说对扩展开放，对修改关闭。在程序需要进行拓展的时候，不能去修改原有的代码，而是要扩展原有代码，实现一个热插拔的效果。所以一句话概括就是：为了使程序的扩展性好，易于维护和升级。想要达到这样的效果，我们需要使用接口和抽象类等，后面的具体设计中我们会提到这点。

1、单一职责原则
不要存在多于一个导致类变更的原因，也就是说每个类应该实现单一的职责，如若不然，就应该把类拆分。

2、里氏替换原则（Liskov Substitution Principle）
里氏代换原则(Liskov Substitution Principle LSP)面向对象设计的基本原则之一。 里氏代换原则中说，任何基类可以出现的地方，子类一定可以出现。 LSP是继承复用的基石，只有当衍生类可以替换掉基类，软件单位的功能不受到影响时，基类才能真正被复用，而衍生类也能够在基类的基础上增加新的行为。里氏代换原则是对“开-闭”原则的补充。实现“开-闭”原则的关键步骤就是抽象化。而基类与子类的继承关系就是抽象化的具体实现，所以里氏代换原则是对实现抽象化的具体步骤的规范。—— From Baidu 百科

历史替换原则中，子类对父类的方法尽量不要重写和重载。因为父类代表了定义好的结构，通过这个规范的接口与外界交互，子类不应该随便破坏它。

3、依赖倒转原则（Dependence Inversion Principle）
这个是开闭原则的基础，具体内容：面向接口编程，依赖于抽象而不依赖于具体。写代码时用到具体类时，不与具体类交互，而与具体类的上层接口交互。

 

4、接口隔离原则（Interface Segregation Principle）
这个原则的意思是：每个接口中不存在子类用不到却必须实现的方法，如果不然，就要将接口拆分。使用多个隔离的接口，比使用单个接口（多个接口方法集合到一个的接口）要好。

 

5、迪米特法则（最少知道原则）（Demeter Principle）
就是说：一个类对自己依赖的类知道的越少越好。也就是说无论被依赖的类多么复杂，都应该将逻辑封装在方法的内部，通过public方法提供给外部。这样当被依赖的类变化时，才能最小的影响该类。

最少知道原则的另一个表达方式是：只与直接的朋友通信。类之间只要有耦合关系，就叫朋友关系。耦合分为依赖、关联、聚合、组合等。我们称出现为成员变量、方法参数、方法返回值中的类为直接朋友。局部变量、临时变量则不是直接的朋友。我们要求陌生的类不要作为局部变量出现在类中。

 

6、合成复用原则（Composite Reuse Principle）
原则是尽量首先使用合成/聚合的方式，而不是使用继承。


### 分类及简介
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019052413011038.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMyNzM2OTQ3,size_16,color_FFFFFF,t_70)
* **创建型模式**  (5种)

   **工厂模式(Factory Pattern):** 根据提供给工厂的数据，从一系列相关的类中选择一个类实例并返回。

   **抽象工厂模式(Abstract Factory Pattern):** 提供一个创建一系列相关或相互依赖对象的接口，而无需指定它们具体的类。

  **建造者模式(Builder Pattern):** 将一个复杂的构建与其表示相分离，使得同样的构建过程可以创建不同的表示。

  **原型模式(Prototype Pattern):** 用原型实例指定创建对象的种类，并且通过拷贝这些原型创建新的对象。

  **单例模式(Singleton Pattern)**: 保证一个类仅有一个实例，并提供一个访问它的全局访问点。
  
* **结构型模式** （7种）

   **适配器模式(Adapter Pattern):** 将一个类的接口转换成客户希望的另外一个接口。适配器模式使得原本由于接口不兼容而不能一起工作的那些类可以一起工作。
   
  **桥接模式(Bridge Pattern):** 类的接口和它的实现相分离，无需改变调用者的代码即可替代实现的过程。

   **组合模式(Composite Pattern):** 组合就是对象的结合。可以构建部分-整体的关系或数据的树形关系。

   **装饰模式(Decorator Pattern):** 动态地给一个对象添加一些额外的职责。就增加功能来说，装饰器模式相比生成子类更为灵活。

  **外观模式(Facde Pattern):** 为子系统中的一组接口提供一个一致的界面，外观模式定义了一个高层接口，这个接口使得这一子系统更加容易使用。

  **享元模式(Flyweight Pattern):** 通过共享（把参数移动外部）大幅地减少单个实例的数目。

  **代理模式(Proxy Pattern):** 为其他对象提供一种代理以控制对这个对象的访问。

* **行为型模式** (11种)

  **解释器模式(Interpreter Pattern):** 给定一个语言，定义它的文法表示，并定义一个解释器，这个解释器使用该标识来解释语言中的句子。
  
  **模板方法模式（Template Method Pattern):** 定义一个操作中的算法的骨架，而将一些步骤延迟到子类中。模板方法使得子类可以不改变一个算法的结构即可重定义该算法的某些特定步骤。

  **职责链模式(Chain of Responsibility Pattern):** 避免请求发送者与接收者耦合在一起，让多个对象都有可能接收请求，将这些对象连接成一条链，并且沿着这条链传递请求，直到有对象处理它为止。
 
  **命令模式(Command Pattern):** 将一个请求封装成一个对象，从而使您可以用不同的请求对客户进行参数化。

  **迭代器模式(Iterator Pattern):** 允许使用一个标准的接口顺序访问一个数据列表或集合。

  **中介者模式(Mediator Pattern):** 用一个中介对象来封装一系列的对象交互，中介者使各对象不需要显式地相互引用，从而使其耦合松散，而且可以独立地改变它们之间的交互。

  **备忘录模式(Memento Pattern):** 在不破坏封装性的前提下，捕获一个对象的内部状态，并在该对象之外保存这个状态，以便在适当的时候恢复对象。

  **观察者模式(Observer Pattern):** 定义对象间的一种一对多的依赖关系，当一个对象的状态发生改变时，所有依赖于它的对象都得到通知并被自动更新。

  **状态模式(State Pattern):** 允许对象在内部状态发生改变时改变它的行为，对象看起来好像修改了它的类。
  
  **策略模式(Stractegy Pattern):** 创建表示各种策略的对象和一个行为随着策略对象改变而改变的 context 对象。策略对象改变 context 对象的执行算法。

  **访问者模式（Visitor Pattern）**：表示一个作用于某对象结构中的各元素的操作。它使你可以在不改变各元素类的前提下定义作用于这些元素的新操作。

### spring 中用到的9大设计模式详解
[静态工厂（StaticFactory Method）](https://blog.csdn.net/qq_32736947/article/details/90583291)
[工厂方法（Factory Method）](https://blog.csdn.net/qq_32736947/article/details/90613388)
[单例模式（Singleton）](https://blog.csdn.net/qq_32736947/article/details/90649485)
[适配器（Adapter）](https://blog.csdn.net/qq_32736947/article/details/90695247)
[装饰（Decorator）](https://blog.csdn.net/qq_32736947/article/details/90708794)
[代理（Proxy）](https://blog.csdn.net/qq_32736947/article/details/90814940)
[观察者（Observer）](https://blog.csdn.net/qq_32736947/article/details/91129229)
[策略（Strategy）](https://blog.csdn.net/qq_32736947/article/details/91410454)
[模板方法（Template Method）](https://blog.csdn.net/qq_32736947/article/details/91488427)

### UML类图符号 各种关系说明以及举例
参考：https://www.cnblogs.com/h2zZhou/p/6256725.html






