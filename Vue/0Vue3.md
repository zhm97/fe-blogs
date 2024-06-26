教程

- 
- 异常处理：https://juejin.cn/post/6932620551827488775?searchId=202311171734478FA08540E39199F5004F
- vue中使用jsx：https://juejin.cn/post/7272308621710213161
- 面试题
  - [【🐰中小厂前端面经】三年工作经验求职时会被问些什么? - 掘金 (juejin.cn)](https://juejin.cn/post/7266721485811925033#heading-60)
- nuxt：[路由 · 快速入门 Nuxt](https://nuxt.com.cn/docs/getting-started/routing)



## 核心问题

#### 关注点

- vue3
- 借助官方的demo：vue3练习的demo应该如何搭建？避免重复学习
  - 官网其实已经很详细了
- 路由vue-router
- 状态管理pinia
- 构建工具vite
- hook风格
- jsx
- 调试能力
- 测试能力：可选
- 兼容问题





#### vue插件

- [vuejs/awesome-vue: 🎉 A curated list of awesome things related to Vue.js (github.com)](https://github.com/vuejs/awesome-vue)



#### 项目

除了管理系统，还有啥好做的？

教程

- [bradtraversy/50projects50days: 50+ mini web projects using HTML, CSS & JS (github.com)](https://github.com/bradtraversy/50projects50days?tab=readme-ov-file)
- 管理系统
  - geeker：[路由、菜单 | Geeker-Admin (spicyboy.cn)](https://docs.spicyboy.cn/guide/router.html)
  - vben：[常见问题 | Vben Admin (vvbin.cn)](https://doc.vvbin.cn/other/faq.html#接口请求问题)




类型

- 数据可视化项目
- 在线教育平台
  - 有些有复杂交互的项目
- 游戏网站
- 地图应用
- 实时通信应用



## 面试题

响应式？

- 原理：通过proxy拦截对象属性的读取或写入操作，并将其转换成getter和setter，
- 结果：数据改变，视图更新





## 基础

#### 生命周期

：口诀，cmuu

教程

- https://juejin.cn/post/7093880734246502414#comment





#### [组件通信](https://juejin.cn/post/6844903887162310669#heading-7)

应该要根据组件间关系来学

- 父子
- 兄弟
- 爷孙





#### 插槽

口诀：ts，用的时候用template，而定义的时候则是用slot

ref的对象元素某个元素或者是子组件实例

作用域插槽

- 能访问自身作用域数据的插槽



插槽的内容、出口：



获取插槽对象

- 在模板中：$slots
- 在script中：使用useSlots()，返回值才是slots





#### 过渡、动画

：雕虫小技，没那么重要，动画则是通过animate实现



#### 混入

：mixin使得我们能够为vue组件编写可插拔、可重用的功能

可插拔？

- 插上即实现功能，而移除也不会影响系统正常运行

则是在组件自身钩子调用前调用



#### 指令

：你需要对dom元素进行底层操作（比如聚焦）

[常用的自定义指令](https://juejin.cn/post/6963840401899782175#heading-1)、[2](https://github.com/Michael-lzg/v-directives)

- 权限校验指令
- 复制黏贴指令
- 输入框防抖指令

如何批量注册指令？

- 通过把多个指令定义在一个文件中，通过main来引入，然后遍历注册即可

```js
//方法1，通过forEach，这种是半自动的
import debounce from "./debounce";
const directives = {
  debounce,
};
export default {
  install(vm) {
    //   通过object方法来获取到所有的keys
    Object.keys(directives).forEach((key) => {
      vm.directive(key, directives[key]);
    });
  },
};

//方法2，通过require.context方法，全自动的，但是你需要在webpack环境下才行
```

[require.context](https://www.jianshu.com/p/c894ea00dfec)

- [批量注册组件](https://juejin.cn/post/6844903748712857613)

非main.js文件如何获取vue应用实例？

- 通过install方法，可以传入这个应用实例

js移除当前节点居然是这样操作的：先找到父节点，然后移除自己的子节点

- [js常见的节点操作](https://juejin.cn/post/6976087862689136670)

vue3在template中使用字符串需要在双引号里再加单引号

```text
<button v-permission="'user-delete'">用户删除按钮</button>
```



#### 响应式api 

什么是响应性？

：我觉得就是数据与其视图是否同步更新，为了保证变量做到响应性，所以要用响应式的api对其进行包装，得到响应性的对象（普通对象不是响应性的），后面你修改值就会有效果了

- 在template中会自动读取value，所以不用.value

值传递修改不会同步，而引用传值则是修改会同步

- 扩展运算符、解构不能随便用，它会导致属性失去响应性，除非你用上toRefs

为什么要组合api来替代选项api？

- 因为选项api的代码逻辑关注点（比如属性）太多了，**拆的太散**，可读性差，难以维护
  - 组合api则是对同一逻辑关注点进行了归类，可读性好，代码可维护了，哈哈

应用场景

- 代码逻辑比较复杂的组件

setup内部不要使用this

ref的重点是他的内部值，而reactive则是返回对象的响应式拷贝，reactive会解包所有深层的ref对象，而且保持响应式，响应式操作指（比如更新视图）

- 

事件总线的监听，监听，触发事件，这个事件（我想到的是叫声，哈哈，我所要做的是监听他的叫声，然后在它叫了之后做某些响应的动作）

vue3中on、emit方法被删了，所以用第三方库才行，

在template中的数据不是所有都要响应式的，因为有些数据是不会改的，比如name

**ref**

ref和reactive都是响应式转换都是深层的

- 推荐使用ref，ref方法是无敌的

**reactive**

：返回的就是proxy对象



vue2与vue3的不同

- 前者通过Object.defineProperty后者通过Proxy来实现响应式

有时候要加入immediate:true才会监听到

**watch**

watch中什么时候要用函数，什么时候直接用值就行？

- 监听响应式对象的时候可以直接用值，而监听普通值的时候则是要用函数

**watchEffect**



为什么watch直接写属性不能跟踪，而写方法就能响应式的跟踪

```js
// 直接student.age不行，相当于写死一个值，只能通过getter才行
watch(() => student.age, () =>  
console.log('age ' + student.age);
})
```





## hook

：能够复用（或者叫封装）逻辑

教程

- [浅谈：为啥vue和react都选择了Hooks🏂？ - 掘金 (juejin.cn)](https://juejin.cn/post/7066951709678895141)
- 

hook优点？

- 状态逻辑复用
  - 以前状态逻辑是跟组件耦合在一起的，没法复用
- 逻辑集中
  - 以前太分散了，分成好几块，需要不断的翻找
- 渐进式
- 可读性更强
  - 简化了this

vue中的组合式函数就是hook

- 它依赖于组合式api



## vueuse





## jsx

：没必要一定要往jsx靠，vue有自己的风格，就是模板

- https://juejin.cn/post/6846687590704381959
- 语法：https://juejin.cn/post/6996214286292877326
- 语法：https://juejin.cn/post/7029508496756310052

vue中如何引入jsx

- vite

  - 引入jsx插件，无需配置babel
  - 需要在script中配置lang=“jsx”

通过v-slots属性来指定引用插槽

- 而直接用

tsx中不能使用setup语法糖了

什么时候要用括号，我老是花括号用错地方，

- 有表达式的地方就要用花括号，而且是外层用，里层就不用了，比如{arr.length&&console.log('xxx')}





## 组件



#### 异步组件

普通组件可以通过路由懒加载得到异步组件，但是异步组件不一定要通过路由懒加载实现

- 

组件事件

：本质上是一种子组件向父组件通信的机制，是单向的





## 兼容

其实这个问题主要靠积累，让测试去验证，出了问题再说



## vue-router

：很多时候你不需要学那么深入

关注点

- 路由匹配
  - 动态路由
  - 嵌套路由
- 参数传递
- 路由组件
- 路由守卫





## pinia

持久化：[Pinia的使用以及数据持久化 - 掘金 (juejin.cn)](https://juejin.cn/post/7101657189428756516#heading-7)



## debug

定位

- 



异常处理



## 渲染机制





## 风格

风格不应该成为编码的负担，所以挑几个看即可，每多记一组就多个负担

- 变量、方法的规范

[前端代码规范（vue篇） - 掘金 (juejin.cn)](https://juejin.cn/post/7331714933388525580?searchId=202405161429156789AD1AEB243D1B3F8A#heading-30)

[前端命名规则与各个场景的命名方法，解决你取变量名的痛苦！！！（二） - 掘金 (juejin.cn)](https://juejin.cn/post/7016139493312823303?searchId=20240620160310BA82F5ACACFA9D683F95)

变量

- boolean：can,has,is,
  - 如isShow
- map：by，如usersByName

函数

- add,edit,remove,queryXXX
- open,close
- submit,reset
- 不要onxxxClick，我觉得这样太麻烦了，直接

下划线：前端中_一般作为特殊使用的下划线，一般使用中划线

- 比如常量中作为语义分隔(`MAX_VALUE`)，前置作为私有不能使用的变量(`__myprovite`)。



## 异常处理

#### 全局异常处理

- 采用vue的异常捕获：app.config.errorHandler
- 采用js的异常捕获：window.onError



## vueuse

：基于vue的工具库，vue2、3都可以用，能够大大提高开发效率





## SSR

关注点

- 路由
- 请求
- seo





## 问题

运行机制

- create初始化：初始化数据、监听器
- mount挂载：将组件实例挂在到指定的dom元素上，同时编译模板，生成虚拟dom
- 渲染：将虚拟dom渲染成真实dom
- update更新
- unMount卸载



渲染更新流程

- 依赖收集
  - 收集组件为响应式的依赖
- 响应式数据更新
- 组件更新：重新执行render函数，生成新的虚拟dom
- diff算法：比如新旧虚拟dom的差异
- 渲染：真实dom更新



应用实例&组件实例

- 应用实例
  - 通过createApp来创建的，一般在main文件里，一个vue应用一般只有一个vue实例
    - 获取：在main中可以直接获取app、其他可以通过函数传参的方式获取

- 应用实例
  - 获取：ref来获取、

- 相同点：都是vue实例
- 不同点：应用实例代表整个当前应用，组件实例只代表当前组件，能够调用的方法也是不同的



怎样修改已有类型，而且复用已有类型

- 

路由懒加载跟异步组件是有区别的

- 路由懒加载一定是用到了异步组件
- 异步组件则不一定是路由懒加载

动态组件&异步组件

- 动态组件一般都不是异步的
- 异步组件则可以是动态的，可以是静态的

legacy api：遗留api，也可以叫传统api

.vue文件可以被ts文件导入，也可以导出

组件我怎么知道谁套在外层，谁套在里层？

- 

为啥有时候要用属性绑定，而不是事件绑定

- 因为它就不是事件啊，

为啥vue在script内容里可以直接导入css文件？

- 这是vite支持的写法

