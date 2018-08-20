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
