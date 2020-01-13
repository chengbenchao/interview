##### 1、数组的方法

```
增加：
    unshift() //从数组的前面增加
    push() // 从数组的最后面增加一个值,可以一次性添加多个
    splice(index,0,parmas) // 从index的前面增加 
    concat() //拼接两个数组,但是不能改变原数组的结构
删除：
    shift() //从前面删除
    pop() //从后面删除
    splice(index,howmany)  //index从哪个下标开始,howmany删除多少个
查询：
	indexOf()  
    includes() -->判断数组是否包含某个值
    slice()
    find() -->找不到就返回undefind
    findIndex()
修改：
 	splice()
遍历：	
    for in
    map()
    forEach()
    every()
    some()
    from()
    filter()
    
截取:
	slice()
将数组拼接成字符串：
	join()
排序：
	sort()	
求和：
	reduce()
反转：
	reverse()
求最值：
    Math.min(...arr)
    Math.max(...arr)

```

##### 2、JS哪几种情况输出false

```
NaN，""，null，undefined，0

```

##### 3、jQuery ajax传参

```
url:"",
type:"get",
data:,
success:,
error:

```

##### 4、break、continue区别

```
break:结束整个循环；
continue：跳过某次循环；
```

##### 5、关于声明提前

```
javaScript在执行代码的时候会将所有的var声明的变量，放在作用域的顶部集中创建,赋值留在原地

```

##### 6、==和===的区别

```
== 比较时会先进行类型转换，然后比较转换值; 比如：2 == '2' // true
=== 不会进行类型转换，先比较类型，然后比较值，若类型不相同则直接false；2 === '2' // false
```

##### 7、JS中常用事件

```
鼠标事件：
    onClick(鼠标单击)，ondbclick(鼠标双击)，
    onmousedown(鼠标按下未抬起)，onmouseup(鼠标抬起)，
    onmousemove(鼠标移动)，onmouseover(鼠标移入)，onmouseout(鼠标移出)，
    onmouseenter(鼠标移入)，onmouseleave(鼠标移出)
    onmouseover与onmouseenter的区别：前者若有子级元素，它会把事件传递给子级元素,而后者不会。
键盘事件：
    onkeydown(键盘按下，键盘未抬起事件会一直触发)
    onkeyup(键盘抬起)
    onkeypress(键盘按下数字键货子母键触发，功能键除外(上下左右，ctrl，shift，alt))
焦点事件：
    onfocus(有焦点的元素获取到焦点时触发，用tab键也会触发这个事件)
    onblur(有焦点的元素失去焦点时触发)
```

##### 8、call、apply和bind的区别

```
call和apply改变了函数的this上下文后便执行该函数,而bind则是返回改变了上下文后的一个函数;
call,apply的区别：
他们俩之间的差别在于参数的区别，call和apply的第一个参数都是要改变上下文的对象，而call从第二个参数开始以参数列表的形式展现，apply则是把除了改变上下文对象的参数放在一个数组里面作为它的第二个参数

```

##### 9、同步和异步

```
同步：客户端向服务器发送请求的过程中，用户不可以进行其他操作 
异步：客户端向服务器发送请求的过程中，用户可以进行其他操作

```

##### 11、什么是同源策略

```
同源策略：具有相同的协议(http/https)、域名、端口号为同源；

```

##### 12、什么是跨域、如何解决跨域

```
跨域：协议(http/https)、域名、端口号只要有一个不一样就是跨域；
解决跨域：
    跨域资源共享（CORS）---需后端处理；
    服务器转发代理---请求同源地址的代理接口，服务器访问跨域接口并返回数据；
    jsonp---利用script标签不受同源策略的限制特征，在src内写入请求地址，末尾回调处理数据：
    <script type="text/javascript" src="http://localhost/Service.ashx?callback=jsonpCallback" />

```

##### 13、什么是回调函数

```
把函数作为一个参数，传递给另外一个函数

```

##### 14、重载和重写

```
重载是指不同的函数使用相同的函数名，这些同名函数的形式参数（指参数的个数、类型或者顺序）必须不同，也就
是说用同一个函数完成不同的功能
覆盖（也叫重写）是指在派生类中重新对基类中的虚函数（注意是虚函数）重新实现。即函数名和参数都一样，只是
函数的实现体不一样

```

