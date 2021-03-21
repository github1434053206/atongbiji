# 学习视频

https://www.bilibili.com/video/av48272338?from=search&seid=5087137190985879891

https://www.bilibili.com/video/av71003890?from=search&seid=13459588641289821608

http://www.hcoder.net/course/info_246.html

https://www.bilibili.com/video/av52545607?from=search&seid=14443184170051664296

# uniapp基础

## uniapp介绍

http://www.hcoder.net/tutorials/info_1335.html

uniapp的目录结构和小程序差不多

## 使用和安装

### 下载工具

下载微信开发者平台

下载Hbuilderx:

www.dcloud.io/hbuilderx.html

### uni-app在ios苹果真机运行

https://www.cnblogs.com/yunsun/archive/2019/09/11/11506444.html

https://ask.dcloud.net.cn/question/65723

https://blog.csdn.net/cafuf/article/details/106121223

https://www.cnblogs.com/yunsun/p/11506444.html

### 在安卓夜神模拟器上运行

https://blog.csdn.net/weixin_43968043/article/details/86579020

### uniapp运行小米安卓手机：

https://www.jianshu.com/p/d22b32af3848

https://blog.csdn.net/weixin_44519961/article/details/89543339

## uniapp目录结构

https://blog.csdn.net/ITxiaodong/article/details/92699036

```
unpackage：为编译后的文件一般不修改

APP.VUE：全局配置

main.js:vue的初始化入口文件

manifest.json：项目配置

pages.json：配置路由，导航栏底栏等，相当于小程序的那个文件

uni.scss：基础样式的规定
```



```
pages:业务页面文件存放目录

components：组件文件存放目录

static:静态资源

unpackage:为编译后的文件一般不修改

APP.VUE:应用配置，用来配置APP全局样式以及监听应用的生命周期，全局配置，可设置公共css

main.js:vue初始化入口文件

manifest.json:打包信息，appid,logo,版本

pages.json:配置页面路由，导航条，选项卡等页面类信息，配置路由，导航栏底栏等，相当于小程序的那个文件

uni.scss：基础样式的规定
```

```
pages.json参数：

https://uniapp.dcloud.io/collocation/pages?id=tabbar

重要：[condition](https://uniapp.dcloud.io/collocation/pages?id=condition)

启动模式配置，仅开发期间生效，用于模拟直达页面的场景，如：小程序转发后，用户点击所打开的页面。
```

## uniapp基础组件

### 视图组件

```
view：试图容器，类似于div
https://uniapp.dcloud.io/component/view

scroll-view ：可滚动的视图容器，可滚动视图区域。用于区域滚动
https://uniapp.dcloud.io/component/scroll-view

```

### scroll-view

类似view，可滚动的

https://uniapp.dcloud.io/component/scroll-view

### swiper

类似与轮播图，可横向轮播或者竖向轮播

https://uniapp.dcloud.io/component/swiper

## uniapp基础api

### 图片api

https://uniapp.dcloud.io/api/media/image

### 视频api

https://uniapp.dcloud.io/api/media/video

基础代码：

```vue
<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="top">
			<button type="primary">hello uni!</button>
			<button type="primary2">hello ！！s</button>
		</view>
		
		<navigator url="../home/home?id=123">home</navigator>
		
		<button type="default" @click="seo">dianji</button> -->
		
<!-- 		<button type="default"  class="irews" @click="set">登录</button>
		<button type="default"  class="irews" @click="get">获取用户信息</button>
		<button type="default"  class="irews" @click="choose">获取图片</button> -->
		<video class="videobox" id="vie" src="../../static/12345.mp4" controls></video>
		<button type="default"  class="irews" @click="pau">暂停</button>
		<button type="default"  class="irews" @click="play">开始</button>
		 <!-- <button type="primary" loading="true">页面主操作 Loading</button> -->
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// title: 'Hello uniapp',
				// eor: ["a","b","c"]
				videoCon: null
			}
		},
		onLoad() {
			// console.log(this.videoContext)
			// console.log(this.videoCon)
			this.videoCon=uni.createVideoContext("vie")
 
		},
		methods: {
			// seo(){
			// 	uni.navigateTo({
			// 		url:'../home/home'
			// 	})
			// },
			// set(){
			// 	uni.setStorage({
			// 		key: '1234',
			// 		data: 'wuguotong',
			// 		success() {
			// 			console.log("success") 
			// 		}
			// 	})
			// },
			// get(){
			// 	uni.getStorage({
			// 		key: '1234',
			// 		success(res){
			// 			console.log(res)
			// 			console.log(res.data)
			// 		}
			// 	})
			// },
			// choose(){
			// 	uni.chooseImage({
					
			// 	})
			// },
			pau(){
				this.videoCon.pause();
			},
			play(){
				this.videoCon.play();
			}
		}
	}
</script>

<style>
	.videobox{
		width: 100%;
		/* height: 100%; */
	}
	
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	
	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
	
	.text-area {
		display: flex;
		justify-content: center;
	}
	
	.title {
		font-size: 36rpx;
		color: red;
	}
	
	
	
	.content .irews{
		    /* background-image:url("button/btnbg.png"); */
			background-color: #4CD964;
		        border: none;
		        color: white;
		        padding: 15rpx 30rpx;
		        text-align: center;
		        text-decoration: none;
		        display: inline-block;
		        font-size: 13rpx;
	} 
</style>

```

