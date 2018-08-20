# Learn-Vue
Vue知识的持续学习和持续更新~~~
----
1. Vue基础知识思维导图 
2. vue-router  
3. vuex的原理  
4. 生命周期函数  beforeCreate、created、beforeMouted、Mounted、beforeUpdate、Updated、beforeDestroy、Destroyed
5. 生命周期内create和mounted的区别，二者分别能干什么   
created钩子函数在模板渲染成html前调用，此时视图中的html并没有渲染出来，DOM还未生成，此时如果直接去操作html的dom节点，一定找不到相关的元素  
Mounted钩子函数是编译、挂载完成，模板渲染成html后调用，此时可以对html的dom节点进行一些需要的操作。
#### 6. 单向数据流   
所有 props 都在子组件和父组件之间形成一个单向往下流动的数据绑定：当父组件中的属性更新时，数据就会向下流动到子组件，但是反过来，子组件属性更新时，父组件并不会感知到子组件的数据变化。这种机制可以防止子组件意外地修改了父组件的状态，造成应用程序的数据流动变得难于理解。
此外，每次父组件更新时，子组件中所有的 props 都会更新为最新值。也就是说，你不应该试图在子组件内部修改 prop。如果你这么做，Vue 就会在控制台给出警告。
诱使我们修改 prop 的原因，通常有两种：

prop 用于传递初始值(initial value)；之后子组件需要将 prop 转为一个局部数据属性。在这种情况中，最好定义一个局部的 data 属性，然后将 prop 的值，作为局部属性初始值。
````js
props: ['initialCounter'],
data: function () {
  return {
    counter: this.initialCounter
  }
}
````
prop 用于传递一个需要转换的未加工值(raw value)。在这种情况中，最好预先定义一个 computed 属性，然后在其函数内部引用 prop 的值：
``` js
props: ['size'],
computed: {
  normalizedSize: function () {
    return this.size.trim().toLowerCase()
  }
}
```
注意，JavaScript 中的对象和数组都是通过引用(reference)传递的，因此，如果 prop 是一个数组或对象，则在子组件内部改变对象或数组本身，仍然会影响到父组件状态。

