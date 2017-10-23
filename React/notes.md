* React 不是一个 MVC 框架,它是构建易于可重复调用的 WEB 组件,侧重于 UI ,也就是 view 层
* React 是单向的从数据到视图的渲染,非双向数据绑定
* 不直接操作 DOM 对象,而是通过 虚拟DOM 通过 diff 算法以最小的步骤作用到最真实的 DOM 上
* 不便于直接操作 DOM ,大多数时间只是对 virtual DOM 进行编程