### 设备api

https://uniapp.dcloud.io/api/system/info?id=getsysteminfo

### 界面api

https://uniapp.dcloud.io/api/ui/prompt

### 页面与窗体api---监听页面事件

是实现页面传值的问题

https://uniapp.dcloud.io/api/window/communication?id=on

被监听的组件：

```
<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="top">
			<button type="primary">hello uni!</button>
			<button type="primary2">hello ！！s</button>
		</view>
		
		<navigator url="../home/home?id=123">home</navigator>
		
		<button type="default" @click="seo">dianji</button> -->
		
<!-- 		<button type="default"  class="irews" @click="set">登录</button>
		<button type="default"  class="irews" @click="get">获取用户信息</button>
		<button type="default"  class="irews" @click="choose">获取图片</button> -->
		<video class="videobox" id="vie" src="../../static/12345.mp4" controls></video>
		<button type="default"  class="irews" @click="pau">暂停</button>
		<button type="default"  class="irews" @click="play">开始</button>
		
		<button type="default"  class="irews" @click="pos">刷新</button>
		<navigator url="../home/home">home</navigator>
		 <!-- <button type="primary" loading="true">页面主操作 Loading</button> -->
		<!-- <home @func="gethome"></home> -->
	</view>
</template>

<script>
	
	import home from '../home/home.vue'
	
	export default {
		data() {
			return {
				// title: 'Hello uniapp',
				// eor: ["a","b","c"]
				videoCon: null
			}
		},
		mounted() {
			
		},
		onLoad() {
			// console.log(this.videoContext)
			// console.log(this.videoCon)
			// this.videoCon=uni.createVideoContext("vie")
			
			// uni.getSystemInfo({
			// 	success(res){
			// 		console.log(res)
			// 		console.log(res.model)
			// 	}
			// })
			
			// uni.getNetworkType({
			// 	success:(res)=>{
			// 		console.log("网络类型") 
			// 		console.log(res)
			// 	}
			// })
			
			// uni.onAccelerometerChange(function (res) {
			//     console.log(res.x);
			//     console.log(res.y);
			//     console.log(res.z);
			// });
			
// 			uni.offAccelerometerChange(function (res) {
//    console.log(res.x);
//        console.log(res.y);
//        console.log(res.z);
// })
 
		},
		 components:{
		        home,
		    },
		methods: {
			gethome(data){
				console.log(data)
			},
			
			// seo(){
			// 	uni.navigateTo({
			// 		url:'../home/home'
			// 	})
			// },
			// set(){
			// 	uni.setStorage({
			// 		key: '1234',
			// 		data: 'wuguotong',
			// 		success() {
			// 			console.log("success") 
			// 		}
			// 	})
			// },
			// get(){
			// 	uni.getStorage({
			// 		key: '1234',
			// 		success(res){
			// 			console.log(res)
			// 			console.log(res.data)
			// 		}
			// 	})
			// },
			// choose(){
			// 	uni.chooseImage({
					
			// 	})
			// },
			pau(){
				this.videoCon.pause();
			},
			play(){
				this.videoCon.play();
			},
			pos(){
				console.log("123")
				 uni.$emit('asc',{msg:'页面更新'})
				}
		}
	}
</script>

<style>
	.videobox{
		width: 100%;
		/* height: 100%; */
	}
	
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	
	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
	
	.text-area {
		display: flex;
		justify-content: center;
	}
	
	.title {
		font-size: 36rpx;
		color: red;
	}
	
	
	
	.content .irews{
		    /* background-image:url("button/btnbg.png"); */
			background-color: #4CD964;
		        border: none;
		        color: white;
		        padding: 15rpx 30rpx;
		        text-align: center;
		        text-decoration: none;
		        display: inline-block;
		        font-size: 13rpx;
	} 
</style>

```

监听事件的组件：

```
<template>
	<view class="home">
		<text>hello</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		onLoad() {

		},
		mounted() {
			// this.$emit('func',"12345")
			uni.$on('asc',(data)=>{
				console.log(data)
			})
		},
		methods: {

		}
	}
</script>

<style>
</style>

```

