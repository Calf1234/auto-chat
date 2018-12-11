# auto-chat

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

---

## 项目结构
### README.md: readme

### build: webpack的主要配置

### config: 工程的主要配置

### index.html: 启动的html

### node_modules: npm下载的文件

### package-lock.json: npm具体下载的依赖库文件

### package.json: npm配置文件

### src: 主要代码的文件夹

### static: 静态文件存放地点，默认在打包时不参与优化
**chatData.json**: 固定的聊天数据源

对chatData.json的配置，我们对话的消息分为”对方（left）“和”我（right）“两个部分，我们叫它leftMsg和rightMsg，也就是说每一次对话消息应该分为两个大部分lefgMsg和rightMsg。

在聊天的开始，”对方“先进行发言，然后”我“选择想要说的话，”对方“根据我选择的不同进行不同的回复，那么”对方“如何知道”我“的选择呢？我们可以给每一条消息指定一个id，使用这个id进行聊天数据的配比。

### test: 测试内容
