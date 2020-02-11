##### 1、类型转换
```
1、Number(null)             //0
2、null==undefined          //true
3、100-null+"11"            //10011
4、0==""                    //true
```
##### 2、声明提前
```
(1)
var a = 100;
function a(){
    console.log("hello")
}
a();
//报错      Tip：function声明函数的优先级最高,放在最顶部,再是声明的变量
```
```
(2)
var a = 100;
var a = function(){
    console.log("hello world")
}
a()
//hello world
```
```
var a = 100;
function bar(){
    console.log(a)
    if(!a){
        var a = 20;
    }
    console.log(a)
}
bar()
//undefined
//20
Tip：{}里面为一个作用域
```
##### 3、逻辑运算符
```
1、console.log(10&&0)       //输出0     Tip：与运算符   如果第一个为false则返回第一个,为true的话,返回第二个
2、console.log(""||"abc")   //abc      Tip：或运算符   第一个为true,返回第一个,为false返回第二个
您细品
```

##### 4、请写出下列代码输出结果

```javascript
function foo(something) {
    this.a = something;
}
var obj1 = { foo: foo };
var obj2 = {};
//foo函数中的this是obj1，就是让obj1.a = 2;
obj1.foo(2);
console.log(obj1.a);     //2
//改变obj1里面的foo函数中的this为obj2，同时入参参数3，即让obj2.a = 3
obj1.foo.call(obj2, 3);
console.log(obj2.a);     //3
//把obj1.foo函数当成构造函数来使用，此时foo构造函数中的this就是new出来的bar实例，因此bar.a = 4
//但是次时的obj1仍然是上面的obj1，所以obj1.a还是为2
var bar = new obj1.foo(4);
console.log(obj1.a);     //2
console.log(bar.a);      //4
```
##### 5、将数组[999,88,777,409,7862,1045,3987,4679,56]进行排序

```javascript
//冒泡排序
var arr = [999,88,777,409,7862,1045,3987,4679,56];
for (var j = 0; j < arr.length - 1; j++) {
    for (var i = 0; i < arr.length - 1 - j; i++) {
        if (arr[i] > arr[i + 1]) {
            var temp = arr[i];
            arr[i] = arr[i + 1];
            arr[i + 1] = temp;
        }
    }
}
console.log(arr);
```
##### 6、下面这个JS程序的输出是什么？

```javascript
function Foo(){	
    var i=0;
    return function(){
        console.log(i++);
    }
}

var f1=Foo();
    f2=Foo();

f1();//0
f1();//1      闭包：函数嵌套函数，延长变量的作用域链
f2();//0
```
##### 7、请给出这段代码的运行结果

```javascript
var bb=1;
function aa(bb){
	bb=2;
	alert(bb);
}

aa(bb);//2        调用aa()函数，aa函数里面的局部变量bb是2
alert(bb);//1    aa函数里面局部变量的bb是2，aa函数外部的全局变量bb是1
```
##### 8、以下代码中x,y,p分别是多少？

```javascript
let obj={p:['Hello',{y:'World'}]};
let {p,p:[{x,y}]}=obj;

答：x:undefined;
       y:undefined;
       p:['Hello',{y:'World'}]
```
##### 9、数组求最大值 ：var arr=[45,2,3,4,10,8],用es6求最大值?

```javascript
var arr = [45,2,3,4,10,8];
var max = arr.reduce(function(a , b){ 
    return b > a ? b : a; 
});
console.log(max); 
# reduce:让数组中的前项和后项做某种计算，并累计最终值.
```

##### 10、以下的运行结果是？

```javascript
function runAsync1(){
	var p=new Promise(function(resolve,reject){
        setTimeout(function(){
            resolve('数据1')；
            return '数据2'
         },1000);
    });
	return p;
};

function runAsyn2(){
	var p=new Promise(function(resolve,reject){
        setTimeout(function(){
            resolve('数据3')；
            return '数据4'
        },2000);
    });
	return p;
};

Promise.all([runAsync1(),runAsync2()])
.then(function(results){
	console.log(results);
})
.catch(function(reason){
	console.log(reason);
})

答：输出：['数据1'，‘数据3’]；
解析：Promise的all方法提供了并行执行异步操作的能力，并且在所有异步操作执行完后才执行回调。runAsync1(),runAsync2()两个函数是并行执行的，等到它们都执行完后才会进到then里面。
```