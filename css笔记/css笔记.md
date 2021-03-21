# Css基础

可以看css参考手册

 [CSS参考手册.chm](CSS参考手册.chm) 

## 什么是css

css就是页面的装饰，就像装饰人的衣服裤子一样

## css选择器

w3c指导：https://www.runoob.com/cssref/css-selectors.html

### 基础选择器

https://www.cnblogs.com/haiyan123/p/7552235.html

主要有四类选择器是基础选择器：

```jafva
通用元素选择器 *: 所有的标签都变色

标签选择器：匹配所有使用p标签的样式 p{color:red}

id选择器：匹配指定的标签  #p2{color:red}

class类选择器：谁指定class谁的变色，可选多个  .c1{color:red} 或者 div.c1{color:red}
```

### 组合选择器

https://www.cnblogs.com/haiyan123/p/7552235.html

http://www.ruanyifeng.com/blog/2009/03/css_selectors.html

```
1.后代选择器 (不分层级，只让p标签变色) .c2 p{color:red} 
    
2.子代选择器（只在儿子层找） .c2>p{color:red}
    
3.多元素选择器：同时匹配所有指定的元素  .div,p{color:red}
　　　　　　　　　　　　　　　　　　　　　　　或者
　　　　　　　　　　　　　　　　　　　　　　　　.c2 .c3,.c2~.c3{
　　　　　　　　　　　　　　　　　　　　　　　　　　　color: red;
　　　　　　　　　　　　　　　　 　　　　　　　　　　 background-color: green;
　　　　　　　　　　　　　　　　　　　　　　　　　　　font-size: 15px;
　　　　　　　　　　　　　　　　}

 
    不常用    
3.毗邻选择器（紧挨着，找相邻的,只找下面的，不找上面的）.c2+p{color:red}

4.兄弟选择器：同一级别的，离得很近的.c2~p{color:red}

5.多元素选择器： .c2 .c3,.c2~ .c3{ color:red }
```

### 属性选择器

https://www.cnblogs.com/haiyan123/p/7552235.html

```
/*1.匹配所有haiyan属性的，并且只是在div标签的*/
div[haiyan]{
    color: yellowgreen;
}
```

### 伪类选择器

用：表示

https://www.jianshu.com/p/7d86345ac877

https://segmentfault.com/a/1190000000484493

https://segmentfault.com/a/1190000014066147?utm_source=channel-hottest

### 伪元素选择器

用：：表示

https://www.jianshu.com/p/7d86345ac877

https://segmentfault.com/a/1190000000484493

https://segmentfault.com/a/1190000014066147?utm_source=channel-hottest

### 伪类选择器和伪元素选择器的区别

https://segmentfault.com/a/1190000000484493

https://www.cnblogs.com/lovemomo/p/4878304.html

https://www.cnblogs.com/zcynine/p/5008985.html

## 通用css

### 渐变

```css
background: linear-gradient(0deg,red,orange,yellow,green,  #00ffff,blue,purple);
```

### 过渡效果

https://www.cnblogs.com/shiweida/p/7785185.html

```css
div{
    width: 200px;
    height: 200px;
    background-color: red;
    /*添加单个过渡效果*/
    /*transition:background-color 2s;*/
    /*也可以同时设置多个过渡效果*/
    /*transition:background-color 2s,left 1s;*/
    /*可以设置某个过渡效果的延迟*/
    /*transition:background-color 2s,left 1s 1s;*/
    /*可以设置过渡效果的速率曲线*/
    /*transition:background-color 2s,left 1s ease-out 1s;*/
    /*还可以一次性的为所有属性添加过渡效果*/
    transition:all 1s;
    position: absolute;
    left: 0;
    top: 0;
}
```

### 2D转换

https://blog.csdn.net/A20190518/article/details/98979987

https://www.cnblogs.com/programInit/p/6863885.html

2D移动：translate()

#### 2d缩放

```css
div:hover{
    /*传入两个值，第一个参数表示X方向的缩放 第二个参数表示Y方向上的缩放*/
    /*transform: scale(2,0.5);*/
    /*也可以只传入一个值，表示X方向和Y方向上相同的缩放*/
    /*transform: scale(2);*/
    /*也可以指定具体方向上的缩放*/
    transform: scaleX(2);
}
```

