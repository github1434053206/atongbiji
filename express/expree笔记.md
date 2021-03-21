# 安装

中文官网：

https://www.expressjs.com.cn/

# cmd代码生packgage.json

npm init --yes

# get和post请求

https://www.zhihu.com/question/28586791

最基本的解释：get是向服务器端请求数据，post是提交数据。

# 幂等性

https://www.jianshu.com/p/9d46a730284e

HTTP 幂等方法，是指无论调用多少次都不会有不同结果的 HTTP 方法。不管你调用一次，还是调用一百次，一千次，结果都是相同的。

# express的路由

看pdf：

Express 框架介绍 安装 路由 动态路由 get传值

```
var express = require('express');
var app = express();
app.get('/', function (req, res) {
      res.send('Hello World!'); 
});
app.post("/post",function(req,res){
    console.log("post!")
    res.send('post!');
 });

console.log("服务器启动成功")
app.listen(3000,'127.0.0.1');
```

# EJS模板引擎

网站：npmjs.com/package/ejs

看pdf：

Express 框架介绍 安装 路由 动态路由 get传值

# send方法

看：

https://zhuanlan.zhihu.com/p/143746550

https://www.cnblogs.com/tomotose/p/5109987.html

# 中间件

看pdf：

Express 框架介绍 安装 路由 动态路由 get传值

合视频：https://www.bilibili.com/video/BV11t411k79h?p=30

```
中间件就是辅助作用的，在访问路由前或者访问路由后执行

应用级中间件 :访问路由前执行

路由级中间件 ：当A合B路由冲突的时候，由A路由跳到B路由

错误处理中间件 ：访问路由后出现错误后执行的中间件

内置中间件 ：访问静态文件的中间件

第三方中间件：第三方的中间件
```

# Cookie

看pdf:

Express Cookie的基本使用.pdf

# Session

Session的数据存在服务器中，session的id存到浏览器的cookie中，但数据在服务器中

看pdf：

Express  Session的基本使用.pdf

和这个网站：

https://www.zhihu.com/question/19786827

```
/*session的使用：
https://www.npmjs.com/package/express-session
1、cnpm install express-session --save

2、const session = require('express-session')


3、配置session的中间件

app.use(session({
    secret: 'this is session', //服务器端生成 session 的签名
    name:"itying", //修改session对应cookie的名称
    resave: false, //强制保存 session 即使它并没有变化
    saveUninitialized: true, //强制将未初始化的 session 存储
    cookie: { 
        maxAge:1000*60*30,
        secure: false  // true 表示只有https协议才能访问cookie  
    },
    rolling:true  //在每次请求时强行设置 cookie，这将重置 cookie 过期时间（默认：false）
}))

4、使用
 设置： req.session.username="张三"

 获取：req.session.username

  
 删除session  req.session.username=""

*/

```

# 将session放入mongodb数据库，以便分布式服务器读取

看pdf:

Express  Session的基本使用.pdf

合网站：

https://www.bilibili.com/video/BV11t411k79h?p=33

```
/*
session保存在数据库里面

https://www.npmjs.com/package/connect-mongo

1、配置express-session

2、安装connect-mongo 
    cnpm i connect-mongo --save

3、引入
const MongoStore = require('connect-mongo')(session);

4、配置中间件
    app.use(session({
        secret: 'this is session', //服务器端生成 session 的签名
        name:"itying", //修改session对应cookie的名称
        resave: false, //强制保存 session 即使它并没有变化
        saveUninitialized: true, //强制将未初始化的 session 存储
        cookie: { 
            maxAge:1000*60*30,
            secure: false  // true 表示只有https协议才能访问cookie  
        },
        rolling:true,  //在每次请求时强行设置 cookie，这将重置 cookie 过期时间（默认：false）
        store: new MongoStore({
            url: 'mongodb://127.0.0.1:27017/shop',      
            touchAfter: 24 * 3600 // 不管发出了多少请求 在24小时内只更新一次session， 除非你改变了这个session 
        })
    }))


    https://www.npmjs.com/package/connect-redis

    https://www.npmjs.com/package/connect-mysql


*/


const express = require('express')
const session = require('express-session')
const MongoStore = require('connect-mongo')(session);
const app=express()
//配置session的中间件
app.use(session({
    secret: 'this is session', //服务器端生成 session 的签名
    name:"itying", //修改session对应cookie的名称
    resave: false, //强制保存 session 即使它并没有变化
    saveUninitialized: true, //强制将未初始化的 session 存储
    cookie: { 
        maxAge:1000*60*30,
        secure: false  // true 表示只有https协议才能访问cookie  
    },
    rolling:true,  //在每次请求时强行设置 cookie，这将重置 cookie 过期时间（默认：false）
    store: new MongoStore({
        url: 'mongodb://127.0.0.1:27017/shop',      
        touchAfter: 24 * 3600 // 不管发出了多少请求 在24小时内只更新一次session， 除非你改变了这个session 
    })
}))

app.get("/",(req,res)=>{
    //获取seesion
    if(req.session.username || req.session.age){
        res.send(req.session.username+"--"+req.session.age+"-已登录")        
    }else{
        res.send("没有登录")
    }
})

app.get("/login",(req,res)=>{  
    //设置seesion
    req.session.username="张三"
    req.session.age=20
    res.send("执行登录")
})

app.get("/loginOut",(req,res)=>{  
    //1、设置session的过期时间为0  (它会把所有的session都销毁)
    // req.session.cookie.maxAge=0

    //2、销毁指定session
    // req.session.username=""

    //3、销毁session  destroy

    req.session.destroy()

    res.send("退出登录")
})
app.listen(3000)
```

# 外部用一个文件存储全部路由

看：

https://www.bilibili.com/video/BV11t411k79h?p=34

看pdf和txt

Express应用程序生成器 以及路由模块化.pdf

# express图片上传，件、按照日期生成存储目录

看：

https://www.bilibili.com/video/BV11t411k79h?p=35

看pdf：

Express 结合multer上传文件、按照日期生成存储目录.pdf

