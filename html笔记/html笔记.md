

# html基础

## 基本标签

```html
属性快捷键提示
ALT+/


水平线标签
<hr/>


空一行
<br/>


<font>表单


<input>输入


<ol>有序


<ul>无序

```

## html请求头和响应头

web的请求头和响应头
https://blog.csdn.net/lhjuejiang/article/details/83311704

## html插入js的方法

```html
4.<!-- 1.内嵌脚本 -->
<input type="button" value="点我" onclick="alert('helloworld1')">

<!-- 2.内部脚本 >
<script type="text/javascript">
	alert("helloworld2");
</script>

<!-- 3.外部脚本 -->
<script type="text/javascript" src="js/01-helloworld.js"></script>
```

# html5改动

## HTML5页面中的标签基本使用

```html
<body>
    <header>定义了文档的头部区域</header>
    <div>
        <article>定义页面的侧边栏内容</article>
        <aside>定义页面内容之外的内容</aside>
    </div>
    <footer>定义 section 或 document 的页脚</footer>
</body>
```



## 新增标签

```
<canvas>	标签定义图形，比如图表和其他图像。该标签基于 JavaScript 的绘图 API
```

```
<audio>	定义音频内容
<video>	定义视频（video 或者 movie）
<source>	定义多媒体资源 <video> 和 <audio>  字体
<embed>	定义嵌入的内容，比如插件。
<track>	为诸如 <video> 和 <audio> 元素之类的媒介规定外部文本轨道。
```

```
<datalist>	定义选项列表。请与 input 元素配合使用该元素，来定义 input 可能的值。
<keygen>	规定用于表单的密钥对生成器字段。
<output>	定义不同类型的输出，比如脚本的输出。
```

```
<article>	定义页面的侧边栏内容
<aside>	定义页面内容之外的内容。
<bdi>	允许您设置一段文本，使其脱离其父元素的文本方向设置。
<command>	定义命令按钮，比如单选按钮、复选框或按钮
<details>	用于描述文档或文档某个部分的细节
<dialog>	定义对话框，比如提示框
<summary>	标签包含 details 元素的标题
<figure>	规定独立的流内容（图像、图表、照片、代码等等）。
<figcaption>	定义 <figure> 元素的标题
<footer>	定义 section 或 document 的页脚。
<header>	定义了文档的头部区域
<mark>	定义带有记号的文本。
<meter>	定义度量衡。仅用于已知最大和最小值的度量。
<nav>	定义运行中的进度（进程）。
<progress>	定义任何类型的任务的进度。
<ruby>	定义 ruby 注释（中文注音或字符）。
<rt>	定义字符（中文注音或字符）的解释或发音。
<rp>	在 ruby 注释中使用，定义不支持 ruby 元素的浏览器所显示的内容。
<section>	定义文档中的节（section、区段）。
<time>	定义日期或时间。
<wbr>	规定在文本中的何处适合添加换行符。
```

## DOM扩展

```javascript
1.获取元素：
a)document.getElementsByClassName ('class') 通过类名获取元素，以类数组形式存在。getElementsByTagName

b)document.querySelector('selector') 通过CSS选择器获取元素，符合匹配条件的第1个元素。

c)document.querySelectorAll('selector') 通过CSS选择器获取元素，以类数组形式存在。





2.类名操作：
a)Node.classList.add('class') 添加class

b)Node.classList.remove('class') 移除class

c)Node.classList.toggle('class') 切换class，有则移除，无则添加

d)Node.classList.contains('class') 检测是否存在class





3.自定义属性：
a)在HTML5中我们可以自定义属性，其格式如下data-*=""，例如：data-info="我是自定义属性"，通过Node.dataset['info'] 我们便可以获取到自定义的属性值。

b)当我们如下格式设置时，则需要以驼峰格式才能正确获取：data-my-name="itcast"，获取Node.dataset['myName']
```

## 多媒体

使用方式去百度查

```
1.常用方法：load() 加载、  play() 播放、  pause() 暂停
Jq没有提供对视频播放控件的方式，也就意味着如果要操作视频播放，必须使用原生的js方法—dom元素



2.常用属性：
a)currentTime 视频播放的当前进度、
b)duration:视频的总时间  100000/60
c)paused:视频播放的状态.



3.常用事件：
a)oncanplay: 事件在用户可以开始播放视频/音频（audio/video）时触发。
b)ontimeupdate:通过该事件来报告当前的播放进度.
c)onended:播放完时触发—重置
```