##### 15、事件冒泡、捕获 	阻止事件冒泡

```
事件冒泡：事件开始时由最具体的元素接收，然后逐级向上传播到较为不具体的节点。
事件捕获：是指不太具体的元素更早地接收到事件，然后向下传播到最具体的节点；也就是与冒泡过程相反。
阻止事件冒泡：event.stoppropagation()阻止事件冒泡

```

##### 16、什么是ajax

```
AJAX 是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术

```

##### 17、es6新特性

```
不一样的变量声明：const和let;
模板字符串;
箭头函数;
函数的参数默认值;
Spread / Rest 操作符;
二进制和八进制字面量;
对象和数组解构;
Set和Map
```

##### 18、js中将浮点数转化为整数的方法

```
parseInt;
Math.floor() Math.ceil() Math.round()
```

##### 19、js获取可视区域的width、height

```
document.documentElement.clientWidth
document.documentElement.clientHeight

```

##### 20、BOM的方法

```
window.prompt("请输入你的年龄")		可提示用户进行输入的对话框
window.alter()						提示弹框
window.confirm()					  用于显示一个带有指定消息和确认及取消按钮的对话框
```

##### 21、设置定时器、清除定时器

```
setTimeout
clearTimeout
```

##### 22、es5和es6中实现一个类

```
ES5:
function Person(name) {
    this.name = name; 
}
Person.prototype.sayHello = function(){
    return 'Hi, I am ' + this.name;
}
```

```
ES6:
class Person {
    constructor(name){
        this.name = name;
    }
    sayHello(){
        return 'Hi, I am ' + this.name;
    } 
}

```

##### 23、获取JSON对象所有的key和value

```
var json = {"name" : "Tom", "age" : 18};
for (var key in json) {
    console.log(key);     //获取key值
    console.log(json[key]); //获取对应的value值
}
```

##### 24、识别数组的方法

```
//一共有四种方法，最后一种容易忽视
isArray()
instanceof()
  判断被检测对象是否为构造函数的实例；
  原理：左侧被检测对象的原型链上是否包含右侧构造函数的prototype属性
  let arr = [1, 2, 3]
  arr instanceof Array // true
constructor
  返回对象的构造函数，数组对象的构造函数为Array
  let arr = [1, 2, 3]
  arr.constructor === Array // true
  arr.constructor // ƒ Array() { [native code] }
Object.prototype.toString.call()
  let arr = [1,2,3]
  Object.prototype.toString.call(a) //[object Array]
```

##### 25、find和filter区别

```
find 和 filter 都是不改变原数组的方法
find只查出第一个符合条件的结果,这个结果是一个对象,而filter返回全部结果仍然是数组

```

##### 26、字符串中有哪些方法支持正则

```
search()
match()
replace()
split()

```

##### 27、基本类型和引用类型的区别

```
基本数据类型：
  值不可变；
  不可以添加属性和方法；
  赋值是简单赋值；
  比较是值的比较；
  存放在栈区；
引用数据类型：
  值是可以改变的；
  可以添加属性和方法；
  赋值是对象引用；
  比较是引用的比较；
  同时保存在栈区和堆区中；
```

##### 28、如何执行事件监听

```
addEventListener() 
```

##### 29、css自适应的单位

```
百分比：%
相对视口宽度：vw
相对视口高度：vh
相对视口宽度或高度（取决于哪个小）：vm
相对于父元素字体大小的单位：em
相对于根元素字体大小的单位：rem
```

##### 30、js中浅拷贝和深拷贝

```
浅拷贝：创建一个新对象，这个对象有着原始对象属性值的一份精准拷贝。如果属性是基本类型，拷贝的就是基本类型的值，如果属性是引用类型，拷贝的就是内存地址，如果其中一个对象改变了这个地址，就会影响到原对象。
浅拷贝方法：
1.浅拷贝对象（解构）
var obj = {
    "name": 'xu',
    "age": 23
}
var test = {...obj};

2.浅拷贝数组（slice和concat）
let newArr1 = arr.slice();
let newArr2 = arr.concat();

3.Object.assign
let newObj = Object.assign({},obj);   //浅拷贝obj对象
let newArr = Object.assign([],arr);   //浅拷贝数组

深拷贝：将一个对象从内存中完整地拷贝一份出来，且改变新对象内的引用类型，不会影响到原对象内的数据
深拷贝的方法：
let newObj = JSON.parse(JSON.stringify(obj));
```


