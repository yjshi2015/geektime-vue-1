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
- vue3大核心组件：属性 事件 插槽

- 计算属性computed和监听属性watch:
  - 推荐使用计算属性computed，但要求计算的属性为**响应式属性**
  
- props属性和data数据区别：props属性来自父组件都数据，data数据为自身状态数据

- data-->return中的数据为响应式数据

- model和sync的区别：model针对的是对象，sync针对单个属性  

- vue组件的生命周期：
    - template组件的生命周期类似与java中bean对象的生命周期，初始化--更新--销毁，当然每一个周期点是细拆分成多个节点的
    - 函数式组件(一段js函数)：无状态、无实例、没有this上下文、无生命周期，类似于java的静态方法
    
- vue路由，类似于javaweb的controller

- vue内置命令： v-show、v-if、v-for……