### 原生子窗体subNVue--API

在原本的dom元素显示新的元素

https://uniapp.dcloud.io/api/window/subNVues?id=app-getsubnvuebyid

看这个视频：4-11subNVue原生子窗体.mp4

## uniapp计量单位

uniapp主要用rpx作为单位，rpx和upx一样，是用750px为基础宽度来计算px

https://www.jianshu.com/p/50ea4804f786

upx，rpx的计算：

将设计稿设为750px，对准的基数就是750px的宽度和高度，为upx

https://www.cnblogs.com/putao1/p/10141875.html

```
.owq{
		width: 100upx;
		height: 100upx;
		font-size: 50upx;
	}
```



## 跨端兼容

https://uniapp.dcloud.io/platform?id=%e8%b7%a8%e7%ab%af%e5%85%bc%e5%ae%b9

```
<template>
	<view class="content">
		<button type="default"  class="irews" @click="pos">刷新</button>
	</view>
</template>

<script>
	
	import home from '../home/home.vue'
	
	export default {
		data() {
			return {
			}
		},
		mounted() {
			
		},
		onLoad() {
		},
		 components:{
		    },
		methods: {
			pos(){
				//#ifdef APP-PLUS
					console.log("我是app")
				//#endif
				
				//#ifdef MP-WEIXIN
					console.log("我是微信小程序")
				//#endif
				}
				
		}
	}
</script>


```



## uniapp数据缓存

https://uniapp.dcloud.io/api/README

```vue
<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="top">
			<button type="primary">hello uni!</button>
			<button type="primary2">hello ！！s</button>
		</view>
		
		<navigator url="../home/home?id=123">home</navigator>
		
		<button type="default" @click="seo">dianji</button> -->
		
		<button type="default"  class="irews" @click="set">登录</button>
		<button type="default"  class="irews" @click="get">获取用户信息</button>
		 <!-- <button type="primary" loading="true">页面主操作 Loading</button> -->
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// title: 'Hello uniapp',
				// eor: ["a","b","c"]
			}
		},
		onLoad() {
			

		},
		methods: {
			seo(){
				uni.navigateTo({
					url:'../home/home'
				})
			},
			set(){
				uni.setStorage({
					key: '1234',
					data: 'wuguotong',
					success() {
						console.log("success") 
					}
				})
			},
			get(){
				uni.getStorage({
					key: '1234',
					success(res){
						console.log(res)
						console.log(res.data)
					}
				})
			}
		}
	}
</script>
```



## uniapp跳转

https://uniapp.dcloud.io/api/README

uni.navigateTo

```vue
<template>
	<view class="content">
		
		
		<button type="default" @click="seo">dianji</button>
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// title: 'Hello uniapp',
				// eor: ["a","b","c"]
			}
		},
		onLoad() {

		},
		methods: {
			seo(){
				uni.navigateTo({
					url:'../home/home'
				})
			}
		}
	}
</script>
```

## uni请求

uni.request

## uniapp生命周期

https://www.jianshu.com/p/b481b6c23cdd

onready比onload更早执行，

```vue
<button type="default" @click="ipo">aaa</button>


onReady() {
			   	this.poes = "1234"
			   },
			   
			   
			   methods: {
				// gethome(data){
				// 	console.log(data)
				// },
				 ipo(){
					 console.log(this.poes)
					 // this.lpo(pow)
				 },
			}
```



## uniApp删掉掉顶部导航栏

https://www.cnblogs.com/xieyao/p/11346075.html

## uniapp参数传递

https://blog.csdn.net/wwf1225/article/details/90693854

## 获取元素节点信息

https://www.jianshu.com/p/7132301dd442

## 页面样式与布局

### rpx和px：

rpx为响应式尺寸



## uniapp使用icon

https://www.jianshu.com/p/7fc08b1b4d85

## Uniapp小程序员上线

看12-5项目发布上线.MP4

## app安卓版上线

看12-6APP安卓打包.mp4

和pdf

## uniapp请求后端数据

直接在Hbuider敲ure

## 看错误位置

在Hbuilder中看错误信息的*.vue:51，说明51行有错

# uniapp其他问题和方法和经验