##### 32、二叉树

```
常见的二叉树有
满二叉树：除叶子结点外,所有结点都有两个结点,叶子结点的left,right为NULL.
哈夫曼树：又称为最优二叉数，是一种带权路径最短的树。
完全二叉树:除了最底层的叶子结点之外,其余层全满,而且叶子层集中在左端.堆是一种特殊的完全二叉树。

```

##### 33、正则中匹配以数字开头

```
/^\d+/
```

##### 34、cookie、localStorage、sessionStorage的区别

```
1.数据存储方式：
• cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）
• cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递
• sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存
2、存储大小：
• cookie数据大小不能超过4k
• sessionStorage和localStorage虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大
3、有期时间：
• localStorage 存储持久数据，浏览器关闭后数据不丢失除非主动删除数据
• sessionStorage 数据在当前浏览器窗口关闭后自动删除
• cookie 设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭

```

##### 35、let、const 以及 var 的区别是什么？

```
let 和 const 定义的变量不会出现变量提升，而 var 定义的变量会提升。
let 和 const 是JS中的块级作用域
let 和 const 不允许重复声明(会抛出错误)
let 和 const 定义的变量在定义语句之前，如果使用会抛出错误(形成了暂时性死区)，而 var 不会。
const 声明一个只读的常量。一旦声明，常量的值就不能改变(如果声明是一个对象，那么不能改变的是对象的引用地址)

```

##### 36、字符串常用方法

```
1. indexOf()        返回某个指定的子字符串在字符串中第一次出现的位置
2. slice(a,b)       返回字符串中提取的子字符串。
3. substring(a,b)   提取字符串中介于两个指定下标之间的字符。
4. substr(i,len)    返回从指定下标开始指定长度的的子字符串
5. split()          把字符串分割成字符串数组。
6. replace(a,"b")   在字符串中用一些字符替换另一些字符
7. match()          返回所有查找的关键字内容的数组。

```

##### 37、promise有哪两种状态

```
resolve 成功触发
reject  失败触发

```

##### 39、px和rem区别

```
px 固定长度单位，不能适应响应式页面
rem 相对于根元素<html>的font-size而定，适应响应式页面

```

##### 40、事件代理和事件委托

```
事件委托:事件委托，又称为事件代理，是JavaScript中绑定事件的常用技巧。顾名思义，事件代理就是把原本需要
绑定的事件委托给父元素，让父元素负责事件监听。事件代理的原理是DOM元素的事件冒泡。使用事件代理的好处是
减少事件数量，提高性能。

```

##### 41、js中有哪些内置对象

```
1. Arguments
2. Array
3. Boolean
4. Error
5. Function
6. Math
7. Number
8. Object 
9. String
10. RegExp(正则表达式对象)

```

##### 42、什么是中间件、有哪些中间件

```
中间件: 是一种独立的系统软件或服务程序，分布式应用软件借助这种软件在不同的技术之间共享资源。
常见的中间件： Tomcat Node Express

```

##### 43、es6中导出模块几种方式

```
export
export default

```

##### 44、key值的作用

```
用于管理可复用的元素。尽可能高效地渲染元素，前端框架通常会复用已有元素而不是从头开始渲染。
简单的解释就是，key给每一个元素提供了唯一的类似id的属性，依靠这个key可以更快速更准确的对比新旧虚拟DOM
提高性能。

```

##### 45、不支持冒泡的事件

```
UI事件 
load
unload
scroll
resize

焦点事件 
blur
focus

鼠标事件 
mouseleave
mouseenter

```

##### 46、原生ajax如何实现

