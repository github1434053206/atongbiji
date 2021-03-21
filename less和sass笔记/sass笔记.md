# 安装

看pdf

CSS 框架之 Sass 全面解析.pdf

ruby官网：

https://rubyinstaller.org/downloads/



或者不安装ruby直接用sass

https://blog.csdn.net/qq_40259641/article/details/84979821

#   SASS语法

## 嵌套语法

```scss
.oie{
    .h1s{
        color: red;
    }
    #ope{
        color: blue;
    }
}
```

## 父选择器和标识符

&代表父选择器

```scss
.h1s{
    color: blue;
    &:hover{
        color: red;
    }
}
```

## 群组选择器

```scss
.oie{
    h1,h2,h3{
        color: green;
    }
}
```

## Sass 子组合选择器和同层组合选择器：>、+和~

看https://www.axihe.com/edu/sass/nested/selector.html

## 属性嵌套

看sass的pdf

## import导入

给另一个scss文件导入scss文件

a文件:

```scss
$bco: blue;
```

b文件：

```scss
@import "a";
.oie{
    h1,h2,h3{
        color:$bco;
    }
}
```

## if条件语句

```scss
.oie{
    @if 1+1==2{
        width: 200px;
        height: 200px;
        background-color: red;
    }
}
```

## for循环

```scss
.oie{
    @for $var from 1 to 250 {
        width: #{$var}px;
        height: #{$var}px;
    }
}
```



# 混合器

## 混合器的定义和食用

用@mixin定义，用@include使用

```scss
@mixin grco {
    color: green;
}

.oie h2{
    @include grco;
}
```

## 混合器传参

```scss
@mixin grco($grr) {
    color: $grr;
}
 
.oie h2{
    @include grco(red);
}
```

## 混合器传参默认参数

```scss
@mixin grco($grr:blue) {
    color: $grr;
}

.oie h2{
    @include grco();
}
```

# SASS继承

## 普通继承

用@extend关键词继承

```scss
.divwh{
    width: 500px;
    height: 500px;
}
.grenba{
    background-color: green;
}
.oie{
    @extend .divwh,.grenba;
}
```

## "%"用法及指令作用域问题

看pdf

# SASS函数

## 内置函数

### unquote()函数

去除""双引号

```scss
.oie{
    color: unquote("blue");
}
```

### 数字函数

看pdf

### 列表函数

看pdf

### 三元函数

看pdf

### 颜色函数

看pdf

## 自定义函数

@function

```scss
@function dou($num){
    @return $num * 2
}

.oie{
    width: dou(50px);
    height: dou(50px);
    background-color: red;
}
```

