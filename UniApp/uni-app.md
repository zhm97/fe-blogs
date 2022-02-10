[TOC]

uni-app

：uni-app是基于vuejs的**前端应用**开发框架，特点是：**支持跨端**

## 问题

开发经验干什么？

- 能帮你避坑，少花点时间，少犯错误，动不动？

调试居然也要配置？我吐了

- 

[为什么选uni-app](https://juejin.cn/post/6961663378083282951)

- 所有跨端应用中它做到了最好
- 案例多、生态丰富、



sdk？

：就是软件开发工具包

使用场景

- 还需要引入的？

插件与框架的区别？

- 插件是负责某个功能的
- 而框架指定了这个项目的骨架

云开发？

- 

什么是业务页面？什么是非业务页面？

- 

编译与打包

- 编译是会修改对源代码进行解析的，而打包不会，他只是复制而已

[sitemap？](https://jingyan.baidu.com/article/8ebacdf00ea40a49f65cd5b8.html)

- 网站地图，主要是告诉搜索引擎，方便搜索引擎抓取内容，就像打仗一样，地图非常重要

调试也需要配置吗？还分app、h5、小程序

官方也会有坑的，哈哈，

- 比如编译器



**路由**



刷新算哪种路由方式？还是不算？

- 

页面将全部出栈跟当前页面出栈本质？

- 页面能不能返回的问题而已，全部出就不能咯

页面存在栈里有什么好处？数据保留着吗？

- 

app应用与非app区别？

- app端的渲染方式是原生的
- 非app则是webview渲染

flex布局你需要搞清楚

mp是mini program

第三方服务

：很多都是第三方提供的，比如登录、支付、分享（有人用的第三方），我们只是负责调用，

小程序的运行环境是什么？

- 微信内置浏览器？

ui的结构你要清楚，有哪几部分？

- 状态栏：顶部的时间那一栏是状态栏，
- 导航栏：（分顶部和底部导航栏）

[web框架？](https://blog.csdn.net/weixin_42976659/article/details/88187868)

- 即开发web应用相关的框架

有些组件可以通过配置即可以实现的，比如搜索栏，但是有些平台可能不支持，如小程序

- 



## 框架简介

主要的配置文件简称mp：manifest、pages.json，主要是pages配置（顶部导航栏、tabBar、路由都是pages来配置）

生命周期分：应用、页面、组件生命周期，uniapp都是on开头的，而vue则是before开头的

- 应用：onLoad、onShow、onHiden
- 页面：onInit、onLoad、onShow、onHiden
  - onInit那里获取上一页传入的参数
- 组件生命周期则是与vue的相同



## 内置组件

## api

uniapp的api都是uni开头的



## 扩展组件

：uni-ui就是扩展组件，我可以批量导入

## 模板

## uview

- [引入方式](https://www.jianshu.com/p/d2900005b32a)：非常的土气，还不如node的方式

## uniCloud

：这个暂时碰不到，云开发来着，应该是升级版

- 

## 规范



## 技巧

uni-app

：基于vue的应用开发框架，特点是支持跨平台

uni-app常见操作

- [入门](https://juejin.cn/post/6899642866693423111#heading-22)
- [大纲](https://juejin.cn/post/6963637441177583647#heading-19)
- [专栏](https://juejin.cn/column/6961663481250578462)

看先看一下基本的功能，uni主要是用来干什么的，官方文档不要全看，重点看一下**框架简介**，然后就上手开发了



uni-app由于会接触到多端，所以，坑可能会有很多，小程序支持的，h5未必支持，要想到这一点，祝你好运，

- 

[uni-app学习资料&开源项目](https://github.com/aben1188/awesome-uni-app/blob/master/README.md)



[uni-app的开发经验](https://juejin.cn/post/6844903910876905486)

版本只是个数字而已，不要追求什么最新的版本，你要考虑他的兼容性、适配性的问题



市场上有大量的模板：就是不知道他用的技术栈是什么

- [电商模板](https://ext.dcloud.net.cn/plugin?id=200)



web应用开发来说就是3步

- 第一步是画页面（一定要快）
- 第二步是写交互（思路要先弄清楚，可画图，再写）
- 第三步是优化（这个一般碰不到，哈哈）



## 小程序

#### 项目准备

- 微信开发工具
- postman
- 

#### 项目搭建

**目录**

- components
- 

#### 编码

- 清除元素样式

- 封装request、

- 引入ui库：

- uni适配vue，但是不是完全适配，可能有些vue的东西不支持

#### 测试

#### 发布

- 记得写正确的appid，还有域名白名单要加上
- 需要在hb编译，不要在微信开发者工具编译，而且发布上传的应该是dist包，而不是dev，dev的太大了

## uview

坑

- actionSheet组件的closeOnClickOverlay属性，傻逼设计来的，害我理解错了，自己还设计了一个开关，

#### js

请求都给你集成进去了

## 项目经验

项目教程

- 入门级
  - https://www.bilibili.com/video/BV1vh411B7Sb?p=31
  - https://www.bilibili.com/video/BV11Z4y1K7yY?from=search&seid=12109527285847760697&spm_id_from=333.337.0.0
- 

：我觉得学完视频点播（入门）、商城（中级）、微信项目（高级），再自己贡献一个插件（禅道），我就是个uni-app的大神了，哈哈，

获取当前用户信息的实现

- 只需要调用请求用户信息的授权即可
- 不需要登录

微信登录的实现

- 

[可以通过媒体查询来决定显示不同精度的图片](https://juejin.cn/post/6844903845617729549)，即根据dpr来决定显示哪种类型的图片

- 我现在要讨论的是移动端适配的问题
- 目前的策略（按蓝湖的尺寸直接写rpx，因为设计稿是750px，默认是按照dpr为2来算的，但其实这样做有个问题，如果设备为dpr为3，你只是把图片尺寸拉长了3倍，图片会失真）
- dpr
  - 设备像素/设备独立像素=dpr，设计独立像素即逻辑像素，如果写rpx则是设备像素，我们写的px就是设备独立像素，
  - 

在小程序的导航栏中自定义组件，

- 但是小程序不仅仅要放到指定文件夹，而且还要只能是小程序的格式wxml

操，被带偏了，只有使用自定义导航栏，不是使用自定义组件的意思

- 可以通过uni-nav-bar