教程

- 入门：https://juejin.cn/post/7023242274876162084
- 面试题：https://juejin.cn/post/7207659644487893051?searchId=202311161058157AAABBA3DB48F70E0846
- 官网：https://webpack.docschina.org/concepts/
- 视频：https://www.bilibili.com/video/BV14T4y1z7sw?p=2&vd_source=522153461914a766fc002cc8619314e4
- 自定义loader：https://juejin.cn/post/6891565484324585480#heading-11

常见操作

- 配置
- 插件、优化配置





## 核心关注点

学习策略

- 感觉没啥好学的



input：入口

output：出口

loader：加载器

plugin：插件

config：配置

env：环境



## input





## output





## config





## env





## loader

：把webpack不认识的资源转换成webpack认识的，比如语法转换，内容的拼接，如css-loader与style-loader

css-loader：负责解析css文件，转换语法

style-loader：负责将内容拷贝到style标签中





## plugin





## 问题

webpack中解释了为何webpack模块

- [模块（Modules） | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/concepts/modules/)

如何优化？

：主要方式就是清除、压缩（清呀）

- 方式1：先分析，看短板在哪里，再针对短板做优化
- 方式2：无脑优化，根据常见的优化手段进行优化，不管问题出在哪里

打包为什么要区分环境？

- 因为不同的环境有不同的需求
  - 开发环境：需要打包速度快、需要热更新、打印debug信息、需要sourcemap定位错误信息
  - 生产环境：需要打包体积小、需要做代码切割





