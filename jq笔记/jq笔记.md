# Jquery基础

## 自带函数$(function(){});

```
所有的jquery代码写在页面加载函数
$(function(){
	Jquery代码
});
```

```javascript
<html>
	<head>
		<meta charset="UTF-8">
		<title>jquery入门</title>
		<script src="../../js/jquery-1.8.3.js"></script>
		<script>
			//整个文档加载完毕后执行
			/*function init(){
				alert("张三");
			}*/
			
			/*window.onload= function(){
				alert("张三");
			}
			
			//整个文档加载完毕后(包括图片)执行
			window.onload= function(){
				alert("老王");
			}
			
			//dom树绘制完毕后执行,可能DOM元素关联的东西并没有加载完
			jQuery(document).ready(function(){
				alert("李四");
			});
			
			//jquery的简写方法(页面加载)
			$(function(){
				alert("王五");
			});
			*/
			
			function init(){
				document.getElementById("a1").onclick= function(){
					location.href="";
				}
			}
			
			$(function(){
				document.getElementById("a1").onclick= function(){
					location.href="";
				}
			});
			
			$(function(){
				document.getElementById("a2").onclick= function(){
					location.href="";
				}
			});
			
		</script>
		
	</head>
	<body onload="init()">
		<a href="#" id="a1">ss</a>
		<a href="#" id="a2"></a>
	</body>
</html>
```

## jq获取元素

```
JS:document.getElementById();

JQ:$(“#id”);
```

Jquery对象与DOM对象转换:

```javascript
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript" src="../../js/jquery-1.8.3.js" ></script>
		<script>
			function JSWrite(){
				//document.getElementById("span1").innerHTML="美美哒！";
				var spanEle = document.getElementById("span1");
				$(spanEle).html("美美哒！");
			}
			
			$(function(){
				/*document.getElementById("btn1").onclick = function(){
					document.getElementById("span1").innerHTML="帅帅哒！";
				}*/
				$("#btn1").click(function(){
					//JQ对象转换成DOM对象的第一种方式
					//$("#span1")[0].innerHTML="呵呵哒！";
					//JQ对象转换成DOM对象的第二种方式
					$("#span1").get(0).innerHTML="呵呵哒！";
				});
				
			});
		</script>
	</head>
	<body>
		<input type="button" value="JS写入" onclick="JSWrite()"/>
		<input type="button" value="JQ写入" id="btn1"/><br /><br />
		<span id="span1">sssss</span>
	</body>
```

JQ对象只能操作JQ里面的属性和方法

JS对象只能操作JS里面的属性和方法。

## jq的选择器

### 基本选择器

```
id选择器：$(“#id名称”);

元素选择器：$(“元素名称”);

类选择器：$(“.类名”);

通配符：*

多个选择器共用(并集)
```

例子：

```vue
<html>
	<head>
		<meta charset="UTF-8">
		<title>基本选择器</title>
		<link rel="stylesheet" href="../../css/style.css" type="text/css"/>
		<script type="text/javascript" src="../../js/jquery-1.8.3.js" ></script>
		<script>
			$(function(){
				$("#btn1").click(function(){
					$("#one").css("background-color","pink");
				});
				$("#btn2").click(function(){
					$(".mini").css("background-color","pink");
				});
				$("#btn3").click(function(){
					$("div").css("background-color","pink");
				});
				$("#btn4").click(function(){
					$("*").css("background-color","pink");
				});
				$("#btn5").click(function(){
					$("#two .mini").css("background-color","pink");
				});
			});
		</script>		
	</head>
	<body>
		<input type="button" id="btn1" value="选择为one的元素"/>
		<input type="button" id="btn2" value="选择样式为mini的元素"/>
		<input type="button" id="btn3" value="选择所有的div元素"/>
		<input type="button" id="btn4" value="选择所有元素"/>
		<input type="button" id="btn5" value="选择id为two并且样式为mini的元素"/>
		<hr/>
		<div id="one">
			<div class="mini">
				111
			</div>
		</div>
		
		<div id="two">
			<div class="mini">
				222
			</div>
			<div class="mini">
				333
			</div>
		</div>
		
		<div id="three">
			<div class="mini">
				444
			</div>
			<div class="mini">
				555
			</div>
			<div class="mini">
				666
			</div>
		</div>
		
		<span id="four">
			
		</span>
	</body>
</html>
```

