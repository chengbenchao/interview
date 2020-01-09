##### 1、Vue生命周期

```
beforeCreate()   //组件创建之前
created() 		 //组件被创建,还没有装载在DOM上,不能操作DOM
beforeMount() 	 //组件装载之前,
mounted() 		 //挂载到真实的DOM节点上,可以操作DOM
beforeUpdate() 	 //数据被更新之前
updated() 		 //数据更新后,一般用watch来替换,update只有页面依赖的data的数据更新才会触发
beforeDestroy()	 //销毁组件前
destroyed() 	//销毁组件
```

##### 2、React生命周期

```
React生命周期分为三大周期，11个阶段，调用顺序如下。
（1）在创建的五大阶段，调用方法顺序如下
• getDefaultProps：定义默认属性数据
• getInitialState：初始化默认状态数据
• componentWillMount：组件即将被创建
• render：渲染组件
• componentDidMount：组件构建完成,在这个生命周期里进行http请求
（2）在存在（运行）期的五大阶段，调用方法的顺序如下。
• componentWillReceiveProps：组件即将被接收新的属性数据
• shouldComponentUpdate：判断组件是否应该被更新
• componentWillUpdate：组件即将被更新
• render：渲染组件，当state,props的状态更新时,就会触发
• componentDidUpdate：组件更新完成
（3）在销毁期的一个阶段，调用方法componentWillUnmount,表示组件即将被销毁。
```

