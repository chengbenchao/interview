##### 1、小程序子组件在父组件中注册

```
{
    "component": true,
    "usingComponents": {
       "componentB": "../child/child"
    }
}

```

##### 2、小程序page的生命周期

```
onLoad 				监听页面加载
onReady 			   监听页面初次渲染完成
onShow 				监听页面显示
onHide 				监听页面隐藏
onUnload 			  监听页面卸载
onPullDownRefresh	  监听用户下拉动作
onReachBottom		  页面上拉触底事件的处理函数
```

##### 3、微信小程序怎么在模板中对数据进行再处理

```
<wxs moudle="">

```

##### 4、小程序插槽怎么使用

```
<!--第一步：封装组件，components/music/index.wxml-->
<!--components/music/index.wxml-->
<view>
  <text>我是标准的</text>
  <!--下面是slot插槽（占位），用于承载组件引用时提供的子节点-->
  <slot name="name"></slot>
</view>

```

```
<!--第二步：引入组件，pages/index/index.wxml-->
<f-music></f-music>
<f-music>
<!-- 下面这部分内容将被放置在组件 <slot> 的位置上 -->
  <view slot="name">我是定制的内容</view>
</f-music>

```

##### 5、小程序中自定义属性获取值

```
function (e) {
	console.log(e.currentTarget.dataset.id) 
}
```

