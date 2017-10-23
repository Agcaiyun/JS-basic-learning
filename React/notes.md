* React 与 TypeScript 的区别
    * React 不是一个 MVC 框架,它是构建易于可重复调用的 WEB 组件,侧重于 UI ,也就是 view 层
    * React 是单向的从数据到视图的渲染,非双向数据绑定
    * 不直接操作 DOM 对象,而是通过 虚拟DOM 通过 diff 算法以最小的步骤作用到最真实的 DOM 上
    * 不便于直接操作 DOM ,大多数时间只是对 virtual DOM 进行编程
* 引入库的类型
    * react.min.js          React 的核心库
    * react-dom.min.js      提供与 DOM 相关的功能
    * babel.min.js          babel 可以将 ES6 代码转换为 ES5 代码，这样我们就能在目前不支持 ES6 的浏览器上执行 react 代码.Babel 内嵌了对 JSX 的支持.通过将 Babel 和 babel-sublime 包(package) 一同使用可以让源码的语法渲染上升到一个全新的水平.