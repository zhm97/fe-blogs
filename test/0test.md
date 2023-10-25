本文档主要是书写测试相关的内容

教程

- 测试：<https://juejin.cn/post/6844903511365255182>
- <https://juejin.cn/post/7213362704783196218>
- 前端bug：
  - 常见8种问题：<https://juejin.cn/post/6932813279089672199>
- 后端bug
  - <https://www.cnblogs.com/jinziguang/p/14927414.html>
- vscode调试：<https://juejin.cn/post/7080135520902184997>



## 驱动问题

#### 关注点

- 

怎样才能算是做好了测试工作？

- 把测试中常见的几个点都考虑到了
- 善于利用测试工具
- 补测试文档
- 提前挖掘易错点，比如计数的问题，生成了重复的no

测试需要考虑的点

- 准确性
- 覆盖率
- 安全性
- 兼容性

每开发新功能、或扩展完新功能，都要仔细测一下，如果一个东西老是出问题，别人就会失去对你的信任，甚至是可以被提桶咯，现在是有名刀帮你顶着
：要有联想能力，迅速想到影响范围，然后根据这些范围去测试



## 后端常见的bug



## 前端常见bug

获取

- 查询条件变更，但是前端没改
- 查询参数漏传
  - 比如需要不分页，没传isPaging为false，导致只拿到了第一页的数据

**通用bug**

- 类型不一致：之前只接收字符串，现在传递的却是数组
- 没有兼容多类型：比如需要字符串，也需要兼容数组
- 类型判断错误：比如通过.length来判断是否为数组，但是传递的是字符串也能通过这个判断，导致出错
- 未考虑边界情况
  - 传递的是空数组，但是没有判断，导致出错
  - 读到边界外去了



## bad code

- 逻辑太绕
- 嵌套太深：3层及以上
- 重复代码：维护困难，容易漏改
-

## 调试

前端项目

- 直接代码里写debugger就行

debug的时候需要开启原来的服务吗？还是直接开启debug服务即可
：vscode两种方式都支持，launch、attach，取决于你用的是哪种方式

调试过程中想要终止本次调试，但是不想终止服务，怎么办？

- 终止调试：点击左侧的红色按钮

为啥调试会话自己会结束？我没有去控制时间啊，程序也没有崩溃啊



## 性能分析工具

打脸专用，免得别人瞎扯，要用数据来征服别人



## 测试技巧

口诀：漏对时+多检查

- 漏写：这是我经常卡顿的原因
- 对象错误：这是经常会搞错的，写错了对象
- 时序问题：这个比较隐蔽
- 自己先列举一下常见的场景，拿少量的数据，完整测一遍
- 然后给人使用一下，看看有没有遗漏的场景
- 一定要学会快速的测试
  - 比如不要执行插入动作，注释掉插入数据库的那行代码，或者是打上断点
- 浏览器可以选择重新发送 replay，这样也可以不用每次都去填写了
- 可以用snapshot快速截图，可以实现快速的对比
- 可以写一下默认值，这样就不用每次都去填写了，调试完再解除注释
- 接口调试时，需要做登录校验
  - 这要怎么玩？
- 别人的账号显示有问题
  - 你登录你自己的号来

有空时候多检查一下代码
：早发现，早解决

#### 快速调试

**代码阅读技巧**

目标

- 快速的阅读别人的代码
- 要有移植能力，而不是自己从 0 开始

关注组织结构

- 先搞清楚目标，这个技术主要解决了什么问题
- 我需要做什么？哪些模块是别人提供的，哪些才是自己负责的？
- 如何访问，如何注册
  - 有些不是一口气能拿到的，而是只能通过中间的一些步骤才能拿到
- 谁来调用
- 返回谁

很多时候别人是用测试代码来演示的

- 你要能找到测试代码，并且看懂他们想要表达的意思

有些值是根据其它值算出来的，而不是自己设置出来的

设计是按时间线，即业务场景走下去的，而实现则是按功能模块来划分的，有些相似的功能就会被放到一起

拿到一些账号信息

- 首先要整理
- 然后自己验证一遍，不然到时要用的时候来不及

关注主流程，不要投入关注不影响主流程的东西
关注一下好的写法，从而避免一些问题
：比如 elementPlus 关闭弹窗无法清除数据的问题

校验问题
：目的：防止插入错误的、虚假的记录

有些步骤执行是有隐藏条件的

- 插入
  - 名称在某个范围内需要唯一，所以需要先查找一下有没有重名的
- 查询
  - 需要只能是激活状态的才能被查询出来，被删除或或者是被禁用的，都不能出现
- 条件可能需要组合来过滤

一定要相信自己的观点，不要轻易被别人打断理念
：你有50%的概率是对的！！！





## 问题

测试的必要性

- 

源码调试跟跑测试用例是同一个概念吗？

：不是的

- 源码调试：跟你自己的项目有关
  - sourcemap可以在生产环境上调试
- 测试用例：一般是自动的

sourcemap会对性能有影响吗？

- 有，但是不大