### 层级选择器

```
ancestor descendant: 在给定的祖先元素下匹配所有的后代元素(儿子、孙子、重孙子)

parent > child : 在给定的父元素下匹配所有的子元素(儿子)

prev + next: 匹配所有紧接在 prev 元素后的 next 元素(紧挨着的，同桌)

prev ~ siblings: 匹配 prev 元素之后的所有 siblings 元素(兄弟)
```

例子：

```vue
<html>
	<head>
		<meta charset="UTF-8">
		<title>层级选择器</title>
		<link rel="stylesheet" href="../../css/style.css" />
		<script type="text/javascript" src="../../js/jquery-1.8.3.js" ></script>
		<script>
			$(function(){
				$("#btn1").click(function(){
					$("body div").css("background-color","pink");
				});
				$("#btn2").click(function(){
					$("body>div").css("background-color","pink");
				});
				$("#btn3").click(function(){
					$("#two+div").css("background-color","pink");
				});
				$("#btn4").click(function(){
					$("#one~div").css("background-color","pink");
				});
			});
			
		</script>
		
		
	</head>
	<body>
		<input type="button" id="btn1" value="选择body中的所有的div元素"/>
		<input type="button" id="btn2" value="选择body中的第一级的孩子"/>
		<input type="button" id="btn3" value="选择id为two的元素的下一个元素"/>
		<input type="button" id="btn4" value="选择id为one的所有的兄弟元素"/>
		
		<hr/>
		<div id="one">
			<div class="mini">
				111
			</div>
		</div>
		
		<div id="two">
			<div class="mini">
				222
			</div>
			<div class="mini">
				333
			</div>
		</div>
		
		<div id="three">
			<div class="mini">
				444
			</div>
			<div class="mini">
				555
			</div>
			<div class="mini">
				666
			</div>
		</div>
		
		<span id="four">
			
		</span>
	</body>
</html>
```

### 基本过滤选择器

![过滤选择器1](E:\前端笔记\前端笔记2\前端笔记\jq笔记\过滤选择器1.png)

代码案例演示：

```vue
<html>
	<head>
		<meta charset="UTF-8">
		<title>基本过滤选择器</title>
		<link rel="stylesheet" href="../../css/style.css" type="text/css"/>
		<script type="text/javascript" src="../../js/jquery-1.8.3.js" ></script>
		<script>
			$(function(){
				$("#btn1").click(function(){
					$("div:first").css("background-color","pink");
				});
				$("#btn2").click(function(){
					$("div:last").css("background-color","pink");
				});
				$("#btn3").click(function(){
					$("div:odd").css("background-color","pink");
				});
				$("#btn4").click(function(){
					$("div:even").css("background-color","pink");
				});
			});
		</script>
		
	</head>
	<body>
		<input type="button" id="btn1" value="body中的第一个div元素"/>
		<input type="button" id="btn2" value="body中的最后一个div元素"/>
		<input type="button" id="btn3" value="选择body中的奇数的div"/>
		<input type="button" id="btn4" value="选择body中的偶数的div"/>
		
		<hr/>
		<div id="one">
			<div class="mini">
				111
			</div>
		</div>
		
		<div id="two">
			<div class="mini">
				222
			</div>
			<div class="mini">
				333
			</div>
		</div>
		
		<div id="three">
			<div class="mini">
				444
			</div>
			<div class="mini">
				555
			</div>
			<div class="mini">
				666
			</div>
		</div>
		
		<span id="four">
			
		</span>
	</body>
</html>
```

### 属性选择器

![属性选择器](E:\前端笔记\前端笔记2\前端笔记\jq笔记\属性选择器.png)

例子：

