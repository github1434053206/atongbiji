# 安装和学习

看nodejs笔记下的：

 [【课件】NodeJs 介绍 安装 开发工具配置.pdf]([课件]NodeJs 介绍 安装 开发工具配置.pdf) 

中文：

直接百度搜索vscode中文

学习

nodejs
nodejs学习网
https://www.bilibili.com/video/av38925557?from=search&seid=12559705803152959636

nodejs
nodejs廖雪峰学习网
https://www.liaoxuefeng.com/wiki/1022910821149312/1099503821472096

node环境：
直接下载就可以，用node,npm
http://nodejs.cn/
https://www.runoob.com/nodejs/nodejs-install-setup.html

# 		http模块 	

```
//request获取客户端传过来的信息
//responese返回客户端的信息
//构建http服务器
var http = require('http');//引入http模块
http.createServer(function (request, response) {//该函数用来创建一个HTTP服务器，并将 requestListener 作为 request 事件的监听函数
    console.log(request.url);

    // 发送 HTTP 头部
  // HTTP 状态值: 200 : OK
  //设置 HTTP 头部，状态码是 200，文件类型是 html，字符集是 utf8
    response.writeHead(200, {'Content-Type': 'text/plain'});
    
    //结束，反馈
  response.end('Hello World');
}).listen(8081);//设置端口为8081
```

# url模块

```
const ur = require('url')

let urs = "htttp://www.baidu.com?name=阿通&age=25"


//第二个参数为true，query属性会生成一个对象，如果为false,则返回url对象上的query属性会是一个未解析，未解码的字符串，默认为false
console.log("------------------------")
console.log(ur.parse(urs,true).query)
console.log("姓名："+ur.parse(urs,true).query.name)
console.log("年龄："+ur.parse(urs,true).query.age)
console.log("------------------------")
```

# supervisor

用来预加载的程序

安装：

npm install -g supervisor

使用supervisor代替npm命令

# 安装cnpm

https://developer.aliyun.com/mirror/NPM?from=tnpm去这个网站，复制npm下载命令

# 生成**package.json**

npm init --yes

# Fs模块

**const** ***fs*** = *require*(**'fs'**)

看fs模块的pdf：【课件】Nodejs中的fs模块的使用

# npm常用模块之mkdirp使用

https://www.cnblogs.com/jiaoshou/p/12187136.html

# **Nodejs** **新特性** async await

```
console.log("------------------------1")
function getData(){ 
  console.log("11")
    return 'zhangsan'; 
}
async function testAsync(){ 
  console.log("112")
  return 'Hello async'; 
}
async function test(){
   const v1=await getData(); 
const v2=await testAsync(); 

console.log("--",testAsync())
console.log(v2); 
console.log("zzz");

}
test();
console.log("------------------------1")
//----------------------------------
let pi =require('./mk.js')
console.log("------------------------")
console.log(pi.apis());
console.log("------------------------")
```

```

```

# Promise

攻略：

https://segmentfault.com/a/1190000007032448

基本理解：

```
function sendRequest(a,b) {
    return new Promise(function (resolve, reject) {
        if(a>b){
            resolve("yes")
        }else{
            reject("出现错误")
        }

    });
}

sendRequest(1,2).then(function(data) {
    //异步操作成功后的回调
    console.log('请求成功啦, 这是返回的数据:', data);
    console.log("----2")
}, function(error) {
    //异步操作失败后的回调
    console.log('sorry, 请求失败了, 这是失败信息:', error);
    console.log("----2")
});

sendRequest(3,2).then(function(data) {
    //异步操作成功后的回调
    console.log('请求成功啦, 这是返回的数据:', data);
    console.log("----2")
}, function(error) {
    //异步操作失败后的回调
    console.log('sorry, 请求失败了, 这是失败信息:', error);
    console.log("----2")
});
```

```
//第2种理解,catch,then
function sendRequest(a,b) {
    return new Promise(function (resolve, reject) {
        if(a>b){
            resolve("yes")
        }else{
            reject("出现错误")
        }

    });
}

sendRequest(2,1).then(function(data) {
    //异步操作成功后的回调
    console.log('1请求成功啦, 这是返回的数据:', data);
    return sendRequest(3,2);
}).then(function(data){
    console.log('2请求成功啦, 这是返回的数据:', data);
    return sendRequest(4,3);
}).then(function(data){
    console.log('3请求成功啦, 这是返回的数据:', data)
    return sendRequest(5,3);
}).catch(function(error) {
    //用catch捕捉前面的错误
    console.log('error', error);
});
```

```
//throw等同于reject
/* 例3.4 */
var promise = new Promise(function (resolve, reject) {
    throw new Error('test');
});
/*******等同于*******/
var promise = new Promise(function (resolve, reject) {
    reject(new Error('test'));
});

//用catch捕获
promise.catch(function (error) {
    console.log(error);
});
-------output-------
Error: test
```



# 异步操作与同步操作

异步操作只会在同步操作完成后才操作

# 利用 HTTP 模块 URl 模块 PATH 模块 FS

看pdf笔记文件

# event模块

```
var events = require('events');
var EventEmitter=new events(); /*实例化事件对象*/


EventEmitter.on('123',function(){
 console.log('接收到了123事件');
})
setTimeout(function(){
 console.log('123');
 EventEmitter.emit('123'); /*发送广播*/
},1000)
```

看：

https://www.cnblogs.com/starof/p/5035522.html

和pdf

# callback回调函数

```
function doSomething(msg, callback){
   console.log(msg);
   if(typeof callback == "function") {
      console.log("2")
      callback();
   }
 
} 
doSomething("回调函数", function(){
   console.log("1")
   console.log("匿名函数实现回调!");
}); 

//
function(){
   console.log("1")
   console.log("匿名函数实现回调!");
}需要有人调用
///
```

# npm

```
npm中的package.json
https://www.jianshu.com/p/d128c75b5bf1


npm中的--save的意思是把包写入package.json中



npm i命令是把项目需要的依赖找回来，如果没有发node_modules文件夹，则可以通过Npm i将依赖包找回来，但必须在package.json中dependecies中有的包



NPM官方
https://www.npmjs.cn/getting-started/installing-node/

```



# node操作mongodb数据库

看这个网站

https://www.cnblogs.com/loaderman/p/11505187.html

# 其他笔记

```
nodejs ejs模块引擎
cnpm install ejs --save
```

```
nodejs热加载
supervisor app.js
```

```
nodejs默认会找node_modules对应用快里面的index.js
```

```
nodejs+ex[ress+mongodb
https://www.bilibili.com/video/av81421067?

from=search&seid=12559705803152959636
```

```
node sn 为提示工具
```