#### 2d旋转

```css
div:hover{
    /*传入旋转的角度，如果正值，则进行顺时针旋转*/
    /*transform: rotate(90deg);*/
    /*如果传入负值，则逆时针旋转*/
    transform: rotate(-270deg);
}
```

#### 2d翻转

```css
div:hover{
    /*在X方向上倾斜30度*/
    transform: skewX(30deg);
}
```

### 3D转换

三维变换使用基于二维变换的相同属性，可以让我们基于三个坐标方向对元素进行变换。和二维变形一样，三维变形可以使用transform属性来设置

https://www.cnblogs.com/shiweida/p/7785185.html

#### 3d移动

```css
div:hover{
    /*Y轴移动+100px*/
    /*transform:translateY(100px);*/
    /*X轴移动100px*/
    /*transform:translateX(100px);*/
    /*x轴和Y轴方向同时移动*/
    transform:translate3d(100px,100px,0px);
}
```

#### 3D缩放

```css
div:hover{
    /*Y轴方向放大1倍*/
    /*transform: scaleX(2);*/
    /*X轴方向缩小0.5*/
    /*transform: scaleX(0.5);*/
    /*x轴和Y轴方向同时进行缩放*/
    transform: scale3d(2,0.5,1);
}
```

#### 3D旋转

```css
div:hover{
    /*Y轴方向旋转45度*/
    /*transform: rotateY(45deg);*/
    /*X轴方向旋转90度*/
    /*transform: rotateX(90deg);*/
    /*x轴和Y轴方向同时进行旋转放*/
    transform: rotate3d(1,1,0,45deg);
}
```

### css清除浮动

html代码

```html
 <div class="zx zxb">
        <div class="zx1"></div>
        <div class="zx2"></div>
      </div>
```

css代码

```css
.zx{
  border:1px solid #000;
}

.zxb::after{
  content: "";
 display: table;
 /* 闭合浮动 */
 clear: both;
}

.zx1{
  height: 200px;
  width: 100px;
  background-color: blue;
  float: left;
}

.zx2{
  height: 200px;
  width: 100px;
  background-color: red;
  float: left;
}
```

## 动画

