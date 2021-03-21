# 学习教程



# 其他笔记

```
call()、apply()、bind():
都是调用方法，并且可改其中的this值

重要：
箭头函数和普通函数的this
https://www.cnblogs.com/xxcn/p/11056495.html


js和ts的区别
https://www.cnblogs.com/jiasm/p/9348539.html
https://www.cnblogs.com/stone-lyl/p/9542126.html

js的Null和undefind
https://www.cnblogs.com/ainyi/p/9510426.html

js继承


vuecli写ts
https://cloud.tencent.com/developer/article/1512871

ts元组类型
http://www.softwhy.com/article-7684-1.html

在vsCode中创建ts
1.创建index.ts 
2.npm install -g typescript
3.tsc --init
4.改json文件的outdir为：“./js”
5.点击任务 - 运行任务，监视tsconfig.json

let wu:number | string | undefined
wu有可能是number或undefined或string

never类型：
https://blog.csdn.net/cuishizun/article/details/81564294
引用的作用域大于等于对象的作用域
例如
Father a = new chidren();//向上转型
Chidren chi = (Chidren ) a ;//向下转型
因为引用的箭头要指向对象
Chidren chi2 = new Father();//报错
作用域问题引用永远大于等于对象的作用域
never类型同理，never是所有对象的子集
所以：
let a:never = 123 //报错，原因在于引用的作用域需要大于等于对象的作用域

函数重载
https://blog.csdn.net/qq_38735649/article/details/88573202
```



