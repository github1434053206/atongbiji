# less介绍和安装

## ACE框架

没看

## LESS官网

http://lesscss.org/

中文网站：

http://lesscss.cn/

## LESS指南

less需要服务器上才能运行，就是要有路由才能运行

# less语法

## 变量

@后面接变量

@hc:“www.baidu.com”

```
@hc:green;
#header{
    color: @hc;
}
```

## 作用域

如果对同一个变量定义两次的话，在当前作用域中最后一次定义的将被使用。这 

不 CSS 的机制类似，最后一次定义的值会成为这个属性的值。若定义在嵌套乊中， 

那么这个变量就叧能服务亍这个嵌套乊内的属性了。变量也是没有顺序可言的，叧要 

页面里有，都会按顺序覆盖，按顺序加载

```less
@hc:green;

h2{
    @hc:red;
    color: @hc;
    }
```

## 选择器插值

选择器用变量表示

```less
@qc:get;
.@{qc}{
    color: blue;
}
```

## LESS响应式布局

https://www.cnblogs.com/grt322/articles/9354611.html

## 引用变量值的变量

```less
@meng:green;
@mengto:meng;
h3{
    color: @@mengto;
}
```

## less继承

### less的继承

```less
.yeso{
    color: yellow;
}
#yesoid{
    .yeso;
}

```

### 带参数继承

多个参数也可以

```less
.beticolor(@colo){
    color: @colo;
}
#becol{
    .beticolor(yellow);
}
```

### 隐藏参数继承

```less
.beticolor(){
    color: yellow;
}
#becol{
    .beticolor();
}

```

### 默认值参数继承

```less
.beticolor(@ews:yellow){
    color: @ews;
}
#becol{
    .beticolor();
}
```

## argumengts变量

argumengts变量代表所有参数

```less
.xcbor(@width:2px,@sot:solid,@color:red){
    border: @arguments;
    background-color: blue;
    width: 50px;
    height: 50px;
}


#hahadiv{
    .xcbor(@width:15px,@color:green);
}
```

## less动态参数

```less
.xcbor(...){
    background-color: @arguments;
    width: 50px;
    height: 50px;;
   
}

#hahadiv{
    .xcbor(red);
}
```

# 只学完less课程第19课，以后学习