```vue
<html>
	<head>
		<meta charset="UTF-8">
		<title>层级选择器</title>
		<link rel="stylesheet" href="../../css/style.css"  type="text/css"/>
		<script type="text/javascript" src="../../js/jquery-1.8.3.js" ></script>
		<script>
			$(function(){
				$("#btn1").click(function(){
					$("div[id]").css("background-color","pink");
				});
				$("#btn2").click(function(){
					$("div[id='two']").css("background-color","pink");
				});
			});
			
		</script>
	</head>
	<body>
		<input type="button" id="btn1" value="选择有id属性的div"/>
		<input type="button" id="btn2" value="选择有id属性的值为two的div"/>
		
		<hr/>
		<div id="one">
			<div class="mini">
				111
			</div>
		</div>
		
		<div id="two">
			<div class="mini">
				222
			</div>
			<div class="mini">
				333
			</div>
		</div>
		
		<div id="three">
			<div class="mini">
				444
			</div>
			<div class="mini">
				555
			</div>
			<div class="mini">
				666
			</div>
		</div>
		
		<span id="four">
			
		</span>
	</body>
</html>
```

### 表单选择器

![表单选择器](E:\前端笔记\前端笔记2\前端笔记\jq笔记\表单选择器.png)

例子：

```vue
<html>
	<head>
		<meta charset="UTF-8">
		<title>表单选择器</title>
		<link rel="stylesheet" type="text/css" href="../../css/style.css"/>
		<script type="text/javascript" src="../../js/jquery-1.8.3.js" ></script>
		<script>
			$(function(){
				$("#btn1").click(function(){
					$(":input").css("background-color","pink");
				});
				$("#btn2").click(function(){
					$(":text").css("background-color","pink");
				});
			});
		</script>
	</head>
	<body>
		<input type="button" id="btn1" value="选择所有input元素" />
		<input type="button" id="btn2" value="选择文本框" />
		<br/>
		<form>
			<input type="text" /><br />
			<input type="checkbox" /><br />
			<input type="radio" /><br />
			<input type="image" /><br />
			<input type="file" /><br />
			<input type="submit" />
			<input type="reset" /><br />
			<input type="password" /><br />
			<input type="button" /><br />
			<select><option/></select><br />
			<textarea></textarea><br />
			<button></button>
		</form>
	</body>
</html>
```

# jq其他笔记

```
load方法，可以分离刷新


官网
www.jquery123.com


全屏滚动插件 fullPage.js  http://www.jq22.com/jquery-info1124


iscroll插件为滚动插件


全屏滚动插件 fullPage.js  http://www.jq22.com/jquery-info1124


jq抛出异常
http://www.softwhy.com/article-1478-1.html



jq获取地址链接参数
https://www.cnblogs.com/skytoangel/p/11274559.html


jq监督页面内容变化
https://blog.csdn.net/xiaoshu611/article/details/72985667

jq自动点击
https://blog.csdn.net/soulwyb/article/details/89305297

jq 判断某元素是否有某个类
https://zhidao.baidu.com/question/1895018726023363340.html


JQ页面加载完毕
https://blog.csdn.net/qq_32575047/article/details/80381000



jq当遇到[]的时候，要用$()
https://www.jianshu.com/p/8160a97d21c1


jq获取元素节点
https://www.cnblogs.com/tdzr/p/2019-02-15.html


jq动画
https://www.cnblogs.com/XueTing/p/11240770.html



jquery
sweetalert提示框
https://sweetalert.js.org/


jq
html引入jq
https://blog.csdn.net/baidu_38760069/article/details/83095396


jq动画
https://blog.csdn.net/weixin_43684713/article/details/90666183


jq选择器
https://www.cnblogs.com/songjn/p/8889747.html


JQ查找含有某个属性的元素
https://www.cnblogs.com/cq-0715/p/9618399.html


jquery
图片懒加载
http://www.jq22.com/jquery-info390
https://www.cnblogs.com/zzxuan/p/9690496.html
https://www.cnblogs.com/xyyt/p/7650539.html
https://blog.csdn.net/Mariosss/article/details/77712017
https://blog.csdn.net/weixin_38304202/article/details/78282826
```

