>#### 一：ECMAScript: JS语言标准

##### 1.js数据类型的分类

- 1.1 五种基本类型：`String`,`Number`,`Boolean`,`Null`,`Undefined`. (ES6新增了一种基本类型：`Sysmbol`)

```javascript
1.基本类型的值在内存中占据固定大小的空间,因此被保存在栈内存中
2.基本类型的复制被称为深拷贝，传的是值
var a = 1;
var b = a;
a = 2;
console.log(b);//结果是1。b不会因为a改变而改变
```
- 1.2 三种引用类型：`Object`,`Array`,`Function`

  1.引用类型的值被保存在堆内存中。
  2.包含引用类型值的变量实际上包含的并不是对象本身,而是一个指向该对象的指针。
  3.引用类型的复制仅仅是将地址复制给对方，传的是地址
```javascript
var a = {age:20};
var b = a;
b.age = 21;
console.log(a.age) //21
```

##### 2.js判断数据类型(判断数据类型是否为数组)
- 2.1 typeof
    - typeof 返回类型有7种：string number boolean undefined Function Object Symbol(es6)
    - typeof 不能判断数组类型
    - typeof 返回的值为字符串，
```js
alert(typeof  a  ==  "string") -->  true
alert(typeof  a  ==  String) -->  false
```
```js
function  test(){}
console.log(typeof  1); // number
console.log(typeof  test); // function
console.log(typeof  "yunxi"); // string
console.log(typeof  undefined); // undefined
```
- 2.2 instanceof
```js
console.log([] instanceof  Array); // true
console.log(/\d+/g  instanceof  Array); // false
```
- 2.3 constructor
```js
console.log(arr.constructor  ==  Array); // true
```
- 2.4 Array.isArray(数组)
```js
Array.isArray(state.car) //true
```

##### 3.js哪几种情况为false

五种：NaN,null,undefined,0,""

##### 4.substr,substring,slice的区别
- substr和substring截取字符串, slice截取数组
- substr(index, length)截取从index开始，长度为length的字符串
- substring(index, endIndex)从index开始，到endIndex结束，不包括endIndex

##### 5.遍历数组的方法
- 1.for 循环
```javascript
for(var i=1; i<5; i++) {
    console.log(i); //1, 2, 3, 4
}
```
- 2.for in 遍历下标，也可以遍历 Object 的 key 值
```javascript
// 遍历数组下标
for(var i in arr) {
    console.log(i);
}
// 遍历对象 key 值
var obj = {
  name: 'jack',
   age: '18'
}
for (var i in obj) {
  console.log(i) // name, age
}
```
- 3.for of 遍历值，但不能遍历 Object 的 值
- 4.arr.forEach, 遍历每一项以及下标
```javascript
var arr = [1, 2, 3];
arr.forEach((item, index)=>{
    console.log(item);
    console.log(index);
})
```
- 5.Array.from(arr, (value, index)=>{})
```javascript
Array.from(arr, function(value, index){
    console.log(value);
    console.log(index);
})
```
- 6.map
```javascript
arr.map((item, index)=>{
    console.log(index);
})
```

##### 6.数组的增删查改

1.添加

> 改变数组式增加：

1. push(para1, para2) ：从后添加

2. unshift(para1, para2)：从头增加

3. arr.splice(index, howmany, item)：定点添加-->当howmany修改变为0，即变成定点添加. (splice 读 /ai/)
```javascript
var arr = [1, 2, 3, 4];
arr.push(5, 6);
arr.push([5, 6]) //生成二维数组 1, 2, 3, 4, [5, 6]
arr.push(...[5, 6]) //把5，6加入  `...`是展开语法，属于es6
console.log(arr);  //1, 2, 3, 4, 5, 6
```
```javascript
arr.splice(0, 0, 9);  //往第一项前添加
console.log(arr);   //9, 1, 2, 3, 4
```
> 增加：不改变数组内容，创建一个新的数组

var b = concat(para1, para2)

var b = concat([para1, para2]) 可直接将数组添加，不需展开语法
```javascript
var n = arr.concat(5, 6);
console.log(n);  //1, 2, 3, 4, 5, 6
```

2.删除

1. shift()从头删除

```javascript
arr.shift();
```
2. pop()从后删除

3.修改

splice(index, howmany, item)
index: 从哪里开始
howmany：删除几个，howmany为0就会变成添加
item：在删除的地方添加的值
```javascript
var arr = [1, 2, 3, 4];
arr.splice(1, 2, 1, 1);
console.log(arr); //1, 1, 1, 4
```
4.查询

查询数组中值的下标
arr.indexOf(value)
```javascript
var index = arr.indexOf(2);
console.log(index);  //1
```
5.截取

slice(first, last) 
左闭右开，first包括，last不包括，没有last则从第一位到最后一位
```javascript
var arr = [1, 2, 3, 4]
// var b = arr.slice(1, 3); //2, 3
var b = arr.slice(1); //2, 3, 4
console.log(b);
```
##### 7.深拷贝的几种方式
>深拷贝数组

