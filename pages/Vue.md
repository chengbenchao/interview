##### 1、vue动画原理

```
在进入/离开的过渡中，会有 6 个 class 切换。

v-enter：定义进入过渡的开始状态。在元素被插入之前生效，在元素被插入之后的下一帧移除。

v-enter-active：定义进入过渡生效时的状态。在整个进入过渡的阶段中应用，在元素被插入之前生效，在过渡/动画完成之后移除。这个类可以被用来定义进入过渡的过程时间，延迟和曲线函数。

v-enter-to: 2.1.8版及以上 定义进入过渡的结束状态。在元素被插入之后下一帧生效 (与此同时 v-enter 被移除)，在过渡/动画完成之后移除。

v-leave: 定义离开过渡的开始状态。在离开过渡被触发时立刻生效，下一帧被移除。

v-leave-active：定义离开过渡生效时的状态。在整个离开过渡的阶段中应用，在离开过渡被触发时立刻生效，在过渡/动画完成之后移除。这个类可以被用来定义离开过渡的过程时间，延迟和曲线函数。

v-leave-to: 2.1.8版及以上 定义离开过渡的结束状态。在离开过渡被触发之后下一帧生效 (与此同时 v-leave 被删除)，在过渡/动画完成之后移除。
```

![img](https://i.loli.net/2020/01/07/hi9kVAmf2BNeUzR.png) 

##### 2、keep-alive的作用

```
当<keep-alive>包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们。<keep-alive>是一个抽象组件，它
自身不会渲染一个DOM元素，也不会出现在父组件链中。
当<keep-alive>内切换组件时，它的activated和deactivated这两个生命周期钩子函数将会执行。
```

##### 3、vue中v-if、v-show的区别

```
v-show与v-if都是条件渲染指令。不同的是，无论v-show的值为true或false，元素都会存在于HTML页面中；而只
有当v-if的值为true时，元素才会存在于HTML页面中。v-show指令是通过修改元素的style属性值实现的。
```

##### 4、vue中页面返回怎么写

```
this.$router.back()
this.$router.go(-1) 

```

##### 5、vue中导入本地图片

```
url:require ("image")

```

##### 6、vuex的工作流

![img](https://cdn.nlark.com/yuque/0/2019/png/457370/1574166967535-ff0895d8-f947-4299-b47a-6124f89c0906.png)

```
1.在组件中，用一个this.$store.dispath这个方法触发actions提交修改数据的操作 
2.Actions用commit来触发	mutations来修改数据 
3.mutations接收到commit的请求，就会自动通过Mutate来修改state里面的数据，也只有Mutations可以操作
  state中的状态数据，状态一改变，组件中就重新渲染 
4.最后由store触发每一个调用它的组件更新

```

##### 7、vue中route和router的区别

```
$route为当前router跳转对象 里面可以获取name、path、query、params等
$router为VueRouter的实例，相当于一个全局的路由器对象，里面含有很多属性和子对象，例如history对象 经常
用的跳转链接就可以用this.$router.push，和router-link跳转一样。。。 
```

##### 8、vue移动端适配

```
引入lib-flexible     pxtorem

```

##### 9、vue中计算属性和watch区别

```
computed :一个数据根据你所依赖的数据动态显示新的计算结果 
watch:当依赖的数据改变时做一些事情(执行watch内部的回调函数)

```

##### 10、vue详情中如何获取get传值、动态路由

```
get传值:this.$route.query 
动态路由：this.$route.params 

```

##### 11、vue路由中history和hash的区别

```
hash:仅 hash 符号(#)之前的内容会被包含在请求中,#之后的地址改变是不会请求后端服务，不会出现404错误 
history:前端的 URL 必须和实际向后端发起请求的 URL 一致 

```

##### 12、vue中如何实现图片懒加载

```
先将所有img标签的src链接设为同一张图片(默认图片)，当js监听到该图片进入可视窗口时，再将实际地址应用。

```

##### 13、组件中properties和data的区别

```
properties ：使用组件时外部可以传参数的，也就是调用者可以外部修改该属性 
data：初始值，不能修改 

```

##### 14、router-link标签点击时改变颜色的class

```
linkActiveClass 

```

##### 15、vue中如何实现自定义组件

```
引入import firstComponent from './component/firstComponent.vue' 
注册 在标签内的data代码块后面加上components：{firstComponent}

```

##### 16、vue中如何实现全局过滤器和局部过滤器

```
局部：单个vue页面中的<script>中的filters：{}中
全局：Vue.filter("name"，function(key){ })   main.js中写

```
##### 17、vue路由拦截器(路由守卫),一般用来干什么
https://zhuanlan.zhihu.com/p/59889754

https://www.jianshu.com/p/691379025334
```
路由守卫：主要就是全局守卫、路由独享守卫、局部守卫
  1、全局守卫：是指路由实例上直接操作的钩子函数，特点是所有路由配置的组件都会触发，直白点就是触发路由就会
              触发这些钩子函数
    router.beforeEach((to,from,next)=>{})
    回调函数中的参数，to：进入到哪个路由去，from：从哪个路由离开，next：函数，决定是否展示你要看到的
    路由页面
  2、路由独享守卫：是指在单个路由配置的时候也可以设置的钩子函数
    beforeEnter:(to,from,next)=>{}
  3、局部守卫：是指在组件内执行的钩子函数，类似于组件内的生命周期，相当于为配置路由的组件添加的生命周期钩
              子函数
    beforeRouteEnter:(to,from,next)=>{}

其他的自己照着网址细品
```