```
var url = "https://www.easy-mock.com/mock/5d67436324fd60626abfe910/ajax/base"
var xhr = new XMLHttpRequest();
xhr.open('get',url,true)   //true：异步处理
xhr.send()
xhr.onreadystatechange = function(){
    if(xhr.readyState == 4 && xhr.status == 200){
        var res = JSON.parse(xhr.responseText);   //json格式的字符串转换为json对象
        var name = document.getElementById("name");
        name.innerHTML = res.data.name;
    }
}

```

##### 48、判断数组是否包含某个值

```
indexOf() 此方法判断数组中是否存在某个值，如果存在返回数组元素的下标，否则返回-1
includes() 此方法判断数组中是否存在某个值，如果存在返回 true，否则返回false。
find()  返回数组中满足条件的第一个元素的值，如果没有，返回undefined
findIndex() 返回数组中满足条件的第一个元素的索引（下标）, 如果没有找到，返回-1

```

##### 49、url由那几个部分构成

```
一个完整的URL包括：协议部分、域名部分、端口部分、虚拟目录部分、文件名部分、参数部分、锚部分.
```

##### 50、前++和后++区别

```
i++是先赋值，然后再自增；++i是先自增，后赋值。
```

##### 51、eslint报错

```
webpack.base.config.js中注释掉
rules: [
	//...(config.dev.useEslint ? [createLintingRule()] : []),
]

```

##### 52、无状态组件和有状态组件区别

```
有状态组件拥有生命周期这些函数，无状态组件没有生命周期的函数,无状态组件性能更高。

```

##### 53、doctype的作用、标准与兼容的区别

```
1.<!DOCTYPE> 声明位于位于HTML文档中的第一行，处于 <html> 标签之前。告知浏览器的解析器用什么文档标准
解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。
2.标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方
式显示,模拟老式浏览器的行为以防止站点无法工作。
```

##### 54、箭头函数和普通函数的区别

```
普通函数的this 指向调用它的那个对象
箭头函数不能作为构造函数，不能使用new，箭头函数的this永远指向其上下文的 this
```

##### 55、闭包

```
使用闭包主要是为了设计私有的方法和变量。闭包的优点是可以避免全局变量的污染；缺点是闭包会常驻内存，增加
内存的使用量，使用不当很容易造成内存泄漏。在JavaScript中，函数即闭包，只有函数才会产生作用域。
闭包有3个特性：
（1）函数嵌套函数
（2）在函数内部可以引用外部的参数和变量
（3）参数和变量不会被垃圾回收机制回收
```

##### 56、对mvvm的理解

```
Model-View-ViewModel即模型-视图-视图模型。
【模型】指的是后端传递的数据。
【视图】指的是所看到的页面。
【视图模型】mvvm模式的核心，它是连接view和model的桥梁。

```

##### 57、原型和原型链

```
原型
• 在JavaScript中，每当定义一个函数数据类型(普通函数、类)时候，都会天生自带一个prototype属性，这个属
性指向函数的原型对象，并且这个属性是一个对象数据类型的值。
• 每一个对象数据类型(普通的对象、实例、prototype......)也天生自带一个属性__proto__，属性值是当前实
例所属类的原型(prototype)。原型对象中有一个属性constructor, 它指向函数对象。

原型链
• 在JavaScript中万物都是对象，对象和对象之间也有关系，并不是孤立存在的。对象之间的继承关系，在
JavaScript中是通过prototype对象指向父类对象，直到指向Object对象为止，这样就形成了一个原型指向的链条，
专业术语称之为原型链。
• Object是JS中所有对象数据类型的基类(最顶层的类)在Object.prototype上没有proto这个属性。

```

##### 58、Java和JavaScript区别

```
1.Java是强类型语言，JS是弱类型语言
2.Java变量在使用之前必须声明，而JavaScript不需要
3.Java面向对象的编程语言，JS基于对象和事件驱动的脚本语言
4.java主要在服务端运行，javascript主要运行在客户端浏览器中
5.Java的源代码在执行之前必须经过编译，而JavaScript可以由浏览器直接解释执行。

```

##### 59、js中有如何实现重载

```
function overload () {
  if (arguments.length === 1) {
    console.log('一个参数')
  }
  if (arguments.length === 2) {
    console.log('两个参数')
  }
}

```

##### 60、search的返回值

