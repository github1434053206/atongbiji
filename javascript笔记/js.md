# Javascript基础

## js介绍

### js是什么

JavaScript（简称“JS”） 是一种具有[函数](https://baike.baidu.com/item/函数/301912)优先的[轻量级](https://baike.baidu.com/item/轻量级/22359343)，解释型或即时编译型的高级[编程语言](https://baike.baidu.com/item/编程语言/9845131)。

https://baike.baidu.com/item/javascript/321142?fr=aladdin

### js历史

https://javascript.ruanyifeng.com/introduction/history.html

### js 的组成

| 组成部分   | 说明                               |
| ---------- | ---------------------------------- |
| Ecmascript | 描述了该语言的语法和基本对象       |
| DOM        | 描述了处理网页内容的方法和接口     |
| BOM        | 描述了与浏览器进行交互的方法和接口 |

### js内存


https://www.jb51.net/article/164566.htm

## js基本概念

### js中的数据类型

JavaScript 有 5 种简单数据类型：`Undefined、Null、Boolean、Number、String` 和 1 种复杂数据类型 `Object` 。

#### null和undefined的区别

```
undefined表示bai变量du声明但未初始化时zhi的值

null表示准备用来保存对象，还没有真正dao保存对象的值。从逻辑角度看，null值表示一个空对象指针，return返回objectleix
```

https://zhidao.baidu.com/question/684860319823019892.html

https://www.cnblogs.com/ChengWuyi/p/8648164.html

https://www.zhihu.com/question/56841737

https://www.cnblogs.com/dyh-air/articles/7943295.html
https://www.cnblogs.com/lvmylife/p/8183653.html

#### for和if

```javascript
for in(类似于增强型FOR循环)
  var arr = [1,3,5,7,"js"];
    //循环打印出数组中的每个元素
     for(index in arr){//index表示数组下标
        //alert(index);
        alert(arr[index]);
```

#### js替换字符串

https://www.cnblogs.com/youantianqin/p/11276555.html

### 类型检测

#### typeof

检测变量类型：https://www.runoob.com/js/js-typeof.html

#### instanceof

**instanceof** **运算符**用于检测构造函数的 `prototype` 属性是否出现在某个实例对象的原型链上。

https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/instanceof

```javascript
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}
const auto = new Car('Honda', 'Accord', 1998);

console.log(auto instanceof Car);
// expected output: true

console.log(auto instanceof Object);
// expected output: true

```

#### object.prototype.toString.call()

**object.prototype.toString.call()** 方法就可以精确的判断js对象的数据类型。

https://www.cnblogs.com/mmzuo-798/p/11102798.html

```javascript
var a = "hello world";
var b = [];
var c = function(){};

console.log( object.prototype.toString.call( a ) );
console.log( object.prototype.toString.call( b ) );
console.log( object.prototype.toString.call( c ) );

//结果
//[object String];
//[object Array];
//[object Function];
```

### 常用属性

#### console.dir和console.log

dir可以看见内部

#### argument

argument代表所有参数

可看：

https://www.cnblogs.com/gongyijie/p/9425549.html

https://blog.csdn.net/w369033345/article/details/52366657

### 值类型和引用类型

https://www.jb51.net/article/106581.htm

https://www.cnblogs.com/leiting/p/8081413.html

https://www.cnblogs.com/cxying93/p/6106469.html

#### 值类型和引用类型的差别

```
- 基本类型在内存中占据固定大小的空间，因此被保存在栈内存中

- 从一个变量向另一个变量复制基本类型的值，复制的是值的副本

- 引用类型的值是对象，保存在堆内存

- 包含引用类型值的变量实际上包含的并不是对象本身，而是一个指向该对象的指针

- 从一个变量向另一个变量复制引用类型的值的时候，复制是引用指针，因此两个变量最终都指向同一个对象
```

### 预解析-变量提升

预解析:在当前作用域下，js运行之前，会把带有var和function关键字声明的变量先声明，并在内存中安排好。然后从上至下解析js语句。而且function的声明优先于var声明。

https://www.jianshu.com/p/c3276ff58c93

https://www.cnblogs.com/urlvue/p/9905992.html

https://www.cnblogs.com/shaohua007/p/7587657.html

### js获取时间

https://www.cnblogs.com/zhaoqiming/p/7988380.html

### js中的解构

https://www.cnblogs.com/ghostwu/p/7305973.html

## js面向对象

### 创建对象简单方式

我们可以直接通过 `new Object()` 创建：

```javascript
var person = new Object()
person.name = 'Jack'
person.age = 18

person.sayName = function () {
  console.log(this.name)
}
```

json格式方式创建：

```javascript
var person = {
  name: 'Jack',
  age: 18,
  sayName: function () {
    console.log(this.name)
  }
}
```

工厂模式：

```javascript
function createPerson (name, age) {
  return {
    name: name,
    age: age,
    sayName: function () {
      console.log(this.name)
    }
  }
}

var p1 = createPerson('Jack', 18)
var p2 = createPerson('Mike', 18)
```

### 构造函数

```javascript
function Person (name, age) {
  // 当使用 new 操作符调用 Person() 的时候，实际上这里会先创建一个对象
  // var instance = {}
  // 然后让内部的 this 指向 instance 对象
  // this = instance
  // 接下来所有针对 this 的操作实际上操作的就是 instance

  this.name = name
  this.age = age
  this.sayName = function () {
    console.log(this.name)
  }

  // 在函数的结尾处会将 this 返回，也就是 instance
  // return this
}

var p1 = new Person('Jack', 18)
p1.sayName() // => Jack

var p2 = new Person('Mike', 23)
p2.sayName() // => Mike
```

#### 构造函数和实例对象的关系

构造函数是根据具体的事物抽象出来的抽象模板

实例对象是根据抽象的构造函数模板得到的具体实例对象

如果要检测对象的类型，还是使用 `instanceof` 操作符

```javascript
console.log(p1 instanceof Person) // => true
console.log(p2 instanceof Person) // => true
```

### 原型-prototype 

Javascript 规定，每一个构造函数都有一个 `prototype` 属性，指向另一个对象。
这个对象的所有属性和方法，都会被构造函数的实例继承。

```javascript
function Person (name, age) {
  this.name = name
  this.age = age
}

console.log(Person.prototype)

Person.prototype.type = 'human'

Person.prototype.sayName = function () {
  console.log(this.name)
}

var p1 = new Person(...)
var p2 = new Person(...)

console.log(p1.sayName === p2.sayName) // => true
```

这时所有实例的 `type` 属性和 `sayName()` 方法，
其实都是同一个内存地址，指向 `prototype` 对象，因此就提高了运行效率。

### 构造函数、实例、原型三者之间的关系

任何函数都具有一个 `prototype` 属性，该属性是一个对象，构造函数的 `prototype` 对象默认都有一个 `constructor` 属性，指向 `prototype` 对象所在函数。，通过构造函数得到的实例对象内部会包含一个指向构造函数的 `prototype` 对象的指针 `__proto__`。

<img src="../三者之间的关系.png" alt="">

```javascript
//运行这段代码，在窗口看console
function F () {
    this.name = "abc"
}
console.dir(F)
console.log(F.prototype) // => object

F.prototype.sayHi = function () {
  console.log('hi!')
}
console.log("----------------------")


var instance = new F()

console.log(instance)
```

把构造函数比作入口a

把原型对象比作入口b

把实例对象比作入口c

入口的链接是桥

入口a可以通过prototype对象进入口b，入口b可以通过constructor对象进入口a，入口c可以通过__proto__进入口b

入口a可以通过new进入入口c

a<---------------------->b

↓                                  ↑

c--------------------------c

### 属性成员的搜索原则：原型链

简单的回顾一下构造函数、原型和实例的关系：每个构造函数都有一个原型对象，原型对象都包含一个指向构造函数的指针，而实例都包含一个指向原型对象的内部指针。那么假如我们让原型对象等于另一个类型的实例，结果会怎样？显然，此时的原型对象将包含一个指向另一个原型的指针，相应地，另一个原型中也包含着一个指向另一个构造函数的指针。假如另一个原型又是另一个类型的实例，那么上述关系依然成立。如此层层递进，就构成了实例与原型的链条。这就是所谓的原型链的基本概念。——摘自《javascript高级程序设计》

把构造函数比作入口a

把原型对象比作入口b

把实例对象比作入口c

把原型对象看成实例对象，那么这个实例对象的原型对象比作入口d

入口的链接是桥

入口a可以通过prototype对象进入口b，入口b可以通过constructor对象进入口a，入口c可以通过__proto__进入口b

入口a可以通过new进入入口c,入口b可以通过proto进入入口d

a<---------------------->b

↓                      /^^     ↓      

c--------------               ↓ 

​                                  ↓ 

​								  d

从b到d的这条链就是原型链，由此课件原型链子可以有无线条

切记：原型对象也算是某个实例对象

https://www.cnblogs.com/loveyaxin/p/11151586.html

### javascript的对象、类、方法、原型

```
类和对象的概念：

　　1.所有的事物都是一个对象，而类就是具有相同属性和行为方法的事物的集合

　　2.在JavaScript中建立对象的目的就是将所有的具有相同属性的行为的代码整合到一起，方便使用者的管理

　　3.类是具有相同特征和方法(行为)的事物的抽象，其中可以理解为：对象是类的实例，类是对象的实例
```

```
对象可分为两种，一种是函数对象，另一种是普通对象
普通对象不含有prototype，只含有__proto__
函数对象两者都含有

实例中的__proto__就是原型对象，构造函数中的prototype也是原型对象
实例中的构造函数和原型对象中的构造函数指向同一个构造函数
```

https://www.cnblogs.com/klmn/p/6701520.html

## 继承

https://www.baidu.com/link?url=G6TIvucR4tvdB8JevQmRB4Q7NxP4Nf85MDbNeJ69Q_6w3MHcn7czg3qQ2beTfB4Oq3GQToytkgXqkWmKpdKAG_&wd=&eqid=fb3429550000e991000000065f9c3032

构造函数的属性继承：借用构造函数

```javascript
function Person (name, age) {
  this.type = 'human'
  this.name = name
  this.age = age
}

function Student (name, age) {
  // 借用构造函数继承属性成员
  Person.call(this, name, age)
}

var s1 = Student('张三', 18)
console.log(s1.type, s1.name, s1.age) // => human 张三 18
```

原型继承

```javascript
function Person (name, age) {
  this.type = 'human'
  this.name = name
  this.age = age
}

Person.prototype.sayName = function () {
  console.log('hello ' + this.name)
}

function Student (name, age) {
  Person.call(this, name, age)
}

// 利用原型的特性实现继承
Student.prototype = new Person()

var s1 = Student('张三', 18)

console.log(s1.type) // => human

s1.sayName() // => hello 张三
```

### ES6中class 的**继承**

```javascript
  class Person {
            //调用类的构造方法
            constructor(name, age) {
                this.name = name
                this.age = age
            }
            //定义一般的方法
            showName() {
                console.log("调用父类的方法")
                console.log(this.name, this.age);
            }
        }
        let p1 = new  Person('kobe', 39)
        console.log(p1)
        //定义一个子类
        class Student extends Person {
            constructor(name, age, salary) {
                super(name, age)//通过super调用父类的构造方法
                this.salary = salary
            }
            showName() {//在子类自身定义方法
                console.log("调用子类的方法")
                console.log(this.name, this.age, this.salary);
            }
        }
        let s1 = new Student('wade', 38, 1000000000)
        console.log(s1)
        s1.showName()
```

## 函数

### 函数的定义方式

#### 函数声明

```
function foo () {

}
```

#### 函数表达式

```
var foo = function () {

}
```

#### 创建参数个数不限数量的函数

https://blog.csdn.net/xiamocsdn/article/details/88680437

```javascript
function sum(){
	var sum=0;
	for (var i = 0; i < arguments.length; i++) {
		sum += arguments[i];
	}
	return sum;
}
console.log(sum(1,33,12));
```

### 函数的调用方式

#### 函数内 `this` 指向的不同场景

函数的调用方式决定了 `this` 指向的不同：

| 调用方式     | 非严格模式     | 备注                         |
| ------------ | -------------- | ---------------------------- |
| 普通函数调用 | window         | 严格模式下是 undefined       |
| 构造函数调用 | 实例对象       | 原型方法中 this 也是实例对象 |
| 对象方法调用 | 该方法所属对象 | 紧挨着的对象                 |
| 事件绑定方法 | 绑定事件对象   |                              |
| 定时器函数   | window         |                              |

这就是对函数内部 this 指向的基本整理，写代码写多了自然而然就熟悉了。

### js对象和函数的关系

很明显函数是一种对象，但你不能说函数是对象的一种。因为他俩之间是没有包含关系的。有点像鸡蛋和鸡的关系。对象是通过函数创建的，而函数又是一种对象，所有函数都是 `Function` 的实例

https://www.cnblogs.com/yuanzhiguo/p/8109540.html

https://www.cnblogs.com/ooooevan/p/6013513.html

### 函数的其他成员

```
- arguments
  - 实参集合
  
- caller
  - 函数的调用者
  
- length
  - 形参的个数
  
- name
  - 函数的名称
```

```javascript
function fn(x, y, z) {
  console.log(fn.length) // => 形参的个数
  console.log(arguments) // 伪数组实参参数集合
  console.log(arguments.callee === fn) // 函数本身
  console.log(fn.caller) // 函数的调用者
  console.log(fn.name) // => 函数的名字
}

function f() {
  fn(10, 20, 30)
}

f()
```

### 高阶函数

```
- 函数可以作为参数

- 函数可以作为返回值
```

```javascript
// 函数可以作为参数

function eat (callback) {
  setTimeout(function () {
    console.log('吃完了')
    callback()
  }, 1000)
}

eat(function () {
  console.log('去唱歌')
})
```

```javascript
//函数可以作为返回值

function genFun (type) {
  return function (obj) {
    return Object.prototype.toString.call(obj) === type
  }
}

var isArray = genFun('[object Array]')
var isObject = genFun('[object Object]')

console.log(isArray([])) // => true
console.log(isArray({})) // => true
```

### 作用域

```
- 全局作用域

- 函数作用域

- 块级作用域
```

### 回调函数

我想把并行执行的name，console出来

```javascript
function get(){


    setTimeout(() => {
        let name = "zhangsan"
        return name
    }, 1000);
}

let ps = get();
console.log(ps)

//返回undfined
```

用回调函数：

```javascript
function get(){

    var callback = function(data){
        console.log(data)
    }

    setTimeout(() => {
        let name = "zhangsan"
        callback(name)
    }, 1000);
}

get();
```

和这个，两个代码块都是相同的结果，但第1个代码块是方便理解第2个代码块

```javascript
function get(callback){
    setTimeout(() => {
        let name = "zhangsan"
        callback(name)
    }, 1000);
}

get((data)=>{
    console.log(data)
})
```

```
js 回调函数获取异步操作数据：

https://blog.csdn.net/weixin_39051908/article/details/103887002
```



### 函数闭包

http://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html

闭包就是将函数内部和函数外部连接起来的一座桥梁。

它的最大用处有两个，一个是前面提到的可以读取函数内部的变量，另一个就是让这些变量的值始终保持在内存中。

读取函数内部的变量：

```javascript
function f1(){

　　　　var n=999;

　　　　function f2(){
　　　　　　alert(n);
　　　　}

　　　　return f2;

　　}

　　var result=f1();

　　result(); // 999
```

让这些变量的值始终保持在内存中：

```javascript
　function f1(){

　　　　var n=999;

　　　　nAdd=function(){n+=1}

　　　　function f2(){
　　　　　　alert(n);
　　　　}

　　　　return f2;

　　}

　　var result=f1();

　　result(); // 999

　　nAdd();

　　result(); // 1000
```

### 函数递归

#### 递归执行模型

```javascript
function fn1 () {
  console.log(111)
  fn2()
  console.log('fn1')
}

function fn2 () {
  console.log(222)
  fn3()
  console.log('fn2')
}

function fn3 () {
  console.log(333)
  fn4()
  console.log('fn3')
}

function fn4 () {
  console.log(444)
  console.log('fn4')
}

fn1()
```

#### 浅拷贝和深拷贝

https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&tn=baidu&wd=javascript%20%E6%B5%85%E6%8B%B7%E8%B4%9D%E5%92%8C%E6%B7%B1%E6%8B%B7%E8%B4%9D&oq=javascript%2520%25E9%2597%25AD%25E5%258C%2585&rsv_pq=e82da6fd0001e285&rsv_t=46dcDjgujaRWA%2BQVTdgb6rbvhUtMkvRz%2Bxk0eXjECZu4UQG3nozyJ2LDiE4&rqlang=cn&rsv_dl=tb&rsv_enter=1&rsv_btype=t&inputT=330&rsv_sug3=139&rsv_sug1=18&rsv_sug7=100&rsv_n=2&rsv_sug2=0&rsv_sug4=428

https://www.cnblogs.com/zyt-it/p/10256742.html

https://www.cnblogs.com/to-red/p/12450607.html

## call、apply、bind

在 javascript 中，call 和 apply 都是为了改变某个函数运行时的上下文（context）而存在的，换句话说，就是为了改变函数体内部 this 的指向。

总结：call和apply都是改变上下文中的this并立即执行这个函数，bind方法可以让对应的函数想什么时候调就什么时候调用，并且可以将参数在执行的时候添加，这是它们的区别，根据自己的实际情况来选择使用。

https://www.runoob.com/w3cnote/js-call-apply-bind.html

https://www.cnblogs.com/pssp/p/5215621.html

https://www.cnblogs.com/moqiutao/p/7371988.tml

## 正则表达式

抄百度的正则表达式

https://www.cnblogs.com/boonya/p/11181300.html
https://blog.csdn.net/weixin_40408910/article/details/80598640

## 数组和伪数组

### 数组

数组不用多说

#### javascript数组中的map方法

https://blog.csdn.net/liminwang0311/article/details/86480829

#### js对象数组转json互转

https://www.cnblogs.com/Im-Victor/p/9431718.html

#### js 数组去重

https://blog.csdn.net/weixin_42567389/article/details/88130456

https://www.w3school.com.cn/jsref/jsref_splice.asp

#### slice() 方法

slice() 方法可从已有的数组中返回选定的元素。

https://www.w3school.com.cn/js/jsref_slice_array.asp

https://www.cnblogs.com/langshening/p/9975866.html

#### 排序

https://www.cnblogs.com/webcabana/p/7460038.html

#### 数组的第一个添加数组

https://blog.csdn.net/qq_39702981/article/details/86220737

### 伪数组

```
1. 拥有 length 属性，其它属性（索引）为非负整数(对象中的索引会被当做字符串来处理，这里你可以当做是个非负整数串来理解)

2. 不具有数组所具有的方法


常见的伪数组有：

- 函数内部的 `arguments`

- DOM 对象列表（比如通过 `document.getElementsByTags` 得到的列表）

- jQuery 对象（比如 `$("div")` ）
```

伪数组是一个 Object，而真实的数组是一个 Array。

伪数组存在的意义，是可以让普通的对象也能正常使用数组的很多方法，比如：

```javascript
var arr = Array.prototype.slice.call(arguments);
 
Array.prototype.forEach.call(arguments, function(v) {
  // 循环arguments对象
});

// push
// some
// every
// filter
// map
// ...
```

## JavaScript 垃圾回收机制

https://segmentfault.com/a/1190000018605776?utm_source=tag-newest

https://en.wikipedia.org/wiki/Garbage_collection_%28computer_science%29

## Object静态成员和实例成员

暂没写

## 命名规范

https://www.cnblogs.com/xulei1992/p/5606565.html

https://www.runoob.com/js/js-conventions.html

```
命名的方法通常有以下几类：  

a).命名法说明

1).camel命名法，形如thisIsAnApple 

2).pascal命名法，形如ThisIsAnApple

3).下划线命名法，形如this_is_an_apple  · 

4).中划线命名法，形如this-is-an-apple  

根据不同类型的内容，必须严格采用如下的命名法： 

b).变量名：必须使用camel命名法

c).参数名：必须使用camel命名法  

d).函数名：必须使用camel命名法

e).方法/属性：必须使用camel命名法

f).私有（保护）成员：必须以下划线_开头

g).常量名：必须使用全部大写的下划线命名法，如IS_DEBUG_ENABLED

h).类名：必须使用pascal命名法

i).枚举名：必须使用pascal命名法  

j).枚举的属性：必须使用全部大写的下划线命名法

k).命名空间：必须使用camel命名法  
```

### 在""或''中插入变量或方法

 return `translate(${arcs.centroid(d)})`或者
  return 'translate('+arcs.centroid(d)+')'

# BOM

## BOM的概念

我们在浏览器中的一些操作都可以使用BOM的方式进行编程处理，

比如：刷新浏览器、后退、前进、在浏览器中输入URL等

## BOM的顶级对象window

```javascript
浏览器中有个顶级对象--window--皇上

页面中顶级对象:document--太监

页面中的所有内容都是浏览器的
所有变量都属于window，window可省
window.alert(“a”）;
```

window是浏览器的顶级对象，当调用window下的属性和方法时，可以省略window
注意：window下一个特殊的属性 window.name

### 对话框

- alert()
- prompt()
- confirm()

### 页面加载事件

window.onload，页面加载完毕
onunload，当用户退出页面时

onload

```javascript
window.onload = function () {
  // 当页面加载完成执行
  // 当页面完全加载所有内容（包括图像、脚本文件、CSS 文件等）执行
}
```

onunload

```javascript
window.onunload = function () {
  // 当用户退出页面时执行
}
```

## 定时器

#### setTimeout()和clearTimeout()

在指定的毫秒数到达之后执行指定的函数，只执行一次

```javascript
// 创建一个定时器，1000毫秒后执行，返回定时器的标示
var timerId = setTimeout(function () {
  console.log('Hello World');
}, 1000);

// 取消定时器的执行
clearTimeout(timerId);
```

#### setInterval()和clearInterval()

定时调用的函数，可以按照给定的时间(单位毫秒)周期调用函数

```javascript
// 创建一个定时器，每隔1秒调用一次
var timerId = setInterval(function () {
  var date = new Date();
  console.log(date.toLocaleTimeString());
}, 1000);

// 取消定时器的执行
clearInterval(timerId);
```

## location对象

location对象是window对象下的一个属性，时候的时候可以省略window对象

location可以获取或者设置浏览器地址栏的URL

成员

assign()/reload()/replace()

hash/host/hostname/search/href…
href属性：设置跳转页面地址

## URL

统一资源定位符 (Uniform Resource Locator, URL)

URL的组成

```
scheme://host:port/path?query#fragment
scheme:通信协议
	常用的http,ftp,maito等
host:主机
	服务器(计算机)域名系统 (DNS) 主机名或 IP 地址。
port:端口号
	整数，可选，省略时使用方案的默认端口，如http的默认端口为80。
path:路径
	由零或多个'/'符号隔开的字符串，一般用来表示主机上的一个目录或文件地址。
query:查询
	可选，用于给动态网页传递参数，可有多个参数，用'&'符号隔开，每个参数的名和值用'='符号隔开。例如：name=zs
fragment:信息片断
	字符串，锚点.
```

## history对象

History 对象包含用户（在浏览器窗口中）访问过的 URL。

主要负责页面的后退，前进

https://www.w3school.com.cn/jsref/dom_obj_history.asp

```
- back()
- forward()
- go()
```

## navigator对象

Navigator 对象包含有关浏览器的信息。

https://www.w3school.com.cn/jsref/dom_obj_navigator.asp

```
- userAgent

通过userAgent可以判断用户浏览器的类型

- platform

通过platform可以判断浏览器所在的系统平台类型.
```

# DOM

## 什么是dom

用来操作页面的

DOM节点是文档节点+标签节点+属性节点+注释节点+文本节点

dom树：

https://www.jianshu.com/p/0ec77136ec48

```
- 文档：一个网页可以称为文档
- 节点：网页中的所有内容都是节点（标签、属性、文本、注释等）
- 元素：网页中的标签
- 属性：标签的属性
```

## 获取页面元素

根据id获取元素

```javascript
//根据id获取元素

var div = document.getElementById('main');
console.log(div);

// 获取到的数据类型 HTMLDivElement，对象都是有类型的
// HTMLDivElement <-- HTMLElement <-- Element  <-- Node  <-- EventTarget
```

根据标签名获取元素

```javascript
var divs = document.getElementsByTagName('div');
for (var i = 0; i < divs.length; i++) {
  var div = divs[i];
  console.log(div);
}
```

根据name获取元素*

```javascript
var inputs = document.getElementsByName('hobby');
for (var i = 0; i < inputs.length; i++) {
  var input = inputs[i];
  console.log(input);
}
```

根据类名获取元素

```javascript
var mains = document.getElementsByClassName('main');
for (var i = 0; i < mains.length; i++) {
  var main = mains[i];
  console.log(main);
}
```

根据类名获取元素

```javascript
var text = document.querySelector('#text');
console.log(text);

var boxes = document.querySelectorAll('.box');
for (var i = 0; i < boxes.length; i++) {
  var box = boxes[i];
  console.log(box);
}
```

总结:

```
掌握
	getElementById()
	getElementsByTagName()
了解
	getElementsByName()
	getElementsByClassName()
	querySelector()
	querySelectorAll()
```

## 事件

事件：触发-响应机制

### 事件的基本使用

```javascript
var box = document.getElementById('box');
box.onclick = function() {
  console.log('代码会在box被点击后执行');  
};
```

### 注册/移除事件的三种方式

```javascript
var box = document.getElementById('box');
box.onclick = function () {
  console.log('点击后执行');
};
box.onclick = null;

box.addEventListener('click', eventCode, false);
box.removeEventListener('click', eventCode, false);

box.attachEvent('onclick', eventCode);
box.detachEvent('onclick', eventCode);

function eventCode() {
  console.log('点击后执行');
}
```

### js中的冒泡事件

从里向外进行触发事件
https://blog.csdn.net/u011482763/article/details/53377577

## 属性和方法

### innerHTML和innerText

document对象中有**innerHTML、innerText**这两个属性，都是获取document对象文本内容，但使用起来还是有区别的；

https://www.cnblogs.com/siduoxiaohua/p/10530876.html

### 非表单元素的属性

href、title、id、src、className

```javascript
var link = document.getElementById('link');
console.log(link.href);
console.log(link.title);

var pic = document.getElementById('pic');
console.log(pic.src);
```

### setAttribute()方法

setAttribute()方法把指定属性设置或更改为指定值。

https://blog.csdn.net/yhlysy/article/details/75194844

//将type的属性值改为text

```html
<script>

function change(){
var inp=document.getElementById("btn2"); 
inp.setAttribute("type","text");

}
    </script>
 
  <input type="button" id="btn2" value="插入节点" οnclick="change()">   
```

### scroll系列

scroll，滚动，一般讨论的是网页整体与浏览器之间的关系。

https://www.jianshu.com/p/cd5ba22a416d

https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&tn=baidu&wd=javascript%20scroll%E7%B3%BB%E5%88%97&oq=javascript%2520setAttribute()&rsv_pq=8cdea3b10010f926&rsv_t=a49f46ODytJDlwtgU3OBces7PunrPCzyVRkdoV1Oxf8tXBNOmOAyGSG9O4k&rqlang=cn&rsv_dl=tb&rsv_enter=1&rsv_btype=t&inputT=450&rsv_sug3=282&rsv_n=2&rsv_sug2=0&rsv_sug4=491

### client系列

client，最直接的，是客户端的意思。

Js中有一些系列的方法client的方法和属性。

https://www.jianshu.com/p/e6dc6bb1657e

### forEach() 方法

https://www.runoob.com/jsref/jsref-foreach.html

https://blog.csdn.net/qq_44034384/article/details/99290078

forEach() 方法用于调用数组的每个元素，并将元素传递给回调函数。

```javascript
<button onclick="numbers.forEach(myFunction)">点我</button>
<p id="demo"></p>
 
<script>
demoP = document.getElementById("demo");
var numbers = [4, 9, 16, 25];
 
function myFunction(item, index) {
    demoP.innerHTML = demoP.innerHTML + "index[" + index + "]: " + item + "<br>"; 
}
</script>



//index[0]: 4
//index[1]: 9
//index[2]: 16
//index[3]: 25
```



## HTML转义符

HTML转义符

```
"		&quot;
‘		&apos;
&		&amp;
<		&lt;    //less than  小于
>		&gt;   // greater than  大于
空格	   &nbsp;
©		&copy;
```

## js操作css

使用style方式设置的样式显示在标签行内

```javascript
var box = document.getElementById('box');
box.style.width = '100px';
box.style.height = '100px';
box.style.backgroundColor = 'red';
```

offest系列中的属性
比如获取css里面的长宽高
比如获取元素的宽：
document.getElementById("b21").offsetwidth

## js类名操作

修改标签的className属性相当于直接修改标签的类名

```javascript
var box = document.getElementById('box');
box.className = 'clearfix';
```

## js创建元素

document.write()

```javascript
document.write('新设置的内容<p>标签也可以生成</p>');
```

innerHTML

```javascript
var box = document.getElementById('box');
box.innerHTML = '新内容<p>新标签</p>';
```

document.createElement()

```javascript
var div = document.createElement('div');
document.body.appendChild(div);
```

## js节点

JavaScript中的节点是页面中所有的内容（标签、属性、文本（文字、换行、空格、回车））

### 操作

https://m.html.cn/qa/javascript/11377.html

```
元素节点（标签）

文本节点

属性节点（标签里的属性）
```

```javascript
var body = document.body;
var div = document.createElement('div');
body.appendChild(div);

var firstEle = body.children[0];
body.insertBefore(div,firstEle);

body.removeChild(firstEle);

var text = document.createElement('p');
body.replaceChild(text, div);
```

### 节点层级

重点讲父子属性，兄弟属性画图讲解

```javascript
var box = document.getElementById('box');
console.log(box.parentNode);
console.log(box.childNodes);
console.log(box.children);
console.log(box.nextSibling);
console.log(box.previousSibling);
console.log(box.firstChild);
console.log(box.lastChild);
```

```
- 注意

  childNodes和children的区别，childNodes获取的是子节点，children获取的是子元素

  nextSibling和previousSibling获取的是节点，获取元素对应的属性是nextElementSibling和previousElementSibling获取的是元素

  ​	nextElementSibling和previousElementSibling有兼容性问题，IE9以后才支持

- 总结
```

```
节点操作，方法
	appendChild()
	insertBefore()
	removeChild()
	replaceChild()
节点层次，属性
	parentNode
	childNodes
	children
	nextSibling/previousSibling
	firstChild/lastChild
```

### js克隆元素节点

https://blog.csdn.net/yuyecsdn/article/details/89636630

## js监控

### addEventListener（）

监控对象

https://blog.csdn.net/zenglintao/article/details/105909699

https://www.cnblogs.com/art-poet/p/12132078.html

https://www.runoob.com/jsref/met-element-addeventlistener.html

```javascript

//为 <button> 元素添加点击事件。 当用户点击按钮时，在 id="demo" 的 <p> 元素上输出 "Hello World" :

document.getElementById("myBtn").addEventListener("click", function(){
    document.getElementById("demo").innerHTML = 		"Hello World";
	});
```



## DOM小型项目原理

### 轮播图原理

ul图移动，无缝连接需要加多一个图，需要一个动态移动函数





# javascript-ES6和ES7

## ES6变动：面向对象

### class

es6新推出的概念，表示类，和java中的class很像

1.class关键字是es6推出的


2.class中的构造方法不能有两个及其以上

3.class中只能定义静态变量,如static info = 5

4.super()为父类的构造方法

### ES6中的多态

```javascript
var makeSound = function(animal) {
    animal.sound();
}

var Duck = function(){}
Duck.prototype.sound = function() {
    console.log('嘎嘎嘎')
}
var Chiken = function() {};
Chiken.prototype.sound = function() {
    console.log('咯咯咯')
}

makeSound(new Chiken());
makeSound(new Duck());
```

```javascript
class Person{
    constructor(name,age){
        this.name = name
        this.age = age
    }

    
    static info = 5
    say(){
        console.log("说话")
    }
    static stop(){
        console.log("禁止")
    }

    pp(){}
}

var person = new Person("张三",40)
person.say()
console.dir(Person)
console.dir(person)


class Baby extends Person{
    constructor(babyhight,name,age){
        super(name,age)
        this.babyhight=babyhight
    }

    seeBaby(){
        console.log(this.name+"---"+this.age+"岁---"+this.babyhight+"cm")
    }

    pp(){
        console.log("pp")
    }
}
var baby = new Baby(30,"小宝",1)
baby.seeBaby()
Baby.stop()
baby.pp()
```



## ES6变动：let与var与const

let是块作用域：

```
let a = 5;
if(true){
	let a = 8;
}

console.log(a)


//打印为5，因为a=8的a只在if中有效
```

```
var a = 5;
if(true){
	var a = 8;
}

console.log(a)

//打印8,因为var是全局作用域
```

看这个网站：

https://www.jianshu.com/p/84edd5cd93bd

const和let一样，是一个块级作用域，但不可变

## ES6变动：方法和属性的简写：

变动的：

```javascript
let name = 'zhangsan'
let app = {
    name,
    run(){
        console.log("名字是:"+this.name)
    }
}

app.run()
```

原来的：

```javascript
let name = 'zhangsan'
let app = {
    name : name,
    run:function(){
        console.log("名字是:"+this.name)
    }
}

app.run()
```

## ES6变动：箭头函数

看这个网站：

https://es6.ruanyifeng.com/#docs/function#%E7%AE%AD%E5%A4%B4%E5%87%BD%E6%95%B0

```javascript
var le =function Person() {  
    this.age = 10
    console.log(this.age)
    setInterval(() => {
        console.log("--"+this.age)
        this.age++;
        console.log("----"+this.age)
    }, 2000);
}
le()

//箭头函数中的this指向上一个函数的this
```

```javascript
let la = function pe(){
    console.log("---")
    console.log(this)
}

let las = ()=>{
    console.log("-------------")
    console.log(this)
}
la();
las();

//la中的this指向自己的函数，las的this则指向全局即使windows
```



## ES6变动：Promise处理异步

理解：

https://www.jianshu.com/p/1b63a13c2701
https://blog.csdn.net/qq_34645412/article/details/81170576

https://wangdoc.com/javascript/async/general.html

```javascript
function db(dbres,dbrej,jl,n,ms){
    setTimeout(() => {
        if(Math.random()<jl){
            dbres("第"+n+"次赌博赢了")
        }else{
            dbrej("失败，不赌了")
        }
    }, ms);
}

let p = new Promise(function(res,rej){
   db(res,rej,0.9,1,1000)
}) 

p.then((data)=>{
    console.log(data)
    return new Promise(function(res,rej){
        db(res,rej,0.9,2,1000)
    })
})
.then((data)=>{
    console.log(data)
    return new Promise(function(res,rej){
        db(res,rej,0.4,3,1000)
    })
})
.then((data)=>{
    console.log("不赌了，"+data)
},(err)=>{
    console.log(err)
})
```

promise简单使用
https://blog.csdn.net/weixin_39051908/article/details/103887982

## ES6变动：模板字符串

```javascript
console.log('姓名：${a.name}')
```

## ES7变动：async和await

await必须用在async方法里面

将一个方法变为异步方法

```javascript
async function getc(){
    return 'data'
}

console.log(getc())
 //返回：Promise { 'data' }
```

第一种获取async方法里面的数据

```javascript
async function getc(){
    return 'data'
}

getc().then((data)=>{
    console.log(data)
})
```

await是调用异步方法,await必须用在异步方法里面

第2种获取async方法里面的数据

```javascript
async function getc(){
    return 'data'
}

async function gete(){
    console.log(await getc())
}
gete()
```

await把异步方法变成同步，例子：

```javascript
async function getc(){
    console.log("2")
    return 'data'
}

async function gete(){
    console.log("1")
    console.log(await getc())
    console.log("3")
}
gete()

//打印1 .2 .data .3
```

await调用返回promise值，例子：

```javascript
let suv = ()=>{
    return new Promise((res,rej)=>{
        setTimeout(() => {
            let data = "zhangsan2"
            res(data)
        }, 1000);
    })
}

let spe = async ()=>{
    let pp = await suv();
    console.log(pp);
}

spe();

//返回zhangsan2
```

## js中的asymc/await/promise区别

https://segmentfault.com/a/1190000007535316

var [data,err] = "123123"
console.log(data)// "1"
console.log(err)// "2"

# javascript其他知识点

```
javascript一些比较难理解的知识点
https://www.cnblogs.com/ksunone/p/7273037.html


js33个概念
https://github.com/stephentian/33-js-concepts


js动画引擎
https://github.com/juliangarnier/anime


js 对象的属性key
https://www.cnblogs.com/wxcbg/p/10453215.html


js 双引号里面有双引号的解决方法
http://ask.zol.com.cn/x/4640863.html


红宝书js要看的


javsscript
iscroll插件为滚动插件


js开发必备插件vscode
https://www.cnblogs.com/sexintercourse/p/9521946.html


jq局部刷新
https://www.jianshu.com/p/86cc8892a812


防止无限定时器占用内存
let rty = setInterval(() => {
				dels()							
				clearInterval(rty)				
			}, 500);
			
			
			
js setCookie和getCookie
https://blog.csdn.net/qq_29301417/article/details/78684649

<a href="{url 'user/logout'}"><i class="fa fa-sign-out 
color-gray"></i> 退出系统</a>	



javascript：
对象内方法的三种写法：
	uni.getSystemInfo({
				success:(res)=>{
					console.log(res)
					console.log(res.model)
				}
			})

，

uni.getSystemInfo({
				success:function(res){
					console.log(res)
					console.log(res.model)
				}
			})
，

uni.getSystemInfo({
				success(res){
					console.log(res)
					console.log(res.model)
				}
			})


js的change事件
https://blog.csdn.net/weixin_45217584/article/details/92612406

```

