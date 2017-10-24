<script src="https://cdn.bootcss.com/react/15.4.2/react.min.js"></script>
<script src="https://cdn.bootcss.com/react/15.4.2/react-dom.min.js"></script>
<script src="https://cdn.bootcss.com/babel-standalone/6.22.1/babel.min.js"></script>


* React 与 TypeScript 的区别
    * React 不是一个 MVC 框架,它是构建易于可重复调用的 WEB 组件,侧重于 UI ,也就是 view 层
    * React 是单向的从数据到视图的渲染,非双向数据绑定
    * 不直接操作 DOM 对象,而是通过 虚拟DOM 通过 diff 算法以最小的步骤作用到最真实的 DOM 上
    * 不便于直接操作 DOM ,大多数时间只是对 virtual DOM 进行编程
* 引入库的类型
    * react.min.js          React 的核心库
    * react-dom.min.js      提供与 DOM 相关的功能
    * babel.min.js          babel 可以将 ES6 代码转换为 ES5 代码，这样我们就能在目前不支持 ES6 的浏览器上执行 react 代码.Babel 内嵌了对 JSX 的支持.通过将 Babel 和 babel-sublime 包(package) 一同使用可以让源码的语法渲染上升到一个全新的水平.
* create-react-app 
    * create-react-app 是来自 Facebook ,通过该命令我们无需配置就能快速构建 react 开发环境
    * create-react-app 自动创建的项目是基于 webpack + ES5
*  创建项目
    * create-react-app  my-app(name)
    * cd my-app/
    * npm start
* 原生 HTML 元素名以小写字母开头,而自定义的 react 类名 以大写字母开头,比如:HelloMessage 不能写成 helloMessage
* 在添加属性时, class 属性需要写成 className ,for 属性需要写成 htmlFor , 这是因为 class 和 for 时 JS 的保留字