[animation](https://www.html.cn/book/css/properties/animation/animation.htm)

w3c:https://www.w3school.com.cn/css3/css3_animation.asp

https://www.jianshu.com/p/15f2adfbdad0

创建动画：

https://www.w3school.com.cn/cssref/pr_keyframes.asp

```
@keyframes：
创建动画

@keyframes rotate{
	0%{
	transform:rotate(0deg)
}

	100%{
transform:rotate(360deg)
}
}
```



```css
动画是CSS3中具有颠覆性的特征之一，可通过设置多个节点来精确控制一个或一组动画，常用来实现复杂的动画效果.


1.必要元素：
a、通过@keyframes指定动画序列；自动补间动画，确定两个点，系统会自动计算中间过程。这两个点就称为关键帧。我们可以设置多个关键帧
 b、通过百分比将动画序列分割成多个节点；
 c、在各节点中分别定义各属性
 d、通过animation将动画应用于相应元素；
 
 
2.animation样式常用属性：
a)动画序列的名称:animation-name: move;
b)动画的持续时间:animation-duration: 1s;
c)动画的延时:animation-delay: 1s;
d)播放状态:animation-play-state: paused|running;
e)播放速度:animation-timing-function: linear;
f)播放次数 反复:animation-iteration-count: 1;
g)动画播放完结后的状态:animation-fill-mode: forwards;
h)循环播放时，交叉动画:animation-direction: alternate;
```

```css
<style>
    *{
        padding: 0;
        margin: 0;
    }
    div{
        width: 300px;
        height: 300px;
        margin:100px auto;
    }
    div > img{
        width:100%;
    }
    /*添加动画*/
    @keyframes rotateAni {
        0%{
            /*可以同时对多个属性添加动画效果*/
            transform: rotate(0deg) scale(1);
        }
        50%{
            transform: rotate(180deg) scale(2);
        }
        100%{
            transform: rotate(360deg) scale(1);
        }
    }
    div:hover > img{
        /*动画名称-自定义*/
        animation-name: rotateAni;
        /*动画时间*/
        animation-duration: 1s;
        /*动画速率曲线： linear：匀速  ease：动画以低速开始，然后加快，在结束前变慢  ease-in：动画以低速开始  ease-out：动画以低速结束  ease-in-out：动画以低速开始和结束*/
        animation-timing-function: linear;
        /*动画播放次数*/
        animation-iteration-count: 4;
        /*动画时间延迟*/
        animation-delay: 0s;
        /*动画播放完的状态：  forwards:保持动画播放完毕后的状态 backwards:退回到原始状态(默认值)*/
        animation-fill-mode: forwards;
        /*动画是否轮流反射播放：  alternate:在规定的次数内轮流反射播放  normal:正常播放*/
        /*animation-direction: alternate;*/
    }
    div:active >img{
        /*动画的当前播放状态：  paused：暂停  running:运行*/
        animation-play-state: paused;
    }
</style>
```

#### 动画插件

http://www.mamicode.com/info-detail-1793104.html

## 字体

看css笔记3.docx

```
下载字体图标文件：如https://www.awesomes.cn/的网站的介绍和使用
```

自定义字体

```css
/*定义字体图标*/
@font-face {
    font-family: 'wjs'; //自定义的字体名称
    src: url('../fonts/MiFie-Web-Font.eot'); /* IE9*/
    src: url('../fonts/MiFie-Web-Font.eot') format('embedded-opentype'), /* IE6-IE8 */
    url('../fonts/MiFie-Web-Font.woff') format('woff'), /* chrome、firefox */
    url('../fonts/MiFie-Web-Font.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
    url('../fonts/MiFie-Web-Font.svg') format('svg'); /* iOS 4.1- */
}
```

通过css样式使用字体

```css
/*自定义字体图标*/
.wjs_font_icon{
    font-family: wjs; //这里对应着自定义的字体名称
}
/*手机图标对应的编码*/
.wjs_font_icon_phone::before{
    content: "\e908"; //指定显示的内容
}
```

## css布局

水平

display讲解：

```
https://www.cnblogs.com/Ry-yuan/p/6848197.html
inline（行内元素）:
使元素变成行内元素，拥有行内元素的特性，即可以与其他行内元素共享一行，不会独占一行. 
不能更改元素的height，width的值，大小由内容撑开. 
可以使用padding上下左右都有效，margin只有left和right产生边距效果，但是top和bottom就不行.
block（块级元素）:
使元素变成块级元素，独占一行，在不设置自己的宽度的情况下，块级元素会默认填满父级元素的宽度. 
能够改变元素的height，width的值. 
可以设置padding，margin的各个属性值，top，left，bottom，right都能够产生边距效果.
 inline-block（融合行内于块级）:
结合了inline与block的一些特点，结合了上述inline的第1个特点和block的第2,3个特点.
用通俗的话讲，就是不独占一行的块级元素。如图:
```

```
html:
position:fiexd布局
是固定布局，就是一直固定在那里的一个组件
就像抖音首页的右边点赞，关注，头像等固定组件
```



### 栅格布局

参加bootstrap

### 多列布局

CSS3中新出现的多列布局(multi-column)是传统HTML网页中块状布局模式的有力扩充。这种新语法能够让WEB开发人员轻松的让文本呈现多列显示。我们知道，当一行文字太长时，读者读起来就比较费劲，有可能读错行或读串行；人们的视点从文本的一端移到另一端、然后换到下一行的行首，如果眼球移动浮动过大，他们的注意力就会减退，容易读不下去。所以，为了最大效率的使用大屏幕显示器，页面设计中需要限制文本的宽度，让文本按多列呈现，就像报纸上的新闻排版一样

```
1.常用属性：
a)column-count: 属性设置列的具体个数
b)column-width: 属性控制列的宽度
c)column-gap: 两列之间的缝隙间隔
d)column-rule: 规定列之间的宽度、样式和颜色
e)column-span: 规定元素应横跨多少列(n:指定跨n列  all:跨所有列)
```

```css
<style>
    *{
        padding: 0;
        margin: 0;
    }
    .wrapper{
        width:1054px;
        padding:20px;
        margin:0 auto;
        font-family: "微软雅黑",Arial;
        /*设置以几列的方式显示*/
        column-count:2;
        /*指定列宽*/
        column-width:500px;
        /*指定列与列之间的间距*/
        column-gap: 50px;
        /*指定列与列之间间隙的样式*/
        /*column-rule:2px dotted red*/
        /*相对应下面的三个属性*/
        column-rule-color:red;
        column-rule-style:dotted;
        column-rule-width:2px;
    }
    .wrapper > h4{
        column-span: all;
    }
</style>
```

### flex伸缩布局（重点）

布局的传统解决方案，基于[盒状模型](https://developer.mozilla.org/en-US/docs/Web/CSS/box_model)，依赖 [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)属性 + [position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)属性 + [float](https://developer.mozilla.org/en-US/docs/Web/CSS/float)属性。它对于那些特殊布局非常不方便。CSS3在布局方面做了非常大的改进，使得我们对块级元素的布局排列变得十分灵活，适应性非常强，其强大的伸缩性，在响应式开中可以发挥极大的作用。

```
https://www.jb51.net/css/632494.html
flex属性，伸缩布局要用
常用属性：
display: flex;
flex: 1;
还有其他
```

```
flex布局子元素被撑开的解决方案：
https://blog.csdn.net/Zoey_J/article/details/100983674

flex布局：
https://zhuanlan.zhihu.com/p/25303493

flex布局居中：
http://www.divcss5.com/jiqiao/j52666.shtml
```

模板代码：

```css
//父元素：
display: flex;
    flex-wrap:wrap;
    justify-content:center;
    align-items:center;
    flex-direction:row;

display:block; /*转换为块级*/
display:inline; /*转换为行内*/

//去掉某个元素的属性：initial
.demo{
       float:initial !important;
    }

```

问题和方法：

```
flex布局
当超出行时还整齐对齐的方法
    text-align: justify;
```

### css响应式布局

https://blog.csdn.net/gtlishujie/article/details/81975

```css
/* 响应式 */
@media screen and (max-width: 1068px){
    
    .about-info {
    padding-left: 10px;
    padding-right: 10px;
        text-align: center;
    font-size: 14px;
    line-height: 34px;
    color: #666;
    padding-bottom: 50px;
}
```

### 流式布局

就是百分比布局，非固定像素，内容向两侧填充，理解成流动的布局，称为流式布局

流式布局：就是百分比布局，非固定像素，内容向两侧填充，理解成流动的布局，称为流式布局*/
        /*视觉窗口：viewport,是移动端特有。这是一个虚拟的区域，承载网页的。
          承载关系：浏览器---->viewport---->网页

### rem布局（移动端特有）

移动端特有

适配方案rem：宽度和高度都能做到适配（等比缩放）

```
<!--通过控制html上的字体大小去控制页面上所有已rem为单位的基准值控制尺寸-->
<!--4.1 把页面上px单位转换成rem单位-->
<!--4.2 页面制作的时候 psd 上的量取的px转成rem使用-->
<!--4.3 怎么换算？？？预设一个基准值 方便计算 100px -->
<!--4.4 适配的时候设置基准值  320px  50px 怎么算：（640px 100px ===320px 50px）-->
<!--4.5 换算公式：当前rem基准值 = 预设的基准值 / 设计稿宽度 * 当前设备的宽度 -->
<!--4.6 怎么去改变 （js换算，媒体查询推荐）-->
```

```
/*1.rem是相对单位*/
        /*2.em大小是基于父元素的字体大小*/
        /*3.rem的大小是基于？？？*/
        /*4.浏览器默认的字体大小是16px*/
        /*5. r 意思 root 根元素，html标签 */
        /*6. rem的大小是基于html元素的字体大小*/
```



### 栅格布局

-----boostraap

## css关键字

#### !important关键字

!important为开发者提供了一个增加样式权重的方法

https://www.cnblogs.com/planetwithpig/p/11804355.html

# Css中的常用属性与方法

```
将border的大小算在width中

box-sizing：border-box的含义

https://www.cnblogs.com/lovekiku123/p/11909327.html

https://www.cnblogs.com/less-yang/p/7221515.html
```

```
border-radius：圆角
```

```
flex-wrap:wrap 换行显示
```

```
伪类
：ntp-last-of-type（-n+2） 选择标签的最后2个
：ntp-last-of-type（2） 选择标签的第2个
```

```
line-height：行的高度
```

```
margin:0 auto; //居中
```

```
text-decoration：取消下划线
```

```
overflow 
overflow属性指定如果内容溢出一个元素的框，会发生什么
```

```
文字水平垂直居中：
https://www.cnblogs.com/xiaozhumaopao/p/5803188.html
```

```
页面垂直水平居中除了flex布局还有其他方法
```

```
input标签前添加文字用
https://segmentfault.com/q/1010000008629020
display:inline-block;
不用flex布局
```

```
max-height:
设定元素最高值
```

```
vertical-align：
可设置元素的对齐
```

```
边框阴影
  box-shadow: 0px 2px 2px rgba(0, 0, 0, .3);
```

```
隐藏超出元素范围的方法
http://www.divcss5.com/wenji/w415.shtml
```

```
缩小图片方法
http://www.divcss5.com/wenji/w632.shtml
```

```
列表横向排列
https://zhidao.baidu.com/question/551805817.html
```

```
float加载子元素的属性上才有效果
```

```
行内元素对整齐，当超过一点时溢出
 text-align: justify;
```

```
幻灯片
https://www.cnblogs.com/5201314m/p/9895264.html
http://www.dowebok.com/56.html
```

```
样式选中效果routerlink
https://www.ucloud.cn/yun/111878.html
```

```
a和routerlink有很大关系
```

```
routerlink样式
https://www.cnblogs.com/kugeliu/p/6727675.html
```

```
h3触摸变颜色
div a:hover h3{
  color: #29abe2;
	/* border-bottom: 3px solid #29abe2; */
}
```

```
选中目标或者想复制时，想改变颜色
::selection {
    background: #262a30;
    color: #fff;
}
呈黑色，而不是普遍的蓝色
```

```
水平居中方法2
http://www.divcss5.com/rumen/r622.shtml
white-space 属性设置如何处理元素内的空白。

这个属性声明建立布局过程中如何处理元素中的空白符。值 

pre-wrap 和 pre-line 是 CSS 2.1 中新增的
https://www.w3school.com.cn/cssref/pr_text_white-

space.asp
```

```
css排除某元素
https://blog.csdn.net/parade0393/article/details/80801
```

```
字体垂直居中：
https://zhidao.baidu.com/question/512789571.html
```

```
颜色使用的特殊属性rgba
background-color: rgba(10,20,245,0.5);
```

```
css
normalize.css
```

```
不要换行
white-space:nowrap
```

```
省略号
text-overflow: ellipsis
```

```
overflow:hidden是当元素内的内容溢出的时候使它隐藏溢出的部分

，即超出部分隐藏
```

```
align-items: center,表示在Y轴上居中
```

```
box-shadow设置阴影效果
```

```
animate.css 动画框架
```

```
rem和rpx:
https://blog.csdn.net/byg184244735/article/details/80198882
```

```
css
颜色调节器
http://www.atool9.com/colorpicker.php
```

```
图文详解CSS中!important 的使用方法
http://www.divcss5.com/rumen/r55319.shtml
.line-h0{ line-height: 0!important; }
```

```
CSS text-decoration 属性
https://www.w3school.com.cn/cssref/pr_text_text-decoration.asp
```



# css-api网站

http://www.w3school.com.cn/tags/tag_style.asp

# animate.css插件

一个动画插件

```
动画animate.css
vue中引入

animate.css:https://www.jianshu.com/p/06d497ad0ab5
样式：http://www.jq22.com/yanshi819
模板代码：

https://blog.csdn.net/weixin_39051908/article/details/

102841075
指南：https://www.cnblogs.com/gluncle/p/9662410.html
https://blog.csdn.net/qq_25804071/article/details/7091

1421
https://www.cnblogs.com/wwhhq/p/8067768.html
http://www.jq22.com/yanshi819
粒子系统动画插件
http://www.jq22.com/jquery-info566
```

# css框架

## mint-ui

## M-ui