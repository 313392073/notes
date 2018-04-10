## react-router

### v4
1. 动态路由。它不是一个配置或app外部的一个资源，它是组件，这意味着可以在组件使用的地方使用它。
2. 主要有三种组件：路由器组件（一般指BrowserRouter和HashRouter），路由匹配组件(Route/Switch)，导航组件
3. 路由匹配组件匹配上就会渲染组件，没有匹配上渲染null，如果不带路径将会匹配所有
4. 路由匹配组件可以放在任何你想根据路径渲染组件地方
5. Switch 组件用来盛放Route组件，它会渲染跟路径匹配的第一个组件。也可以在最后放一个404组件，在所有路由都不匹配的时候显示。
6. Route有三个属性，component（常用，传入组件即可。不可传入函数式组件，否则会有重复挂载的问题） render（传入无状态的函数式组件） children
7. Link组件用于创建链接，每渲染一个Link组件，就会在html中生成一个a标签
8. NavLink 是一个特殊的Link组件，在当前路径匹配‘to’属性时，将应用‘activeClassName’属性的值到a标签的class属性上
9. 当你想强制重定向到某个路径时你需要Redirect组件。这会强制导航到它的‘to’属性值指定的路径。
#### 嵌套路由

#### 响应式路由
比如根据屏幕大小动态调整路由


#### BrowserRouter
- basename 正确写法是加上前边的斜杠而不需要后边的斜杠

#### NavLink
- exact 严格匹配，但是不考虑结尾的斜杠
- strict 值为true 的时候在判断是否匹配当前路径时将考虑结尾的斜杠。仅仅是考虑斜杠，需要带斜杠的严格匹配时还需要加上exact。
- isActive 自定义的判断是否是匹配路径的逻辑
- location 可选的传入isActive方法的参数，可作为判断是否匹配的路径的比较对对象


#### Redirect
导航到一个新的路径，新的路径会在历史堆栈中覆盖当前路径信息，就像后端重定向一样。

#### Route
路由中最基础的组件，提供了在路由匹配是渲染UI的功能。在没有匹配路径也会渲染组件，只是组件被渲染为null。

匹配路径后渲染组件，组件props将获得match/location/history属性

- component 属性只能接受组件，不能接受行内组件。如果使用行内组件将导致每次路由匹配都会生成新的组件，并导致mount 和 unmount.
- render 在路由匹配时执行接收的函数得到ui。render和component都会获得同样的props
- component 优先级高于render，不应该在同一个Route中同时使用二者。
- children 类似于render，差异在于children的函数会接收一个match 参数，在路由没有匹配时match值为null。
这个特性可以让你在判断到路由没有匹配时做跟多的操作。比如可以显示动画，动画在匹配或没有匹配都要显示，将match
的判断放在动画逻辑后边即可：
```
<Route children={({ match, ...rest }) => (
  {/* Animate will always render, so you can use lifecycles
      to animate its child in and out */}
  <Animate>
    {match && <Something {...rest}/>}
  </Animate>
)}/>
```
children 的优先级低于component 和 render，三者只能使用其一。

-location 路由匹配默认匹配
