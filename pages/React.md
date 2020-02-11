##### 1、react中实现双向数据绑定

```
给输入框添加onChange事件 
编写事件代码 （改变绑定的值 this.setState）

```

##### 2、react点击事件传参

```
onClick={this.handleClick.bind(this, props0, props1, ...}

```

##### 3、redux的应用场景、工作流

```
应用场景：
1. 所有页面都要用的公共信息 ；
2. 一个页面又多个ajax ；
3. 不同组件之间期望不用通过组件代码通信
```
工作流：
   https://img2018.cnblogs.com/blog/1087883/201812/1087883-20181205145741397-1912744867.png

##### 4、在react中如何避免样式重叠

```
1、安装styled-components
2、创建一个样式组件
3、引入使用
```

##### 5、react和react-native之间的区别

```
1、标签：react-native不使用HTML来渲染App，但是提供了可代替它的类似组件
2、导航：react-native拥有自己的导航系统
3、react-native是基于react的移动端开发框架

```

##### 6、react-native引入网络图片

```
//网络图片
<Image source={{uri:"xxx"}}>
//Tips:图片相关的资源一定要加样式width,height
```

##### 7、react-native获取屏幕宽高

```
引入Dimensions
import { Dimensions } from 'react-native';
const { width, height,scale} =Dimensions.get('window');

```
##### 8、你对React生命周期函数的理解

React 16.3+ 之后的生命周期函数：

- **getDerivedStateFromProps:** 在调用`render()`之前调用(props或者state改变的时候回调用)，并在 *每次* 渲染时调用。 需要使用派生状态的情况是很罕见得。

- **componentDidMount:** 首次渲染后调用，所有得 Ajax 请求、DOM 或状态更新、设置事件监听器都应该在此处发生。

- **shouldComponentUpdate:** 确定组件是否应该更新。 默认情况下，它返回`true`。 如果你确定在更新状态或属性后不需要渲染组件，则可以返回`false`值。 它是一个提高性能的好地方，因为它允许你在组件接收新属性时阻止重新渲染。

- **getSnapshotBeforeUpdate:** 在最新的渲染输出提交给 DOM 前将会立即调用，这对于从 DOM 捕获信息（比如：滚动位置）很有用。

- **componentDidUpdate:** 它主要用于更新 DOM 以响应 prop 或 state 更改。 如果`shouldComponentUpdate()`返回`false`，则不会触发。

- **componentWillUnmount** 当一个组件被从 DOM 中移除时，该方法被调用，取消网络请求或者移除与该组件相关的事件监听程序等应该在这里进行。

React 16.3之前的生命周期函数：

- **componentWillMount:** 在组件`render()`前执行，用于根组件中的应用程序级别配置。应该避免在该方法中引入任何的副作用或订阅。

- **componentDidMount:** 首次渲染后调用，所有得 Ajax 请求、DOM 或状态更新、设置事件监听器都应该在此处发生。

- **componentWillReceiveProps:** 在组件接收到新属性前调用，若你需要更新状态响应属性改变（例如，重置它），你可能需对比`this.props`和`nextProps`并在该方法中使用`this.setState()`处理状态改变。

- **shouldComponentUpdate:** 确定组件是否应该更新。 默认情况下，它返回`true`。 如果你确定在更新状态或属性后不需要渲染组件，则可以返回`false`值。 它是一个提高性能的好地方，因为它允许你在组件接收新属性时阻止重新渲染。

- **componentWillUpdate:** 当`shouldComponentUpdate`返回`true`后重新渲染组件之前执行，注意你不能在这调用`this.setState()`

- **componentDidUpdate:** 它主要用于更新 DOM 以响应 prop 或 state 更改。 如果`shouldComponentUpdate()`返回`false`，则不会触发。

- **componentWillUnmount:** 当一个组件被从 DOM 中移除时，该方法被调用，取消网络请求或者移除与该组件相关的事件监听程序等应该在这里进行。

其中下面三个方法在React16.3之后被从生命周期钩子函数中移除了。

- `componentWillMount()`
- `componentWillReceiveProps()`
- `componentWillUpdate()`

## 3.说明Redux更新的方法都有什么

Redux是SPA单页面应用程序中多个组件之间共享数据的一种方式。

Redux强调三个基本原则：

- 唯一数据源 ：唯一数据源指的是应用的状态数据应该只存储在唯一的一个Store上。
- 保持状态只读 ： 保持状态只读，就是说不能去直接修改状态，要修改Store的状态，必须要通过派发一个action对象完成。
- 数据改变只能通过纯函数完成 ：这里所说的纯函数就是把Reducer，Reducer描述了state状态如何修改。


```javascript
# 全局安装
npm install -g create-react-app
# 构建一个my-app的项目
npx create-react-app my-app
cd my-app
# 安装redux
npm install redux --save

#1.main.js
import React from 'react'                        // 创建组件、虚拟DOM元素，生命周期
import ReactDOM from 'react-dom'      // 把创建好的 组件 和 虚拟DOM 放到页面上展示的
import { createStore } from 'redux'

import App from "./app.jsx"

/**
 * 1.创建reducer
    这是一个 reducer，形式为 (state, action) => state 的纯函数.。描述了 action 如何把 state 转变成下一个 state。
    state 的形式取决于你，可以是基本类型、数组、对象、甚至是 Immutable.js 生成的数据结构。惟一的要点是当 state 变化时需要返回全新的对象，而不是修改传入的参数。
 */
function counter(state = 0, action) {
    switch (action.type) {
        case 'ADD':
            return state + 1
        case 'MINUS':
            return state - 1
        default:
            return state
    }
}

//2.声明 actions
//action 是改变 state 的唯一途径，是一个普通的 javascript 对象，它描述了一个行为且是改变 state 的唯一途径。从用户UI操作事件、网络请求回调和 WebSocket 等其他地方获得的数据，最终都会通过 dispatch 函数调用一个 action，从而改变对应的数据。action 必须带有 type 指明具体的行为名称，且能附带上额外的信息。
function addFn() {
    return { type:'ADD' }
}
function minusFn() {
    return { type:'MINUS' }
}

// 3.创建 Redux store 来存放应用的状态。store对象的API 有 { subscribe, dispatch, getState }。
let store = createStore(counter)


// 4.订阅更新，监听state的变化
store.subscribe(() => console.log(store.getState()))

// 5.触发action
store.dispatch(addFn())  // 1
store.dispatch(addFn())  // 2
store.dispatch(minusFn())  // 1


// 6.渲染页面
function render() {
    ReactDOM.render(<App store={store} addFn={addFn} minusFn={minusFn}/>, document.getElementById('app'));
}
render()
// 每当state状态发生变化的时候，重新渲染页面
store.subscribe(render)
    
    
#2.app.jsx
import React, { Component } from 'react';

class App extends Component {
    constructor(props){
        super(props)
    }
    render() {
        const store=this.props.store
        const addFn=this.props.addFn
        const minusFn=this.props.minusFn
        const init=store.getState()
        return (
            <div className="App">
                <h1>你好吗？</h1>
                {<p>现在的总数是：{store.getState()}</p>}
                {<button onClick={ ()=>store.dispatch( addFn() ) }>加1</button>}
                {<button onClick={ ()=>store.dispatch( minusFn() ) }>减1</button>}
            </div>
        );
    }
}
export default App;
```
