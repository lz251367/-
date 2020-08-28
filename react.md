### react相关常识

* react父子组件的双向绑定，依靠的是通过props传入的函数方法，然后在子组件中调用父组件的方法，由父组件执行

* jsx组件标签中的所有值都会渲染到**props**中的 **children** 属性中

  #### 多层组件的传值

  * **context**
  
  #### 生命周期
  
  > **组件更新指: props 或者 state内部发生变化**
  >
  > 组件更新理解：在当前组件中，只要使用setState，不管是否对齐进行修改都会触发组件更新
  >
  > 在父组件传给子组件的props中，只要props改变，不管这个props是否被使用到，都会触发组件的更新，会有很大的性能问题
  
  * constructor()
  
    > 组件 **首次渲染 **至dom最先执行的生命周期，不是必须的
  
  * render()
  
    > 初始化，或者每次组件数据更新时都会调用此生命周期，必须的。当返回值为null或者布尔类型，则不渲染
  
  * componentDidMount()
  
    > 组件首次渲染至dom树 **后** 执行的生命周期
  
  * componentWillUnmount()
  
    > 组件从 DOM 中移除 **前** 执行的生命周期
  
  * shouldComponentUpdate()
  
    > 组件更新 **前** 触发，接收两个参数，`nextState`和`nextProps`，表示更新后的 `state`和`props`值
    >
    >  返回值为true 执行render  否则不执行，用于优化性能
  
  * componentDidUpdate()
  
    > 组件更新 **后** 执行的生命周期，接收两个参数， `prevProps`和`prevState`，表示更新前的 `state`和`props`值
  
  #### 高性能组件   PureComponent  memo
  
  * 内部对 shouldComponentUpdate() 做了封装集成，对state，props进行浅比较，
  * 浅比较会出现很多问题，对原本 **对象** 的修改是不会进行dom渲染的
  * 复杂组件不适用
  
  #### 局部样式 index.module.css
  
  * 将它当一个js文件引入   `import indexCss from "./index.module.css";`
  * 使用： `className={indexCss.header}`





### react常用组件

#### [react中文网](https://zh-hans.reactjs.org/)  [react脚手架](https://create-react-app.dev/docs/getting-started) [react路由](https://reactrouter.com/web/guides/quick-start) [redux](https://redux.js.org/basics/actions)



* prop-types   yarn add prop-types --dev  类型效验

  > color: PropTypes.string.isRequired  属性类型， 是否为空
  
* defaultProps  默认的props的值

  > 

* ref 

  > 需要通过react的api进行创建 再进行绑定  `this.inp = React.createRef();`  `ref={this.inp}`  
  >
  > 通过  `this.inp.current` 调用它的实例

* sass    `yarn add node-sass sass-loader`

#### 路由  react-route-dom

*  yarn add react-router-dom --dev 

  ```
  import { BrowserRouter as Router, Route, Link } from "react-router-dom";
  <Route path="/" exact component={Index} />
  <Link to="/about/">About</Link>
  <Switch>
  	<Route path="/" exact component={Index} />
  	<Redirect to="/404/" ></Redirect>
  </Switch>
  ```

  > exact 表示精确匹配
  >
  > BrowserRouter 使用传统的url模式   HashRouter  使用哈希路由的模式
  >
  > Link  用来跳转路由，类似于a标签
  >
  > Route  用来承载路由
  >
  > Redirect  路由重定向
  >
  > Switch  用 Switch  包住的路由 只会匹配一个  类似于  if() {}else if() {} else if() {} 不用其包住的类似于  if() {}  if() {} 会全部匹配

  

  * props.history.push(/users/${id}/)    路由跳转
  * const { id } = this.props.match.params;   获取路由参数



### 仓库  react-redux

* yarn add redux react-redux --dev

