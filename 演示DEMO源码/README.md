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

- 1.5 计算属性computed和监听属性watch:
  - 推荐使用计算属性computed，但要求计算的属性为**响应式属性**
  - computed属性偏向于缓存
  - watch属性偏向于监听
  
- props属性和data数据区别：props属性来自父组件都数据，data数据为自身状态数据
    - 父组件向子组件通过props属性传值，如果属性名称前有:冒号，则传的为表达式，无：冒号，则为常量
    - 引用类型都属性，比如对象或数组，在声明时必须使用工厂函数，防止多个组件实例共享一份数据
    - 见演示DEMO源码-\>src-\>views-\>1.1章节
- data-->return中的数据为响应式数据

- model和sync的区别：model针对的是对象，sync针对单个属性  

- 插槽：插槽的存在是对父组件引用子组件的补充，父组件不仅引用了子组件，而且还向子组件传入了dom节点

- 1.6 vue组件的生命周期：
    - template组件的生命周期类似与java中bean对象的生命周期，初始化--更新--销毁，当然每一个周期点是细拆分成多个节点的
    - 初始化阶段的顺序，create -\> render(渲染模板) -\> mounted(将数据挂载到dom节点上)
    - 初始化/销毁阶段都执行一次，更新阶段可以执行多次
    - 函数式组件(一段js函数)：无状态、无实例、没有this上下文、无生命周期，类似于java的静态方法
    
- vue路由，类似于javaweb的controller

- vue内置命令： v-show、v-if、v-for……

- 1.10 jsx是一种动态渲染模板的方式，通过render函数来渲染模板

- vuex本质上是提供了一个管理全局变量的方式，这里的变量，在任何一个组件中都可以用到。
  可以通过state/getters来取值，通过action/mutation赋值

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

- css样式（https://www.runoob.com/css）
    - 可以指定特定的HTML元素使用class。如下的样式会让所有的 p 元素使用 class="center" 让该元素的文本居中
      > p.center {text-align:center;}

    - 样式的优先级如下：
    (内联样式）Inline style \> （内部样式）Internal style sheet \>（外部样式）External style sheet \> 浏览器默认样式
    - 如果属性的样式在多个地方被定义，则最终也是按照如上优先级进行继承：相同的属性会被优先级高的覆盖，不同的属性则可以继承下来

    - css的盒子模型，由内向外 content(内容) \> padding(内边距) \> border(边框) \> margin(外边距)
    > 注意: "border-width" 属性 如果单独使用则不起作用。要先使用 "border-style" 属性来设置边框。
      边框设置的顺序，以border-style:dotted solid double dashed为例，即是上/右/下/左

    - 分组选择器：(有逗号分割)，即把不同元素分成一组，用同一套样式，类似于 p1,p2,h {样式}
      嵌套选择器：(无逗号分割)，即元素和class混合使用，类似于 .wrapperML input {样式}，
      或者.topmenu li a {样式}

    - 块级元素(block)特性：
      + 总是独占一行，表现为另起一行开始，而且其后的元素也必须另起一行显示;
      + 宽度(width)、高度(height)、内边距(padding)和外边距(margin)都可控制;
    - 内联元素(inline)特性：
      + 和相邻的内联元素在同一行;
      + 宽度(width)、高度(height)、内边距的top/bottom(padding-top/padding-bottom)和外边距的top/bottom(margin-top/margin-bottom)都不可改变，就是里面文字或图片的大小;
    - 块级元素主要有：
      + address , blockquote , center , dir , div , dl , fieldset , form , h1 , h2 , h3 , h4 , h5 , h6 , hr , isindex , menu , noframes , noscript , ol , p , pre , table , ul , li
    - 内联元素主要有：
      + a , abbr , acronym , b , bdo , big , br , cite , code , dfn , em , font , i , img , input , kbd , label , q , s , samp , select , small , span , strike , strong , sub , sup ,textarea , tt , u , var  

    - 元素的定位Position
      + relative 相对定位，是相对其默认的正常位置
      + fixed 定位，相对于浏览器窗口是固定位置，即使窗口滚动，它也不会移动
      + absolute 定位，绝对定位的元素的位置相对于最近的已定位父元素，如果没有已定位的父元素，那么是相对于<\html>，
      + sticky 定位，粘贴定位，即滚动到一定位置后位置就不再变化
      + z-index 重叠样式，类似于PS中图层的概念
      + overflow 滚动条，溢出后自动出现滚动条

    - 元素的浮动，float，类似于word的图片嵌入到文本中的效果
