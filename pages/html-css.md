##### 1、web标准和w3c规范理解

```
标签字母要小写
标签要闭合
标签不允许随意嵌套
尽量使用外链css样式表和js脚本，结构、表现和行为层分离
```

##### 2、css选择器有哪些

```
元素选择器：p{color:pink}
类选择器：.test{color:yellow}
id选择器：#app{color:red}
属性选择器：a[href][title] {color:red;}
分组选择器：p,h4{background:gray}
子元素选择器：div>span{color:red}
兄弟选择器：div+p{color:red}
后代选择器：h1 em {color:red;}
伪类选择器： div:hover{} input:focus{}
伪元素：h1:before{content:url(logo.gif)}
```

##### 3、选择器优先级

```
内联 > ID选择器 > 类选择器 > 标签选择器
!important 优先级最高,可覆盖行内样式.不可以添加到行内样式属性中.
```

##### 4、图片在div中间隙问题如何解决

```
1、给 div{
  font-size：0;
}
2、或者给img{
  vertical-aline：bottom;
} 
```

##### 5、img中alt的作用

```
假设由于下列原因用户无法查看图像，alt属性可以为图像提供替代的内容：
网速太慢
src 属性中的错误
浏览器禁用图像
用户使用的是屏幕阅读器
```

##### 6、display : none和 visibility : hidden的区别

```
1、display:none;会让元素完全从渲染树中消失，渲染的时候不占据任何空间； visibility: hidden;不会让元素从渲染树消失，渲染师元素继续占据空间，只是内容不可见
2、display: none;是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示； 	visibility: hidden;是继承属性，子孙节点消失由于继承了hidden，通过设置visibility: visible;可以让子孙节点显示
```

##### 7、图片报403的处理

```
将<meta name="referrer" content="no-referrer" />添加到html文档里
```

##### 8、背景如何铺满全屏

```
给
.bg{
    position：fiexd;
	top:0;
	left:0;
	right:0;
	buttom:0
}
```

##### 9、元素垂直水平居中的方法

```
1、定位加上margin	（知道元素宽高）
2、定位加上transform
3、定位加上margin：auto（上下左右设为0）
4、flex布局
5、grid布局
6、改变子元素为行内块元素
7、table布局
```

##### 10、清除浮动方法

```
1、给下面的兄弟元素给clear:both;
2、给父级加overflow:hidden;   /*主要是这个 
3、为父元素设置固定高度
3、用伪元素,给父级内容生成
.row:before{
 display:table; 
 content:"" 
}
.row:after{
 display:table;
 content:""
 clear:both;
}
```

##### 11、标签分类

- 块标签  display:block

```
特点: 1.独占一行 2.能够设置width,height
div,h1~h6,p,ul,li,dl,dt,dd
```

- 内联标签  display:inline

```
特点: 1.并排显示 2.不能设置width,height 3.不能设置margin-top,margin-bottom
a,span,em, i，strong
```

- 内联块标签  display:inline-block

```
特点 1.并排显示 2.可以设置宽高  
button,img,input
```

##### 12、H5中语义化的标签有哪些

```
header、nav、footer、aside、article、section
```

##### 13、css样式覆盖规则

```
1、由于继承而发生样式冲突时，最近父级获胜。
2、继承的样式和直接指定的样式冲突时，直接指定的样式获胜。
3、直接指定的样式发生冲突时，样式权值高者获胜。
4、样式权值相同时，后者获胜。
5、!important的样式属性不被覆盖。
```

##### 14、元素的margin和padding设置为百分比会受谁的影响

```
会受最近块级父元素大小的影响
```

##### 15、阻止a标签默认行为

```
(1) <a href="##" class="demo" ></a>
(2) <a href="javascript:void(0);" class="demo" ></a>
 	<a href="javascript:;" class="demo" ></a>

```

##### 16、link和@import

```
1、link属于html标签，而@import是css提供的。
2、页面被加载时，link会同时被加载，而@import引用的css会等到页面加载结束后加载。
3、link是html标签，因此没有兼容性，而@import只有IE5以上才能识别。
4、link方式样式的权重高于@import。
```

##### 17、伪类和伪元素

```
伪类其实是弥补了CSS选择器的不足，用来更方便地获取信息。
:link :hover :first-child ...
而伪元素本质上是创建了一个虚拟容器(元素)，我们可以在其中添加内容或样式
::before  ::after
```

##### 18、transfrom有哪些属性

```
位移 translate	旋转 rotate	缩放 scale(x,y)	倾斜 skew(x,y)
```

##### 19、为什么要样式重置

```
为了兼容性考虑,每个浏览器默认样式不一样,比如行高,某个浏览器是1,另外一个浏览器可能是1.1,再有一个浏览器
可能就是0.9,这样在开发网页写样式表的时候,处理起来比较麻烦,所以直接给重置统一,这样就能很方便的处理兼容
性。
```

##### 20、css有哪些样式不能继承

```
display \ margin \ border \ padding \ background \ height \ float 
```

##### 21、合并表格边框

```
table {
    border-collapse: collapse;
}
```

##### 22、a标签四种状态

```
a:link 		{color:#FF0000;}		未被访问的链接 
a:visited 	{color:#00FF00;} 		已被访问的链接 
a:hover 	{color:#FF00FF;}		鼠标指针移动到链接上
a:active 	{color:#0000FF;} 		正在被点击的链接 
```

