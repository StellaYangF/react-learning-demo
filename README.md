# React 基础篇

## 介绍

`react` 是一个 `JavaScript` 库，可构建用户界面，专注于视图，实现组件化开发

**库相关**
* `react.js` React 核心
* `react-dom.js` 提供与 **DOM** 相关功能，`render` 核心插入 DOM 元素。

**组件开发**

* 可重组
* 可复用
* 可维护

## 实践

### 搭建开发环境

```bash
npm i create-react-app -g
create-react-app react-learning
cd react-learning
yarn start
```

## JSX

### 什么是 JSX ？

* JS 和 HTML 混合语法
* 聚合 **组件结构**、**数据**、**样式** 进行组件定义
* 语法糖，通过 [bebel.js](https://babeljs.io/) 转译为 `createElement` 语法

### 什么是元素？

* 构成 React 应用最小单位
* 描述屏幕所见内容
* 普通 JS 对象，确保浏览器中 DOM 数据和 React 元素一致

等价代码

```jsx
<h1 className='title' style={{ color: 'pink' }}>hello</h1>
```

```js
React.createElement('h1', {
  className: 'title',
  style: {
    color: 'pink',
  }
}, 'hello');

// 结果
{
  type: 'h1',
  props: {
    className: 'title',
    style: {
      color: 'pink',
    }
  },
  children: 'hello'
}
```

### 书写形式

* 表达式 `{ 表达式逻辑 }`
* 属性 `className`
* 对象 `<ul>{ 数组元素 }</ul>`
* 更新元素渲染 `immutable`，元素创建后，无法改变内容或属性，更新界面唯一办法，创建新元素。
* 只更新已变化的内容

## 组件

### 组件规则

* 必须大写字母开头
* 返回值只能有一个根元素
* 使用必须定义或引用它

### 函数组件

接收 `props`  返回 React 元素

```js
function Header(props) {
  return <h1>Hello, { props.name }</h1>;
}
```

### 类组件

```js
class Header extends React.Component {
  render() {
    return <h1>Hello, { props.name }</h1>;
  }
}
```

### 复合组件 & 提取组件

* 细分小组件
* 抽象出可复用组件，如：Button, Avatart, Slider

## Props

### 只读性

* 类似纯函数，只做计算
* 不可修改传入的 Props

### 类型检查

* 配置特定 `propTypes` 属性
* `defaultProps` 定义默认 props 值