```
search() 方法用于检索字符串中指定的子字符串，返回第一个匹配的位置,如果没有找到任何匹配的子串，
则返回 -1。

```

##### 61、函数的参数默认赋值

```
这是es6的新特性
在es6之前，往往这样定义参数的默认值，在函数内声明。
function printText(text) {
    text = text || ;
    console.log(text);
}
在es6之后可以直接在声明形参的时候给予默认值
function printText(text = 'default') {
    console.log(text);
}

```

##### 62、常用DOM节点

```
1.元素节点 元素节点element对应网页的HTML标签元素
2.属性节点  元素节点（HTML标签）的属性，如 id 、class 、name 等
3.文本节点  素节点或属性节点中的文本内容。
4.注释节点  表示文档注释，形式为<!-- comment text -->。
5.文档节点  表示整个文档（DOM 树的根节点，即 document ）

```

##### 63、typeof能识别数组吗

```
不能， 在参数为数组，对象或者null时，typeof返回的结果都是object
识别数组可以用
Array.isArray()
变量.constract===array
变量 instanceof Array
变量.Object.prototype.toString.call( )
Object.prototype.toString.call(a);//"[object Array]"
Object.prototype.toString.call(b);//"[object Object]"
Object.prototype.toString.call(c);//"[object String]"

```

##### 64、split和join作用

```
join('x')用于以参数'x'连接多个字符或字符串，返回值为一个字符串；

split('x')用于以参数'x'分割字符串，返回一个数组
他们相反

```

##### 65、转义字符

```
不断行的空白格   &nbsp； 
小于	        &lt;
大于	        &gt;
&符号	        &amp;
双引号	        &quot;

```

##### 66、各大浏览器内核

```
1、IE浏览器内核：Trident内核，也是俗称的IE内核；
2、Chrome浏览器内核：统称为Chromium内核或Chrome内核，以前是Webkit内核，现在是Blink内核；
3、Firefox浏览器内核：Gecko内核，俗称Firefox内核；
4、Safari浏览器内核：Webkit内核；
5、Opera浏览器内核：最初是自己的Presto内核，后来是Webkit，现在是Blink内核；
6、360浏览器、猎豹浏览器内核：IE+Chrome双内核；
7、搜狗、遨游、QQ浏览器内核：Trident（兼容模式）+Webkit（高速模式）；
8、百度浏览器、世界之窗内核：IE内核；
9、2345浏览器内核：以前是IE内核，现在也是IE+Chrome双内核；

```

##### 67、雪碧图的好处

```
雪碧图把小图标放在同一张图片文件里，通过 background-position 显示那张图片文件的不同位置。
优点：
1.减少HTTP请求数
2.可以是任意图形，也可以是任意色彩
3.兼容性极好（对于位图的Sprites兼容性都非常的好，但对于SVG的Sprites，还是受到浏览器的限制，最起码要支持SVG的浏览器才能得到支持）
缺点
1.增加开发时间，需要人肉或通过相关工具，将零散的图形合并到一起，而不同的合并方式，图形的色彩对Web的性能有直接的影响；
2.增加维护成本，要增加新的图标合成进来，是件较难的事情，甚至直接会影响到前面又定位好的图片。目前为止，使用自动编译工具，相对比人肉处理要理想一些；
3.图片尺寸固定，在位图的Sprites中无法通过CSS来修改图标的大小，但在SVG的Sprites中可以配合CSS的background-size调整图标的大小；

```

##### 68、表格里cellpadding和cellspacing的区别

```
cellspacing 设置表格边框和单元格之间的间距（以像素为单位）
cellpadding 设置单元格中的内容与单元格边框的间距（也是以像素为单位）

```

##### 69、如何阻止表单提交

```
1.为表单的提交按钮添加点击事件，返回false
2.为表单的提交按钮添加点击事件，添加event.preventDefault()；

```

##### 70、去除用户名前后的空格、全部的空格

```
去除前后空格
使用str.trim()方法
去除全部空格
function tool(a){
    let b=a.trim();
    let c=b.split(" ");
    return c.join("");
}

```

##### 71、axios怎么挂载在原型上