##### 23、说一下盒子模型

```
Margin(外边距) - 清除边框外的区域，外边距是透明的。
Border(边框) - 围绕在内边距和内容外的边框。
Padding(内边距) - 清除内容周围的区域，内边距是透明的。
Content(内容) - 盒子的内容，显示文本和图像。
```

##### 24、box-sizing两个属性区别  border-box  content-box

```
content-box:宽度和高度分别应用到元素的内容框,在宽度和高度之外绘制元素的内边距和边框。
border-box :为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制,通过从已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。
```

##### 25、什么是响应式设计   基本原理

```
内容布局能随用户使用显示器的不同而变化
基本原理：媒体查询
```

##### 26、如何实现盒子圆角阴影效果

```
border-radius : 50%
box-shadow : offsetX水平平移 offsetY垂直平移 blur模糊 size大小 color颜色;
```

##### 27、前端页面分为哪三层

```
结构  表现  行为
```

##### 28、图片有哪几种格式

```
jpg / png / gif / svg / tif
```

##### 29、input中type有哪几个属性

```
传统的10种：
text        定义单行文本输入框
password    定义密码输入框
file        定义文件上传控件
radio       定义单选按钮
checkbox    定义复选框
hidden      定义隐藏的输入字段
button      定义按钮
image       定义图像形式的提交按钮
reset       定义重置按钮,重置按钮会清除表单中的所有数据
submit      定义提交按钮,提交按钮会把表单数据发送到服务器
h5新增13种：
color    定义调色板
tel      定义包含电话号码的输入域
email    定义包含email地址的输入域
url      定义包含URL地址的输入域
search   定义搜索域
number   定义包含数值的输入域
range    定义包含一定范围内数字值的输入域
date     定义选取日、月、年的输入域 
month    定义选取月、年的输入域
week     定义选取周、年的输入域
time     定义选取月、年的输入域
datetime 定义选取时间、日 月、年的输入域(UTC时间)
datetime-local 定义选取时间、日 月、年的输入域(本地时间)

```

##### 30、怎么固定背景图片

```
position:fiexd

```

##### 31、h5中获取用户当前位置

```
getCurrentPosition 

```

##### 32、栅格系统

```
类前缀
col-xs		<768px
col-sm		≥768px
col-md		≥992px
col-lg		≥1200px

```
##### 33、html5有什么新特性？移除了哪些元素？如何处理htm5新标签的浏览器兼容性问题？如何区分HTML和html5?

html5新特性：

```css
用于绘画canvas元素
用于媒介回访的video  和 audio 元素
本地离线存储localStrorage 长期存储数据，浏览器关闭后的数据不丢失；sessionStorage在页面关闭之后自动删除
语义化更好的内容元素，article，footer,header,nav,section
表单控件，calender,date,time,email,url,search
H5的新增接口：地理定位接口、网络访问的接口、读文件的接口、拖拽接口
```

移除的标签：

```css
<basefont> 默认字体，不设置字体，以此渲染
<font> 字体标签
<center> 水平居中
<u> 下划线
<big> 大字体
<strike> 中横线
<tt> 文本等宽
<font> 字体标签
<s> 删除线标签
```

新标签的兼容问题：

```css
//方法一：
//1、使用静态资源的html5shi包
<!--[if lt IE9]>
<script src="http://cdn.static.runoob.com/libs/html5shiv/3.7/html5shiv.min.js"></script>
<![endif]-->

//2、载入之后，初始化新标签的css(解决IE8及以下浏览器下h5新增标签不是块级元素的问题)
header, section, footer, aside, nav, main, article, figure { display: block; }

//方法二
IE6/IE7/IE8支持通过document方法产生的标签，利用这一特性让这些浏览器支持HTML5新标签
```

区分html5 于html

```css
1、在文档类型声明上区别
   HTML声明：
  <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "<http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd>">
　　<html xmlns="<http://www.w3.org/1999/xhtml>">
　　
　HTML5声明：<!doctype html>

2、在结构语义上区分
	HTML：<div id="header"></div>

	HTML5：在语义上却有很大的优势，提供了一些新的HTML5标签比如: article、footer、header、nav、section，这些通俗易懂
```
##### 34、iframe 有哪些优缺点？

```css
iframe的优点：
1.iframe能够原封不动的把嵌入的网页展现出来，iframe和主页面是并行加载的
2.如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。
3.网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。
4.如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。

iframe的缺点：
1.会产生很多页面，不容易管理。
2.iframe框架结构有时会让人感到迷惑，如果框架个数多的话，可能会出现上下、左右滚动条，会分散访问者的注意力，用户体验度差。
3.代码复杂，无法被一些搜索引擎索引到，这一点很关键，现在的搜索引擎爬虫还不能很好的处理iframe中的内容，所以使用iframe会不利于搜索引擎优化。
4.很多的移动设备（PDA 手机）无法完全显示框架，设备兼容性差。
5.iframe框架页面会增加服务器的http请求，对于大型网站是不可取的。 分析了这么多，现在基本上都是用Ajax来代替iframe，所以iframe已经渐渐的退出了前端开发。
6.iframe会堵塞主页面的onload事件
```