```
加了"app-plus": {"titleNView": false} 遇到的问题
https://blog.csdn.net/qq_36770615/article/details/90973456


uni-app 里的#ifdef MP是什么意思？条件编译
https://blog.csdn.net/weixin_39644462/article/details/97821783

uniapp元素-媒体组件
https://uniapp.dcloud.io/component/audio


uniapp的px是相对的，相当于小程序的rpx

若设计稿宽度为640PX，元素A在设计稿宽度为100PX，那么在UNIAPP的宽度为750*100/640，结果为117PX

uniapp:
html标签转化


关于uni-app的ui库、ui框架、ui组件
https://ask.dcloud.net.cn/article/35489

uniapp改css样式
<view class="content">
		
		<button type="default"  class="irews" >登录</button>
		<button type="default"  class="irews" >获取用户信息</button>
		
	</view>
	必须这样子改，或者直接用id，不能直接用.irews
	.content .irews{
		    /* background-image:url("button/btnbg.png"); */
			background-color: #4CD964;
		        border: none;
		        color: white;
		        padding: 45rpx 99rpx;
		        text-align: center;
		        text-decoration: none;
		        display: inline-block;
		        font-size: 35rpx;
	} 

```

## uniapp在一个选项中任选一个，下面展示的view不同（重点）

看视频：

10-6实现切换视频列表功能.mp4

# uniapp一些框架

## H-ui框架

给uniapp用的ui框架

http://www.hcoder.net/hui

## zepto框架

类似于移动端的jquery

## GraceUI框架

https://www.graceui.com//manual/info/166-6.html

## 滑动js插件--swiper

 https://www.swiper.com.cn/

# 引入图标和animate

## 运用animate.css

<view class="animated bounceIn" id="dowebok">123</view>

## 运用icon.css

<view class="iconfont icon-sousuo owq"></view>

# 常用方法

页面点击后快速跳转，页内，将代码直接复制到Uniappp上

:scroll-into-view="viewid"

```vue
<!-- 导航组件 -->
<template>
	<view class="city">
		<scroll-view scroll-y="true" :scroll-into-view="viewid" class="coep">
			<view class="pow" v-for="(item,index) of city" :key="index"
			
			>
			<view class="powid" :id="item.id">
				<text>{{item.id}}</text>
				
			</view>
				
					<view class="powdata" v-for="(items,indexo) of item.datas"
									:key="indexo"
									>
									<view class="powdatadaa">
										<text>{{items}}</text>
									</view>
					
					
					
				</view>
				
				
			</view>
			
			<view class="youbian" >
				<view class="youbianzi" v-for="(item,index) of city" :key="index"
				@click="reo(item.id)"
				>
					<view class="youbianzis">
						{{item.id}}
					</view>
				</view>
			</view>
		</scroll-view>
			<!-- <scroll-view scroll-y="true" scroll-into-view="">
				<view>1234</view>
			</scroll-view> -->
			
			
	</view>
</template>

<script>
	
	
	export default {
			data() {
				return {
					// title: 'Hello uniapp',
					// iStatusBarHeight:0
					viewid: "",
					pid:"",
					city:[
						{
							id:"a",
							datas:["a1","a2","a3","a4","a5"]
						},
						{
							id:"b",
							datas:["b1","b2","b3","b4","b5"]
						},
						{
							id:"c",
							datas:["c1","c2","c3","c4","c5"]
						},
						{
							id:"d",
							datas:["bs1","bd2","bd3","ba4","ber5"]
						},
						{
							id:"e",
							datas:["bf1","ab2","be3","wb4","be5"]
						},
						{
							id:"f",
							datas:["bf1","ab2","be3","wb4","be5"]
						},
						{
							id:"g",
							datas:["bf1","ab2","be3","wb4","be5"]
						}
					]
				}
			},
			onLoad() {
				
			},
			watch:{
				pid:function(val,ret){
					this.viewid=this.pid
					console.log(this.viewid)
				}
			},
			mounted() {
				
				// uni.getSystemInfo({
				// 	success:(res)=>{
				// 		this.iStatusBarHeight = res.statusBarHeight
				// 		console.log(this.iStatusBarHeight)
				// 	}
				// })
				// this.iStatusBarHeight = uni.getSystemInfoSync().statusBarHeight
				// console.log(this.iStatusBarHeight)
			},
			
			 components:{
					
			    },
			methods: {
				// gethome(data){
				// 	console.log(data)
				// },
				reo(data){
					this.pid=data
					console.log(data)
				}
			}
		}
</script>

<style> 

page{
  height:100%;
  /* background-color: #b3d4db; */
  background-color: #333333;
}
	.city{
		margin-top: 60rpx;
		width: 100%;
		height: 100%;
		position: relative;
		
	}
	
	.youbian{
		position: fixed;
		/* float: left; */
		right: 10rpx;
		top: 200rpx;
		width: 40rpx;
		/* height: 200rpx; */
		
	}
	.youbian .youbianzi{
		position: relative;
		float: left;
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		margin-top: 3rpx;
	}
	
	.coep{
		height: 800rpx;
	}
</style>

```



# 问题：

缺系统的笔记，可去找一下然后再来补