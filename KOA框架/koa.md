# KOA官网

www.itying.com/koa

cnpm install --save koa

# 运行koa

```
var koa = require('koa')

var app =new koa()

app.use(async(ctx)=>{
    ctx.body = 'nihao koa';
})

console.log("koa运行成功")
app.listen(8080)
```

# let与var

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

# 未学完

有空再学，看181前端视频koa的