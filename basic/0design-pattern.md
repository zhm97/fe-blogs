教程

- 大纲：https://juejin.cn/post/6953423646664687652
- [JavaScriptStudy/06-设计模式 at master · csxiaoyaojianxian/JavaScriptStudy (github.com)](https://github.com/csxiaoyaojianxian/JavaScriptStudy/tree/master/06-设计模式)
- [浅谈前端出现率高的设计模式 - 掘金 (juejin.cn)](https://juejin.cn/post/7274146202496041018?searchId=202405211705399C841A1F25270B6C5782)



学习目标

- 不仅要懂概念
- 还要能够写出代码，了解适用场景，优缺点



## 关注点

设计原则

什么时候用，不要光学不会用，不知道哪里可以用上

薄弱点

- [ ] 没有实战代码
- [ ] 关注的设计模式过多，其实没必要的，想要抓很多的结果就是1个都抓不住



设计模式
- 创建型：关注创建对象动作
  - 单例：
  - 工厂方法：
  - 抽象工厂：
  - 建造者：
  - 原型：
- 结构型：关注结构组合动作，通过结构组合的方式，满足使用需求，而且保证定义与使用解耦，即不管你定义怎么变，都不会影响到我的使用
  - 桥接：使用格式不想受到影响，但是相关的类自身可能不断丰富
  - 代理：使用时可能需要加一些跟业务无关的功能
  - 装饰器：使用时可能需要动态的组合一些功能
  - 适配器
  - 享元：
  - 组合：使用时可能不想区分部分与整体，期望都用同一套api
  - 门面：使用时可能不想关注具体的api，同一个功能都用同个api
- 行为型：关注对象间的职责和通信，用于制定流程
  - 口诀：观察模板迭代的状态，命令中介解释职责，访问策略备忘录
  - 观察者：
  - 模板方法：
  - 迭代器：
  - 状态机：不同状态之间有耦合
  - 命令：
  - 中介者：
  - 解释器：
  - 职责链：职责链上下游没有耦合
  - 访问者：
  - 策略：不同策略互不影响，没有耦合
  - 备忘录：


- 



## 技巧

复杂代码才需要设计模式

- 如果只是简单功能则是没有必要使用设计模式，随便写

没办法区分设计模式是哪个类型，也不影响你的使用的



## 设计原则

：单接依开迪合

单一职责原则

- 其实是分1个类，还是多个类的来实现功能的问题

接口隔离原则：即高层不应该依赖于它不需要方法

- 比如BasicPrinter和AdvancedPrinter，后者多了扫描功能

依赖倒置原则：应该高层和底层都应该依赖于抽象，而不是高层直接依赖于底层

- 以前的高层模块直接调用底层模块，称为正向依赖，现在是高层和底层都依赖于抽象，比如抽象接口，所以叫依赖倒置
- 以EmailService和Notification举例，改成了EmailService 、Notification ，都依赖于MessageService接口

开闭原则：对扩展开放，对修改封闭，即可以扩展，不可以修改已有

- 

迪米特原则：最少知识原则

- 也就是调用第一层方法即可，不要太深入

合成复用原则：用组合或者是实现接口的方式代替集成

- 



## 设计模式

常用的9种设计模式

- 创建型：单例、工厂
- 结构型：组织已有的对象
  - 代理、适配器、装饰器
- 行为型：对象之间需要相互配合才能完成功能
  - 观察者、模板、职责链、策略
- 



#### :star:单例模式

场景

- 很多js文件就是导出一个对象，这样就能保证为单例对象了
  - 比如全局配置，export default AppConfig



#### :star:工厂模式

：定义一个工厂方法，生成一个对象



#### 抽象工厂模式

：定义一组工厂方法，每个工厂方法生成一个对象，最终可以创建一组对象



#### 桥接模式





#### :star:代理模式



#### :star:适配器模式

：不改动已有的接口，通过新增适配器类来解决问题，使得他们能够一起工作



#### :star:装饰器模式

：可以用来添加功能







#### :star:观察者模式

如果没有观察者模式会怎样？

- 每个需求都对应一版处理函数，导致处理函数数量爆炸



#### :star:模板方法模式

场景

- vue的表单处理器
  - 写一个基础的表单处理器，它的子类都要重写一些方法



#### :star:迭代器模式

分2种类型

- 内部迭代器
  - 自动迭代
- 外部迭代器
  - 可以手动控制迭代的过程



#### 状态模式



#### 命令模式

：为了将命令的发送者、接收者（执行者）解耦，目的是实现对命令的队列、延迟、记录、撤销

如果不用呢？

- 难以或者是需要手动实现命令队列、撤销、记录



#### :star:策略模式

好处

- 每次新增策略，都不用修改计算奖金的方法





#### :star:职责链模式

与策略模式的区别

：策略模式根据请求去判断用哪个类，而职责链则是必须整体类过滤一遍



- 



## 问题

依赖关系图中

- 箭头指向谁，就依赖谁

一切皆对象如何理解？

- 是一切事物都有属性或方法，就算对象？

具体判断代码紧耦合还是松耦合？

- 

声明式与非声明式区别？

- 声明式：关注做什么
- 命令式：关注怎么做



