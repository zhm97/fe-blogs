

教程

- 指南：https://juejin.cn/post/6867861517603438605
- https://juejin.cn/post/7268533072995598347?searchId=20230927174330002E22CDAE5ACD179673



## 驱动问题

啥是工程化？工程化需要做什么？

：前端开发是指前端开发过程中采用一系列工具、方法，以提高开发效率、代码质量和团队协作能力的方法，工程化做的事都是围绕这3个主题

- 自动化构建
- CI、CD
- 文档生成：api、用户文档
- 质量检查：如eslint
- 测试相关：单元、集成测试
- 容器化：如docker
- 版本控制





#### vue-router

- npm i vue-router
- 

#### pinia

#### windicss

- 安装vite-plugin-windicss，windicss
- vite中注册
- main引入css：import 'virtual:windi.css'

#### mock

- npm i mockjs -D
- npm i vite-plugin-mock -D
- vite中注册插件

#### element-plus

- npm install element-plus
- main中注册
  - 导入样式：import 'element-plus/dist/index.css'
  - 注册elementPlus

#### axios

- npm i axios
- 在api下创建http文件，编写请求方法get、post、拦截方法

#### [postcss-px-to-viewport](https://juejin.cn/post/7018433228591595550)

- npm install postcss-px-to-viewport -D
- 修改配置文件：postcss.config.js

#### [editorConfig](https://editorconfig.org/)

:他能够帮你不同IDE下的代码样式问题，

- 创建.editorConfig

```json
# EditorConfig is awesome: https://EditorConfig.org

# top-most EditorConfig file
root = true

[*]                   # 表示所有文件都要遵循
indent_style = space              # 缩进风格，可选配置有space和tab
indent_size = 2                   # 缩进大小
end_of_line = lf                  # 换行符，可选配置有lf、cr和crlf
charset = utf-8                   # 编码格式，通常都是选utf-8
trim_trailing_whitespace = true   # 去除多余的空格
insert_final_newline = true       # 在尾部插入一行

[*.md]                # 表示仅 md 文件适用
insert_final_newline = false      # 在尾部插入一行
trim_trailing_whitespace = false  # 去除多余的空格
```



## 问题
