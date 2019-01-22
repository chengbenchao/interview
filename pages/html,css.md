>#### **李姚组**

##### 1.html标签的分类(李姚)
~~~
块标签
//p,h1~h6
内联标签
//a,span,i,em,strong
内联块
//input,button,img
~~~

##### 2.css的继承(汪娟)
- CSS样式表继承指的是，特定的CSS属性向下传递到子孙元素。
  - 文本相关属性：`font-size`,`font-style`,`color`...
  - 列表相关属性：`line-height`,`list-style`...
  - 特殊`font-size`：`font-size`的子类继承的不是实际值，而是计算后的值。

```html
<p>
字体大小属性<em>继承特性</em>的演示代码
</p>
```

```css
p { font-size:80%}
```

如果font-size继承的是相对值，依照这样的逻辑，em的font-size为80％X80％=64%。

但，实际情况却不是如此。em内的文字并没有改变大小，而是和p保持一致。

##### 3.如何实现一个元素的垂直水平居中

- 第一种方法:定位加上margin

```css
div.box{
weight:200px;
height:400px;
<!--把元素变成定位元素-->
position:absolute;
<!--设置元素的定位位置，距离上、左都为50%-->
left:50%;
top:50%;
<!--设置元素的左外边距、上外边距为宽高的负1/2-->

margin-left:-100px;
margin-top:-200px;
}
```

> 兼容性好;缺点:必须知道元素的宽高

- 第二种方法：定位加上transform

```css
div.box{
weight:200px;
height:400px;
<!--把元素变成定位元素-->
position:absolute;
<!--设置元素的定位位置，距离上、左都为50%-->
left:50%;
top:50%;
<!--设置元素的相对于自身的偏移度为负50%(也就是元素自身尺寸的一半)-->
transform:translate(-50%,-50%);
}
```

> 这是css3里的样式;缺点:兼容性不好，只支持IE9+的浏览器

- 第三种方法:定位加上margin：auto

```css
div.box{
weight:200px;
height:400px;
<!--把元素变成定位元素-->
position:absolute;
<!--设置元素的定位位置，距离上、下、左、右都为0-->
left:0;
right:0;
top:0;
bottom:0;
<!--设置元素的margin样式值为 auto-->
margin:auto;
}
```

> 兼容性较好，缺点:不支持IE7以下的浏览器

- 第四种方法：改变子元素为行内块元素

> 场景： 一个块状元素A内 有若干个块状元素B，要达到的效果是 ，所有块状元素B 在 元素A 内水平居中显示。

```css
<div class="A">
　　<div class="B"></div>
　　<div class="B"></div>
　　<div class="B"></div>
</div>
```

> 首先，我们要设置元素A的大小为500px，设置背景色为green方便查看

```css
.A｛
　　width:500px;
　　backgrond-color:green;
｝
```

> 然后， 设置所有元素B 的宽度为100px，高度为100px，外边据都为5px，背景色为#000方便查看

```css
.B｛
　　width:100px;
　　height:100px;
　　magin:5PX;
　　backgrond-color:green;
｝
```

> 我们要做的就是，先把所有元素B设置为行内块元素,让他们都排成一行， display:inline-block；
> 最后就是给父容器加一个text-align:center的样式。

- 第五种方法：flex布局

> 给父元素样式：

```
.parent{
    justify-content: center;
    align-items: center;
}
```

- 第六种方法：grid布局

> 给父元素样式：

```
.parent{
    justify-items: center;
    align-items: center;
}
```

> 第七种方法：table布局

```
.parent{
     display: table-cell;
     vertical-align: middle;
     text-align: center;
}
```

##### 4.display:none和visibility:hidden之前有什么区别 (李许怡安)

##### 5.position哪些值可以设置,z-index的权重(肖茗君)

##### 6.before:和before::有什么区别

##### 7.为什么要进行样式重置(汪娟)

##### 8.tranform有哪些属性

##### 9.display有哪些值

##### 10.对web标准,及对w3c的规范的理解

>#### **童建设组**

##### 1.css选择器有哪些

##### 2.盒子模型(王宇)

##### 3.flex布局

##### 4.grid布局

##### 5.常用的布局方法有哪些

##### 6.简述一下对html语义化的理解

##### 7.如何解决img,在div中的间隙问题

##### 8.浏览器如何渲染页面

##### 9.如何实现一个圆形

##### 10.box-shadow的传参

>#### **徐保山组**

##### 1.清除float的几种方式

##### 2.link和@import的区别

##### 3.说一下bootstrap的栅格布局

##### 4.css的优先级别

##### 5.说一下用过的css预处理器

##### 6.如何实现css3的动画

##### 7.form表单中action属性的作用

##### 8.前端页面分成那三层,分别是什么?