![img](https://i.loli.net/2020/01/07/kC3vTo9yl6pBVjM.png) 

##### 3、Angular生命周期

当 Angular 使用构造函数新建一个组件或指令后，就会按下面的顺序在特定时刻调用这些生命周期钩子方法：

| 钩子                                                         | 用途及时机                                                   |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `ngOnChanges()`//有父子组件传值,先触发这个方法。没有就先触发ngOnInit() | 当 Angular（重新）设置数据绑定输入属性时响应。 该方法接受当前和上一属性值的 `SimpleChanges` 对象在 `ngOnInit()` 之前以及所绑定的一个或多个输入属性的值发生变化时都会调用。 |
| `ngOnInit()`                                                 | 在 Angular 第一次显示数据绑定和设置指令/组件的输入属性之后，初始化指令/组件。在第一轮 `ngOnChanges()` 完成之后调用，只调用**一次**。 |
| `ngDoCheck()`//可以做一些自定义的操作                        | 检测，并在发生 Angular 无法或不愿意自己检测的变化时作出反应。在每个变更检测周期中，紧跟在 `ngOnChanges()` 和 `ngOnInit()` 后面调用。 |
| `ngAfterContentInit()`//组件渲染完成后触发                   | 当 Angular 把外部内容投影进组件/指令的视图之后调用。第一次 `ngDoCheck()` 之后调用，只调用一次。 |
| `ngAfterContentChecked()`                                    | 每当 Angular 完成被投影组件内容的变更检测之后调用。`ngAfterContentInit()` 和每次 `ngDoCheck()` 之后调用 |
| `ngAfterViewInit()`//视图加载                                | 当 Angular 初始化完组件视图及其子视图之后调用。第一次 `ngAfterContentChecked()` 之后调用，只调用一次。 |
| `ngAfterViewChecked()`                                       | 每当 Angular 做完组件视图和子视图的变更检测之后调用。`ngAfterViewInit()` 和每次 `ngAfterContentChecked()` 之后调用。 |
| `ngOnDestroy()`                                              | 每当 Angular 每次销毁指令/组件之前调用并清扫。 在这儿反订阅可观察对象和分离事件处理器，以防内存泄漏。在 Angular 销毁指令/组件之前调用。 |

```
//重点关注
constructor

ngInit

ngAfterViewInit

ngOnDestory
```

```
//数据改变时以下三个生命周期函数会执行
ngDoCheck()

ngAfterContentChecked()

ngAfterViewChecked()

```

##### 4、Android生命周期

```
- onCreate    活动第一次创建时候调用
- onStart     活动由可见到不可见时候触发
- onResume    活动处于栈的顶部会触发
- onPause     活动处于暂停状态时候触发
- onStop      活动不可见的时候触发
- onDestroy   活动被销毁的时候触发
- onRestart   活动从暂停变为运行状态的时候触发
```

##### 5、小程序生命周期

```
onLoad()	监听页面加载
onReady()	监听页面初次渲染完成
onShow()	监听页面显示
onHide()	监听页面隐藏
onUnload()	监听页面卸载
```

##### 6、初次加载、A-B、B-A哪些生命周期触发

```
Android：
	初次加载：onCreate()	 onStart()	onResume()
	A-B:	onPause()	 onStop()	
	B-A:	onRestart()	 onStart()	onResume()
```

```
Vue:
	初次加载：beforeCreate、created、beforeMount、mounted
	A-B：beforeDestroy()	 destroyed() 	
	B-A：beforeCreate、created、beforeMount、mounted
```

```
react:
	初次加载：constructor -> componentWillMount -> render -> componentDidMount
	数据更新时触发：componentDidUpdate()	render()
	将要被卸载时触发：componentWillUnmount()
```

```
angular:
	初次加载时触发:	  constructor()  ngOnInit()
	父子组件传参时触发:	 constructor()   ngOnChange()	ngOnInit()
	视图加载:     		 ngAfterViewInit()
	销毁时触发: 			ngOnDestroy()
```

```
小程序：
	初次加载：onLoad()	onReady()	onShow()
	A-B：	onHide()
	B-A:	onShow()
```

##### 7、Vue、React、Angular、Android、小程序中如何获取DOM

```
Vue:
	通过给元素绑定ref=“XXX”，然后通过this.$refs.XXX或者this.refs['XXX']来获取
React:
	1、react原生函数findDOMNode获取dom
	2、通过ref来定位一个组件，切记ref要全局唯一
Angular：
	通过ViewChild装饰器获取
Android：
	通过id获取
	Button btn = (Button) findViewById(R.id.send_http);
小程序：
	1、 obj.in(component)	多用于组件的选择器
	2、 obj.select(selector)	selector是css选择器
	3、 obj.selectAll(selector)
```

##### 8、vue和react的区别

```
react:
1 函数式思想，all in js ,jsx语法，js操控css
2 单项数据流
3 setState重新渲染
4 每当应用的状态被改变时，全部子组件都会重新渲染。当然，这可以通过shouldComponentUpdate这个生命周期方法来进行控制，如果为true继续渲染、false不渲染，但Vue将此视为默认的优化。

vue:
1 响应式思想，也就是基于数据可变的。把html、js、css、组合到一起，也可以通过标签引擎组合到一个页面中
2 双向绑定，每一个属性都需要建立watch监听（页面不用，涉及到组件更新的话需要）
3 Vue宣称可以更快地计算出Virtual DOM的差异，这是由于它在渲染过程中，会跟踪每一个组件的依赖关系，不需要重新渲染整个组件树
```

##### 9、get传值、动态路由区别

```
git传值：传的值使用问号拼接在路由后
动态路由：传的值直接跟在路由后
```

##### 10、插槽slot的作用

```
用来传递内容的，但我们不能通过属性传递带标签的内容，所以就需要插槽。其实质是对子组件的扩展，通过slot插
槽向组件内部指定位置传递内容，即将<slot></slot>元素作为承载分发内容的出口

```

##### 11、各框架父子组件传参

```
Vue:
	父传子：父组件通过props向下传递数据给子组件
        1、子组件通过属性接收父组件传递的参数	<home-table :data="arr"></home-table>
        2、子组件接收的参数需要在props属性中注册
        props: {
            data: {
                type: Array
                }
            }
  	子传父：子组件通过this.$emit("methodName",data),父组件定义同名方法即可。
        1、使用$emit方式自定义事件，向父组件传参
        <button @click="handleDelete(index)">删除</button>
        handleDelete(index){
          this.$emit("deleteItem",index)
        }
        2、父组件接收子组件传递过来的事件参数
        <home-table :data="arr" @deleteItem="handleDelete"></home-table>
        handleDelete(index){
          console.log(index)
        }
```

```
React:
	父传子：父组件通过props向下传递数据给子组件
        1、子组件通过属性接收父组件传递的参数		
        <Title msg="hello world"></Title>
        2、从props中接收参数
        <h1>{this.props.msg}</h1>
	子传父：同vue
		1、子组件向父组件自定义方法传参
		<h1 onClick={this.handleClick.bind(this,"1355")}>{this.props.msg}</h1>
		handleClick=(id)=>{
        	console.log(id)
        	this.props.deleteItem(id)
    	}
    	2、父组件自定义方法接收子组件传的参数
		<Title	deleteItem = {this.handleDelete.bind(this)}	msg={this.state.msg}></Title>
```

```
Angular:
	父传子：
		1、在父组件中定义一个参数
		2、在父组件中，子组件自定义属性接收传递的参数
		<app-item *ngFor="let item of movies" [data]="item"></app-item>
		2、子组件中引入Input模块
		3、@Input注册传过来的参数
		@Input() data:any
	子传父：
		1、在父组件中定义一个方法
		<app-header  [run]="run"></app-header>
		2、在子组件中获取方法
		@Input() run:any
		3、子组件通过事件传递参数给父组件
		handleClick(){
    		this.run("1234")
  		}
  		4、父组件接收子组件传过来的参数
  		run(id:string){
    		console.log(id)
  		}
```

```
小程序：
	父传子：
		1、在父组件中，子组件自定义属性接收传递的参数
		<v-item wx:for="{{songs}}" data="{{item}}" index="{{index}}"></v-item>
		2、在子组件properties属性中注册传递过来的参数
	子传父：
		1、在子组件中定义一个事件
		handleClick(){
    		var id=this.properties.itemId;
    		var index = this.properties.index;
    		this.triggerEvent("toggle",{id,index})
   		}
   		2、在父组件中接收事件
   		<v-item	 bind:toggle="handleToggle"></v-item>
```
##### 12、配置子路由、重定向
```
子路由
	 vue:
    	{
    		children:[
          		{
            		path:"morning",
            		component:MorningComponent
          		},
				]
        }
    react:
    <Switch>
            <Route path="/about/morning">
            <Morning/>
            </Route>
    </Switch>
    angular:
    	{
    		children:[
          		{
            		path:"morning",
            		component:()=>import('路径)      
				},]
    	}

重定向
	vue:
    	{
    		path: '/',redirect: '/home',
    	}
    
    react: 
		<Redirect from="/about" to="/about/morning"></Redirect>
    
    angular:
     	{
            path:"",//不能写斜杠
            redirectTo:"morning",
            pathMatch:"full"
        }
    
```