```
// 设置 全局的 baseURL
axios.defaults.baseURL = 'xxx'

// 将 axios 挂载 到 父类的 原型上；
React.Component.prototype.$http = axios

```

##### 72、什么叫优雅降级和渐进增强

```
渐进增强（Progressive Enhancement）：一开始就针对低版本浏览器进行构建页面，完成基本的功能，然后再针
对高级浏览器进行效果、交互、追加功能达到更好的体验。

优雅降级（Graceful Degradation）：一开始就构建站点的完整功能，然后针对浏览器测试和修复。比如一开始使
用 CSS3 的特性构建了一个应用，然后逐步针对各大浏览器进行 hack 使其可以在低版本浏览器上正常浏览。

```

##### 73、JSON.stringify()和JSON.parse()用法

```
JSON.parse()是把字符串类型转化成JSON对象。
JSON.stringify()是把JSON对象转化成字符串类型。

```

##### 74、new操作符的原理

```
创建一个空对象，构造函数中的this指向这个空对象
这个新对象被执行【原型】链接
执行构造函数方法，属性和方法被添加到this引用的对象中

```

##### 75、DOM添加节点和移除节点

```
appendChild()
removeChild()

```

##### 76、如何理解js中this关键字

```
（1）在全局作用域以及普通函数中，this指向全局对象window（注意：在定时器中 setTimeout setInterval 中同样
     指向window）
（2）方法调用中this指向方法的对象，注册事件时this指向事件源
（3）构造函数中this指向构造函数的实例

```

##### 77、js中有哪些定时器

```
setTimeout() 只执行一次
setInterval() 可执行多次

```

##### 78、defer和async的区别

```
在于一个执行时间,defer会在文档解析完之后执行,并且多个defer会按照顺序执行,而async则是在js加载好之后就
会执行,并且多个async,哪个加载好就执行哪个

```

##### 79、es6中set和map

```
Set 它类似于数组但是成员的值都是唯一的，没有重复的值。 另外，两个对象总是不相等的。
map 它类似于对象，也是键值对的集合，但是“键”的范围不限于字符串，各种类型的值（包括对象）都可以当作键。也就是说，Object 结构提供了“字符串—值”的对应，Map 结构提供了“值—值”的对应，是一种更完善的 Hash 结构实现。如果你需要“键值对”的数据结构，Map 比 Object 更合适。

1.将set转为数组
Array.from(set);
var arr=[...set];
set的方法
set.add(value)添加某个值，返回set结构本身
set.delete(value)删除某个值，返回一个boolean ，表示是否成功删除
set.has(value)返回一个boolean，表示该值是否成为set的成员
set.clear()清除所有成员，无返回值
Set 结构的实例有四个遍历方法，可以用于遍历成员:
keys()：返回键名的遍历器
values()：返回键值的遍历器
entries()：返回键值对的遍历器
forEach()：使用回调函数遍历每个成员
2.对map操作
将map转为数组
	1.map转为JSON字符串
	var my_string=JSON.stringify([...my])
	将json字符串转为数组
	var my_obj=JSON.parse(my_string)
	
	2.直接用扩展运算符...展开
将map转为对象
Object.fromEntries(myMap.entries())
将对象转为map
new Map(Object.entries(obj))

map的方法
.set() 添加数据
.delete() 删除某个key以及对应value 返回boolean
.size 返回元素数
.keys() 获取map的所有Key
.values() 获取所有的value
.entries() 获取map的所有成员
.clear() 清除。

```

##### 80、数组去重

https://www.jianshu.com/p/6300a031dba5

