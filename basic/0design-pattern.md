教程

- 大纲：https://juejin.cn/post/6953423646664687652
- [指南](https://github.com/csxiaoyaojianxian/JavaScriptStudy)
- 常用的设计模式



## 核心问题

关注点

- 设计原则
- 设计模式
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
    - 适配器：使用时可能不想按之前的名称来，那可以用
    - 享元：
    - 组合：使用时可能不想区分部分与整体，期望都用同一套api
    - 门面：使用时可能不想关注具体的api，同一个功能都用同个api
  - 行为型：关注某个行为下，相关的对象之间的解耦
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
  - 常用的9种设计模式
    - 创建型：单例、工厂、建造者
    - 结构型：代理、适配器
    - 行为型：观察者、模板、职责链、策略



## 设计原则

：单接依开迪合

单一职责原则

接口隔离原则

依赖倒置原则

合成复用原则

迪米特原则



## 设计模式

- 





#### 单例模式



#### 工厂模式

：定义一个工厂方法，生成一个对象



#### 抽象工厂模式

：定义一组工厂方法，每个工厂方法生成一个对象，最终可以创建一组对象





- 







#### 观察者模式

应用场景

- 数据层与视图层解耦

如果没有观察者模式会怎样？

- 每个需求都对应一版处理函数，导致处理函数数量爆炸



#### 迭代器模式

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



#### 策略模式

好处

- 避免写大量的if、else



#### 职责链模式

与策略模式的区别

：策略模式根据请求去判断用哪个类，而职责链则是必须整体类过滤一遍



## 问题

一切皆对象如何理解？

- 是一切事物都有属性或方法，就算对象？

具体判断代码紧耦合还是松耦合？

- 

声明式与非声明式区别？

- 声明式：关注做什么
- 命令式：关注怎么做


