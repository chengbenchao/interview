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