```
1.通过set去重
arrayA=new Set();
2.利用for嵌套for，然后splice去重
双层循环，外层循环元素，内层循环时比较值。值相同时，则删去这个值
function unique(arr){            
        for(var i=0; i<arr.length; i++){
            for(var j=i+1; j<arr.length; j++){
                if(arr[i]==arr[j]){         //第一个等同于第二个，splice方法删除第二个
                    arr.splice(j,1);
                    j--;
                }
            }
        }
return arr;
}
3. indexOf() 去重
新建一个空的结果数组，for 循环原数组，判断结果数组是否存在当前元素，如果有相同的值则跳过，不相同则push进数组。
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return
    }
    var array = [];
    for (var i = 0; i < arr.length; i++) {
        if (array .indexOf(arr[i]) === -1) {
            array .push(arr[i])
        }
    }
    return array;
}
4.利用includes
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return
    }
    var array =[];
    for(var i = 0; i < arr.length; i++) {
            if( !array.includes( arr[i]) ) {//includes 检测数组是否有某个值
                    array.push(arr[i]);
              }
    }
    return array
}
5.  srot（）  相邻元素去重      
然后根据排序后的结果进行遍历及相邻元素比对，如果相等则跳过改元素，直到遍历结束
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return
    }
    arr = arr.sort()
    let res = []
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] !== arr[i-1]) {
            res.push(arr[i])
        }
    }
    return res
}

```


##### 82、position有哪几种属性

```
relative ：生成相对定位的元素，相对于其正常位置进行定位。
absolute :生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。
fixed :生成固定定位的元素，相对于浏览器窗口进行定位
static:默认值。没有定位，元素出现在正常的流中.
inherit:规定应该从父元素继承 position 属性的值。

```


##### 84、递归函数

```
直接或间接调用函数本身，一定要有一个结束条件 
就是在运行的过程中调用自己

```

##### 85、函数节流、函数防抖

```
函数节流概念：规定一个单位时间，在这个单位时间内，只能有一次触发事件的回调函数执行，如果在同一个单位
             时间内某事件被触发多次，只有一次能生效。
函数防抖概念：在事件被触发n秒后再执行回调，如果在这n秒内又被触发，则重新计时。

```

##### 86、解释下泛型

```
泛型（Generics）是指在定义函数、接口或类的时候，不预先指定具体的类型，而在使用的时候再指定类型的一种特性。

```

##### 87、null，undefined 的区别？

```
null是一个表示”无”的对象，转为数值时为0；undefined是一个表示”无”的原始值，转为数值时为NaN。
null表示”没有对象”，即该处不应该有值
（1） 作为函数的参数，表示该函数的参数不是对象。
（2） 作为对象原型链的终点。
undefined表示”缺省值”，就是此处应该有一个值，但是还没有定义        
（1）变量被声明了，但没有赋值时，就等于undefined。        
（2)  调用函数时，应该提供的参数没有提供，该参数等于undefined。        
（3）对象没有赋值的属性，该属性的值为undefined。        
（4）函数没有返回值时，默认返回undefined。

```

##### 88、原生js查询节点

```
document.getElementById("id")             //通过Id查找节点
document.getElementByClassName("class")   //通过类名获取
document.getElementsByName("name")        //通过name获取
document.getElementsByTagName()           //通过标签名获取
document.querySelectorAll()               //通过选择器查询

```

##### 89、文本限制

```
p{
    overflow: hidden;
    text-overflow: ellipsis;  //超出后以...结尾
    white-space:nowrap; 
    //white-space指定文字是否换行
}

```

##### 90、节点分类

```
1.元素节点 元素节点element对应网页的HTML标签元素
2.属性节点  元素节点（HTML标签）的属性，如 id 、class 、name 等
3.文本节点  素节点或属性节点中的文本内容。
4.注释节点  表示文档注释，形式为<!-- comment text -->。
5.文档节点  表示整个文档（DOM 树的根节点，即 document 
```

##### 91、正则中贪婪和非贪婪模式

```
贪婪与非贪婪模式影响的是被量词修饰的子表达式的匹配行为，
贪婪模式在整个表达式匹配成功的前提下，尽可能多的匹配，
非贪婪模式在整个表达式匹配成功的前提下，尽可能少的匹配
```

##### 92、class封装一个axios
https://juejin.im/post/5a52c9a4f265da3e2a0d6b74 

https://juejin.im/post/5d9f21e3518825564522f9e0

```
import axios from "axios"  // 封装一个比较好用的axios
class AjaxRequest{
    constructor(){
        // 请求的基础路径
        this.baseURL = process.env.NODE_ENV == "production" ? "/" : "http://localhost:3030"
        // 超时时间
        this.timeout = 3000;
    }
    //调用api传过来的options和construcoroptions的合并
    //api 例如 request("/user","post","name=z3")
    merge(options){
        return {...options,baseURL:this.baseURL,timeout:this.timeout}
    }
    //请求方法
    request(options){
        let instance = axios.create();
        let config = this.merge(options);
        return instance(config)
    }
}
export default new AjaxRequest;
```