1.展开语法
```js
var arr = [1, 2, 3, 4, 5];
var temp = [...arr];
```
2.slice 和 concat
```js
var temp = arr.slice(0);
```
```js
var temp = [].concat(arr);
```
3.forEach 单个拷贝
```js
arr.forEach(ele => {
    temp.push(ele)
}
```
>深拷贝对象

1.展开语法
```js
var obj = {
    "name": 'xu',
    "age": 23
}
var test = {...obj};
console.log(test);
```
2. for in 遍历
```js
var test = {};
for(var i in obj) {
    test[i] = obj[i];
}
console.log(test);
```

##### 8.Promise的用法
解释：Promise 是一个构造函数，它可以用来解决回调地狱，封装 ajax 请求
用法：如封装$.ajax
```js
// 1. 创建一个方法，其中 return 出 Promise 对象
// 2. Promise 对象接受一个函数，其中接收 resolve 和 resject 两个参数
function promise(url) {
    return new Promise(function (resolve, reject) {
        $.ajax({
            url,
            type: "get",
            dataType: "jsonp",
            success: function (res) {
                resolve(res);  // resolve 处理异步操作成功的结果
            },
            error: function (err) {
                reject(err)  // reject 处理异步操作失败的结果
            }
        })
    })
}

// 3. 使用封装好的 promise 方法
var url = 'https://douban.uieee.com/v2/movie/top250';
promise(url).then(res => {
    console.log(res);  // 如果请求成功，则打印 res
}, err => {
    console.log(err);  // 如果请求失败，则打印 err
})
```3


##### 4.JS的内存机制与垃圾回收机制

##### 5.JS中的内置函数

##### 6.https的原理及其局限性

##### 7.get方式和post方式有什么区别(李许怡安)

##### 8.解释一下js原型链(李许)

##### 9.call,apply,bind的作用,之间的区别(李许)

##### 10.什么叫域,js是否能跨域,如何跨域(李许)

##### 11.正则中的贪婪模式非贪婪模式的区别(李许)

##### 12.https的局限性(李姚)

##### 13.数组的方法有哪些,有哪些方法不会改变数组原来的结构

##### 14.==和===的区别

##### 15.解释一下同步和异步

##### 16.http和https的区别

##### 17.字符串中有哪些方法支持正则

~~~
replace
match
split
search
~~~

##### 18.let,var,const的区别

##### 19.什么是声明提前

##### 20.谈谈Javascript的垃圾回收机制

##### 21.如何进行页面的性能优化

##### 22.如何实现Javascript的继承

##### 23.浏览器内核分成几个部分,几个浏览器厂商的内核分别是什么

##### 24.innerHTML和document.write之间的区别

>#### **童建设组**

##### 1.$.ajax的传参(戴靓)

##### 2.js中的this怎么理解(童建设)

##### 3.原生ajax如何实现(全梦妍)

##### 4.如何解决回调地狱(戴靓)

~~~
- promise
- generator
- async
~~~

##### 5.点击一个按钮,从客户端发起请求,到服务器端响应到底放生了什么(童建设)

##### 6.什么是跨域(王宇)

##### 7.一个完整的http请求分成几个部分

##### 8.说一下new操作符的作用

##### 9.常见的http状态码

##### 10.数组遍历的方法有哪些

##### 11.写一个简单的邮箱正则

##### 12.字符串的常用方法

##### 13.cookie,LocalStorage,sessionStorage的区别

##### 14.如何实现事件监听(javascript,jquery实现)

>#### **徐保山组**

##### 1.Javascript中的定时器有哪些？他们的区别及用法是什么?(丁美丽)

##### 2.常用的数组的方法有哪些(尹超)

##### 3.promise的原理,如何使用promise(徐保山)

##### 4.怎样添加、移除、移动、复制、创建和查找节点？(丁美丽)

##### 5.JSON的几种方法(丁美丽)

##### 6.什么是事件冒泡,事件捕获,事件委托?如何阻止事件冒泡?(陈雅婷)

##### 7.如何创建JS对象(陈雅婷)

##### 8.如何判断JS的数据类型(丁美丽)

##### 9.基本类型和引用类型的在赋值运算中的区别(徐保山)

##### 10.MVVM开发模式带来的好处

~~~
- 模块化
- 低藕合
- 高复用
- 可维护
- 可拓展
~~~

##### 11.什么叫不同的域

##### 12.如何获取DOM节点

##### 13.JS支持重载吗?(尹超)

##### 14.对js语言特性的理解

##### 15.ES6有哪些特点

##### 16.前端性能优化

#### **算法**

##### 1.数组去重

~~~
var arr = [1, 1, 2, 2, 3, 4]
var clone = [];
var temp ={};
arr.forEach(ele=>{
    if(!temp[ele]){
        temp[ele]="a"
        clone.push(ele)
    }
})
console.log(clone);
~~~

##### 2.冒泡排序

##### 3.取数组中的偶数

##### 4.取数组中的最大值,最小值


##### 6.如何判断质数

~~~
function isPrime(num){
            for(var i=2;i<num;i++){
                if(num%i==0){
                    return false
                }else{
                    return true;
                }
            }
            
}
~~~
bbb
test
aaa

