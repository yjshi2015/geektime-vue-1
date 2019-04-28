# geektime-vue

## 安装依赖
```
npm install
```

### 启动环境
```
npm run serve
```

# 学习记录
- js为单线程执行，所以针对异步请求，哪个先到先处理哪个，不存在“同时”

- vue3大核心组件：属性 事件 插槽

- 计算属性computed和监听属性watch:
  - 推荐使用计算属性computed，但要求计算的属性为**响应式属性**
  
- props属性和data数据区别：props属性来自父组件都数据，data数据为自身状态数据

- data-->return中的数据为响应式数据

- model和sync的区别：model针对的是对象，sync针对单个属性  

- 插槽：插槽的存在是对父组件引用子组件的补充，父组件不仅引用了子组件，而且还向子组件传入了dom节点

- vue组件的生命周期：
    - template组件的生命周期类似与java中bean对象的生命周期，初始化--更新--销毁，当然每一个周期点是细拆分成多个节点的
    - 函数式组件(一段js函数)：无状态、无实例、没有this上下文、无生命周期，类似于java的静态方法
    
- vue路由，类似于javaweb的controller

- vue内置命令： v-show、v-if、v-for……

- router路由相关：
    - router的存在，使页面的模式变成了SPA(单页面)模式，避免了随着url的变化，页面重新加载的问题
    - router模式：
    - 1.Hash模式，在url中存在#符号，丑
    - 2.history模式，在url中避免了#符号，推荐
    - 使用方式：
    - 1.提供一个路由配置表，比如toutes.js，不同的burl对应不同组件的配置
    - 2.初始化路由实例 new VueRouter()
    - 3.挂载到Vue实例上
    - 4.提供一个路由占位符<router-view>，用来挂载URL匹配到的组件
    
- 提高效率的插件
    - vetur 快速生成vue页面，补充标签
    - ESlint 代码规范
    - prettier 格式化
    - vue-devtools 浏览器插件