##### 93、js中如何对对象进行遍历

```
Object.keys()方法
var obj = {'a':'123','b':'345'};
console.log(Object.keys(obj));  //['a','b']

var obj1 = { 100: "a", 2: "b", 7: "c"};
console.log(Object.keys(obj1)); // console: ["2", "7", "100"]

var obj2 = Object.create({}, { getFoo : { value : function () { return this.foo } } });
obj2.foo = 1;
console.log(Object.keys(obj2)); // console: ["foo"]
```

##### 94、什么是栈、什么是队列

```
栈是一种动态集合，它是一种LIFO（last in first out后进先出）结构
队列与栈不同，它是一种FIFO（first in first out先进先出）结构
```

##### 95、js中全局对象是什么

```
JavaScript 中有一个特殊的对象,称为全局对象（Global Object）,它及其所有属性都可以在程序的任何地方访
问,即全局变量。
（1）全局对象是预定义的对象,作为 JavaScript 的全局函数和全局属性的占位符。通过使用全局对象,可以访问
     所有其他所有预定义的对象、函数和属性。全局对象不是任何对象的属性,所以它没有名称。
（2）在顶层 JavaScript 代码中,可以用关键字 this 引用全局对象。但通常不必用这种方式引用全局对象,因为
     全局对象是作用域链的头,这意味着所有非限定性的变量和函数名都会作为该对象的属性来查询。例如,当js
     代码引用 parseInt() 函数时,它引用的是全局对象的 parseInt 属性。全局对象是作用域链的头,还意味着
     在顶层 JavaScript 代码中声明的所有变量,都将成为全局对象的属性。
（3）全局对象只是一个对象,而不是类。既没有构造函数,也无法用new实例化一个新的全局对象。
（4）实际上,ECMAScript 标准没有规定全局对象的类型,而在客户端 JavaScript 中,全局对象就是 Window对象,
     表示允许 JavaScript 代码的 Web 浏览器窗口。浏览器把全局对象作为window对象的一部分实现了,因此,
     所有的全局属性和函数都是window对象的属性和方法。 
```

##### 96、函数的命名规则和类的命名规则

```
函数：
命名方法：小驼峰式命名法。
命名规范：前缀应当为动词。
类：
命名方法：大驼峰式命名法，首字母大写。
命名规范：前缀为名称。
```

##### 97、关于回调地狱
```
一个函数作为参数需要依赖另一个函数执行调用,函数层层嵌套
解决：
    减少函数的嵌套,模块化,Promise,Generator,Async 
```

##### 98、什么是单页面（spa）和多页面（mpa）
```
单页面：就是只有一张Web页面的应用。单页应用程序 (SPA) 是加载单个HTML 页面并在用户与应用程序交互时动态
        更新该页面的Web应用程序。浏览器一开始会加载必需的HTML、CSS和JavaScript，所有的操作都在这张页
        面上完成，都由JavaScript来控制。因此，对单页应用来说模块化的开发和设计显得相当重要。
多页面：由多个完整页面组成，多页面跳转需要刷新所有资源，每个公共资源(js、css等)需选择性重新加载
```
![å¨è¿éæå¥å¾çæè¿°](https://jasonandjay.github.io/study/spa/diff.png) 

##### 99、伪类中nth-child和nth-of-type
```
nth-of-type的关键词是type，即他关心的是类型。它不会对所有子元素生效，只会对子元素中符合选择器要求的类
           型的子元素进行筛选，而忽略非选择器要求的类型的子元素。ele:nth-of-type(n)的意义就是选择父
           元素下的第n个ele类型的子元素。
nth-child的关键词是child，它关心的是所有子元素。它会对所有子元素生效。ele:nth-child的意义就是选择父
           元素下的第n个子元素，如果他是ele类型的，那么对他生效，如果他不是ele类型的，则不生效。
简而言之，nth-child影响到了所有child子元素，而nth-of-type则影响到了相应type的子元素。

```

 