# auto-chat 项目回顾
记录些项目中**Vue 2.5**框架使用到的知识点。

项目地址：<a href="https://github.com/Calf1234/auto-chat" target="_blank">https://github.com/Calf1234/auto-chat</a>

---

## 基础知识
1. 声明式渲染 -> {{}}
2. 列表渲染 -> v-for
3. 属性绑定 -> v-bind
4. 事件处理 -> v-on

---

## Vue的生命周期
<img src="https://cn.vuejs.org/images/lifecycle.png" alt="生命周期图示"></img>

这里更改到的生命周期钩子函数是created。这个阶段实例已经创建完成，data、prop和watch都已经配置ok，但是还没有挂载到dom内去。

auto-chat项目中的聊天数据都是固定的，所以在created钩子函数中先把这个数据都加载进来。这样在项目运行过程中，无论是对方要发言的内容，亦或是我要说的话，都能够从这个加载的数据中直接过滤帅选出来。

---

## Vue中常用的API
. filter
* nextTick

当我们的 DOM 进行渲染的时候，nextTick 为 DOM 渲染之后的回调方法。比如：当我们从服务器获取了一段数据，然后把这些数据进行了渲染到 DOM 上，如果有一些方法需要在 DOM 渲染完成之后执行，那么就可以监听 nextTick 来获取重新渲染之后的 DOM。

使用场景：现在有一个p标签，这个标签用来承载一段描述信息，我们需要获取到p展示了描述信息之后的高度，那么就可以通过 nextTick 来实现这个需求。

---

## 组件
1. <a href="#component-register">组件注册的方式</a>
2. <a href="#component-params">组件之间的传参</a>
3. <a href="#component-events">组件之间的事件传递</a>

<a id="component-register" style="text-decoration: none">
<h3>组件注册的方式</h3>
</a><br>
组件（Component）的注册方式有两种，第一种为全局注册：

~~~ js
Vue.component('my-component-name', { /* ... */ })
~~~

第二种为局部注册：

~~~ js
var ComponentA = { /* ... */ }

new Vue({
  el: '#app'
  components: {
    'component-a': ComponentA
  }
})
~~~

<a id="component-params"  style="text-decoration: none">
<h3>组件之间的传参</h3>
</a><br>
通过 Prop 向子组件传递数据。

所有的 prop 都使得其父子 prop 之间形成了一个单向下行绑定：父级 prop 的更新会向下流动到子组件中，但是反过来则不行。

如果需要对 Prop 进行改变的话，那么有两种方式：

第一种为，接受 Prop 作为 data 选项的初始值，然后修改 data 的值，这也是比较常用的一种方式。

~~~ js
props: ['initialCounter'],
data: function () {
  return {
    counter: this.initialCounter
  }
}
~~~

第二种为，使用计算属性 computed 来对 Prop 进行转换，这种方式多用于对 Prop 进行二次转换的情况下。

~~~ js
props: ['size'],
computed: {
  normalizedSize: function () {
    return this.size.trim().toLowerCase()
  }
}
~~~

**注意在 JavaScript 中对象和数组是通过引用传入的，所以对于一个数组或对象类型的 prop 来说，在子组件中改变这个对象或数组本身将会影响到父组件的状态。**

<a id="component-events"  style="text-decoration: none">
<h3>组件之间的事件传递</h3>
</a><br>
组件之间的事件传递多是通过 $emit 和 $on 来进行的。

---

## 路由： vue-router
<a href="https://router.vuejs.org/zh/">Vue Router 2</a>

---

## 状态管理：Vuex
<a href="https://vuex.vuejs.org/zh/guide/">Vuex 2.0</a>

---

## 网络请求：Axios
<a href="https://github.com/axios/axios">axios</a>是一个基于 Promise 的 Http 客户端，并且可以用于浏览器和 node.js

---