## 地理定位

去百度查

```
a)IP地址


b)三维坐标
i.GPS（Global Positioning System，全球定位系统）
ii.Wi-Fi
iii.手机信号


c)用户自定义数据
如下图对不同获取方式的优缺点进行了比较，浏览器会自动以最优方式去获取用户地理信息。
```

## 拖拽

去百度查

```css
1.定义和用法：拖放是 HTML5 中非常常见的功能。




2.在拖放的过程中会触发以下事件：
a)在拖动目标上触发事件 (源元素):
ondragstart - 用户开始拖动元素时触发
ondrag - 元素正在拖动时触发
ondragend - 用户完成元素拖动后触发
b)释放目标时触发的事件—   当拖拽元素在目标容器上进行操作的时候:
ondragenter - 当被鼠标拖动的对象进入其容器范围内时触发此事件
ondragover - 当某被拖动的对象在另一对象容器范围内拖动时触发此事件
ondragleave - 当被鼠标拖动的对象离开其容器范围内时触发此事件
ondrop - 在一个拖动过程中，释放鼠标键时触发此事件




3.注意： 
1.在拖动元素时，每隔 350 毫秒会触发 ondrag 事件。
2.为了让元素可拖动，需要使用 HTML5 draggable 属性
3.链接和图片默认是可拖动的，不需要 draggable 属性
4.可以通过addEventListener来添加拖拽相关事件
5.事件源：触发事件的源，一般情况下我们会将相同操作的多个对象绑定到同一个处理事件，同时传递当前的对象到处理方法，这就是事件源参数
```

## web存储

```javascript
2.HTML5提供的解决方案：
a)window.sessionStorage
b)window.localStorage




3.特点：
a)设置、读取方便
b)容量较大，sessionStorage约5M、localStorage约20M
c)只能存储字符串，可以将对象JSON.stringify() 编码后存储




4.Window.sessionStorage的使用
a)特点：
i.生命周期为关闭浏览器窗口：相当于存储在当前页面的内内存中
ii.在同一个窗口下数据可以共享(在当前页面下可以获取到，换另外一个页面下不能获取到)
b)方法介绍：(两种存储方式的方法一致)
i.SetItem(key,value):设置数据，以键值对的方式
ii.getItem(key):通过指定的键获取对应的值内容
iii.removeItem(key):删除指定的key及对应的值内容
iv.clear():清空所有存储内容
```

## 应用缓存

去百度查

## 网络状态

去百度查

```css
我们可以通过window.onLine来检测，用户当前的网络状况，事件参数可以返回一个布尔值
1.window.online用户网络连接时被调用
2.window.offline用户网络断开时被调用
```

示例:

```javascript
/*网络连接时调用*/
window.addEventListener("online",function(e){
    console.log("ok");
    console.log(e.returnValue);
});
/*网络断开时调用*/
window.addEventListener("offline",function(e){
    console.log("no");
    console.log(e.returnValue);
});
```

## 全屏

例子：

```javascript
btn.onclick=function() {
    /*能力测试*/
    if(docuEle.requestFullScreen){
        document.getElementById("img").requestFullScreen();
    }
    else if(docuEle.webkitRequestFullScreen){
        document.getElementById("img").webkitRequestFullScreen();
    }
    else if(docuEle.mozRequestFullScreen){
        document.getElementById("img").mozRequestFullScreen();
    }
}
```



# html其他笔记

未细分的笔记：

```css
在vscode中，用html然后会出现自动提示，直接生html的格式

overflow-x:hidden，不出现横向拉条
```

```css
html:
浏览器network是请求,requesturl是请求地址，response是请求返回的数据
```

```css
HTML转js
http://tool.chinaz.com/tools/html_js.aspx
```

```css
html引入js,css
https://www.cnblogs.com/wsg25/p/10643435.html
```

### html,css,js桌面化框架

https://github.com/electron/electron
https://www.bilibili.com/video/av37320192?from=search&seid=16354742310297771024
https://www.bilibili.com/video/av72028068?from=search&seid=12880385209271876894