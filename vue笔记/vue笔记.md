# Vue基础

## 创建vue项目

https://www.cnblogs.com/l-y-h/p/11241503.html

```
第一种创建方式：必须cd到对应的一个项目里面
			
		vue init webpack vue-demo01

		cd  vue-demo01 
		
		cnpm install   /  npm install，如果创建项目的时候没有报错，这一步可以省略。如果报错了  cd到项目里面运行  cnpm install   /  npm install
		
		npm run dev
```

```
另一种创建项目的方式：
		
		vue init webpack-simple vuedemo02

		cd  vuedemo02
		
		cnpm install   /  npm install        
		
		npm run dev
```

## vue模板

测试代码模板：

https://blog.csdn.net/weixin_39051908/article/details/103179641

-----------------------

https://blog.csdn.net/weixin_39051908/article/details/103682085
https://blog.csdn.net/weixin_39051908/article/details/103682108

## mvvm的概念

简单的说，ViewModel就是View与Model的连接器，View与Model通过ViewModel实现双向绑定。bai

https://www.jianshu.com/p/ffcb84dc4ebc

https://zhidao.baidu.com/question/2269971336802684948.html

## Diff算法

https://www.cnblogs.com/wind-lanyan/p/9061684.html

https://blog.csdn.net/weixin_44369568/article/details/91488905

https://www.baidu.com/link?url=1zxXwNrKyBHlF953OqNFErw-yRgidVJTK-ImdIYE-q6q_xKSTa9yuTvI2b37ZccAmqt8D2T9JcrJYntaDnxVe_&wd=&eqid=eab1f599000093f2000000065fa1b9f2

https://segmentfault.com/a/1190000008782928?utm_source=tag-newest

有谜，可以专研

## vue文件命名规范

vue文件用MyHo大写开头命名

vue的组件用Base,App,V等开头命名，如BaseTabber

https://www.cnblogs.com/mouseleo/p/11484550.html

https://cn.vuejs.org/v2/style-guide/#%E5%8D%95%E6%96%87%E4%BB%B6%E7%BB%84%E4%BB%B6%E6%96%87%E4%BB%B6%E7%9A%84%E5%A4%A7%E5%B0%8F%E5%86%99%E5%BC%BA%E7%83%88%E6%8E%A8%E8%8D%90

## vue的符号

### $的意思

https://blog.csdn.net/u011464124/article/details/89137765

除了数据属性，Vue 实例还暴露了一些有用的实例属性与方法。它们都有前缀 `$`，以便与用户定义的属性区分开来。例如：

## vue指令

### v-text和v-html的区别和定义

v-text:转义输出

v-html:不转义输出

https://www.cnblogs.com/tommymarc/p/11627396.html

https://www.cnblogs.com/xiaowie/p/11572015.html

https://blog.csdn.net/pillow233/article/details/100888079

### `样式绑定v-bind`

v-bind指令用于给html标签设置属性。

https://www.cnblogs.com/shix0909/p/11188263.html

https://www.cnblogs.com/yuyujuan/p/9749932.html

```vue
<!-- 完整语法 -->
<a v-bind:href="url"></a>
<!-- 缩写 -->
<a :href="url"></a>
```

```vue
<div id="app">
  <div v-bind:id="id1">文字</div>
</div>

<script>
new Vue({
  el: '#app',
  data: {
    id1: 'myid'
  }
})
</script>
```

https://www.cnblogs.com/shix0909/p/11188263.html

https://www.cnblogs.com/xiaowie/p/11572050.html

### v-on和事件修饰符事件绑定

v-on,它是来绑定事件监听器,这样我们就可以做一些交互了.

   我们在的的时侯v-on是可以缩写成@的，例如上边的可以缩写成:@:chick="btn"。

```vue
<div id="app">
    <!-- 使用事件绑定的简写形式 -->
    <input type="button" value="按钮" v-on:click="btn">
</div>
<script>
    var vm = new Vue({
        el: '#app',
        //methods是用来专门存放vue的处理方法的
        methods: {
            btn: function () {
                alert('123');
            }
        }
    });
</script>
```

https://www.jianshu.com/p/e4095d0fb284

https://www.cnblogs.com/shineguang/p/10884324.html

---------------------------------------------

https://www.cnblogs.com/xuqp/p/9406971.html

什么是事件修饰符

```
在Vue中，事件修饰符处理了许多DOM事件的细节，让我们不再需要花大量的时间去处理这些烦恼的事情，而能有更多的精力专注于程序的逻辑处理。在Vue中事件修饰符主要有：

.stop：等同于JavaScript中的event.stopPropagation()，防止事件冒泡

.prevent：等同于JavaScript中的
event.preventDefault()，防止执行预设的行为（如果事件可取消，则取消该事件，而不停止事件的进一步传播）

.capture：与事件冒泡的方向相反，事件捕获由外到内

.self：只会触发自己范围内的事件，不包含子元素

.once：只会触发一次
```

在事件处理程序中调用 `event.preventDefault()` 或 `event.stopPropagation()` 是非常常见的需求。尽管我们可以在方法中轻松实现这点，但更好的方式是：方法只有纯粹的数据逻辑，而不是去处理 DOM 事件细节。

为了解决这个问题，Vue.js 为 `v-on` 提供了事件修饰符。之前提过，修饰符是由点开头的指令后缀来表示的。

  **使用修饰符 阻止浏览器的默认行为**:

```vue
<div id="app">
    <a href="http://www.qq.com"  v-on:click.prevent="btn">腾讯</a>
</div>
<script>
    var vm = new Vue({
        el: '#app',
        methods: {
            btn: function () {
                alert('123');
            }
        }
    });
</script>
```

https://blog.csdn.net/wangchaohpu/article/details/84575144

### v-model和双向绑定

https://www.jianshu.com/p/20e485cb65d9

https://www.cnblogs.com/mark5/p/11603428.html

https://www.jianshu.com/p/34915ec89166

[Vue.js双向绑定的实现原理](http://www.cnblogs.com/kidney/p/6052935.html)

v-model指令的本质是：  它负责监听用户的输入事件，从而更新数据，并对一些极端场景进行一些特殊处理。同时，v-model会忽略所有表单元素的value、checked、selected特性的初始值，它总是将vue实例中的数据作为数据来源。  然后当输入事件发生时，实时更新vue实例中的数据。

**v-model使用**

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--引入最新的vue稳定版本-->
    <script type="text/javascript" src="https://unpkg.com/vue/dist/vue.min.js"></script>
    <link rel="stylesheet" href="./css/style.css" type="text/css">
</head>
<body>


<!--input输入框-->
<div id="app">
     <input type="text" v-model="message" placeholder="请输入">
    <p>输入的内容是: {{message}}</p>
</div>

<script>
    var  vue=new Vue({
        el:'#app',
        data:{
           message:''
        }
    });
</script>
</body>
</html>

```

**用v-bind和v-on指令实现v-model**，v-model也可以用bind和on实现

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--引入最新的vue稳定版本-->
    <script type="text/javascript" src="https://unpkg.com/vue/dist/vue.min.js"></script>
    <link rel="stylesheet" href="./css/style.css" type="text/css">
</head>
<body>


<!--input输入框-->
<div id="app">
    <!--把message字段的值作为input标签的value属性值，同时监听输入事件，实时更新message的值-->
    <input type="text" @input="handleInput($event)"  placeholder="请输入"  v-bind:value="message">
    <p>输入的内容是: {{message}}</p>
</div>

<script>
    var  vue=new Vue({
        el:'#app',
        data:{
            message:''
        },
        methods:{
            handleInput: function (event) {
                console.info("控制台打印event详情")
                console.info(event)
                console.info(event.toLocaleString());
                this.message=event.target.value;
            }
        }
    });
</script>
</body>
</html>

```

### v-for`和`key

https://www.cnblogs.com/wangyfax/p/10073159.html

v-for循环数组：

```vue
<div id="test">
        <ul>
            <li v-for='(item,index) in arr'>{{ item }}---{{ index }}</li>
        </ul>
    </div>
    <script>
        const vm = new Vue({
            el: "#test",
            data: {
                arr: ['apple', 'orange', 'banana'],
            }
        })
    </script>

//apple---0
//orange--1
//banana--2
```

循环对象与列表渲染

```vue
<div id="test">
        <ul>
            <li v-for='(value,key,index) in obj'>{{ value }}---{{ key }}---{{ index }}</li>
        </ul>
    </div>
    <script>
        const vm = new Vue({
            el: "#test",
            data: {
                obj: {
                    name: "zhangsan",
                    age: 18,
                    sex: '男'
                }
            }
        })
    </script>

//zhangsan--name--0

//18--age--1
...
```

**key**

https://www.jianshu.com/p/4bd5e745ce95

https://www.cnblogs.com/yangpeixian/p/11707069.html

https://blog.csdn.net/xukongjing1/article/details/81587549

当Vue用 v-for 正在更新已渲染过的元素列表是，它默认用“就地复用”策略。如果数据项的顺序被改变，Vue将不是移动DOM元素来匹配数据项的改变，而是简单复用此处每个元素，并且确保它在特定索引下显示已被渲染过的每个元素。

为了给Vue一个提示，以便它能跟踪每个节点的身份，从而重用和重新排序现有元素，你需要为每项提供一个唯一 key 属性。key属性的类型只能为 string或者number类型。

### v-if`和`v-show条件渲染

一般来说，v-if 有更高的切换消耗而 v-show 有更高的初始渲染消耗。因此，如果需要频繁切换 v-show 较好，如果在运行时条件不大可能改变 v-if 较好。

```
共同点：

都是用来控制DOM元素的显示与隐藏的

区别：

（1）v-if指令是动态的创建和删除DOM的元素节点，条件为false时，编译后我们在浏览器中看到代码是不存在的。

而v-show的实际情况是通过css代码来控制该元素的显示与隐藏，也就是display：none；display：block

（2）v-if多用于切换状态不频繁情况，频繁的创建和删除节点是比较耗性能的；v-show初次渲染代价高，实用于显示隐藏切换较频繁的时候
```

使用

```vue
		<!--需要先引用一下vue.js-->
		<script src="js/vue.js" type="text/javascript" charset="utf-8"></script>
		
		<script type="text/javascript">
			var vm = new Vue({
				el:"#Box1",
				data:{
					IsShow:true,
					IsChuang:true
				}
				
			});
		</script>



		<div id="Box1">
			<div v-show="IsShow">
				需要动态显示和隐藏的内容
			</div>
			<div v-if="IsChuang">
				需要创建和删除的具体内容
			</div>
		</div>
```

### 自定义指令

https://cn.vuejs.org/v2/guide/custom-directive.html

https://blog.csdn.net/smlljet/article/details/91874728

自定义全局和局部的 自定义指令：

```
// 自定义全局指令 v-focus，为绑定的元素自动获取焦点：

    Vue.directive('focus', {

      inserted: function (el) { // inserted 表示被绑定元素插入父节点时调用

        el.focus();

      }

    });



    // 自定义局部指令 v-color 和 v-font-weight，为绑定的元素设置指定的字体颜色 和 字体粗细：

      directives: {

        color: { // 为元素设置指定的字体颜色

          bind(el, binding) {

            el.style.color = binding.value;

          }

        },

        'font-weight': function (el, binding2) { // 自定义指令的简写形式，等同于定义了 bind 和 update 两个钩子函数

          el.style.fontWeight = binding2.value;

        }

      }
```

使用方式：

```
<input type="text" v-model="searchName" v-focus v-color="'red'" v-font-weight="900">
```

## vue属性

### 属性介绍

https://www.cnblogs.com/bgwhite/p/9297221.html

```
el属性
用来指示vue编译器从什么地方开始解析 vue的语法，可以说是一个占位符。

data属性
用来组织从view中抽象出来的属性，可以说将视图的数据抽象出来存放在data中。

template属性
用来设置模板，会替换页面元素，包括占位符。

methods属性
放置页面中的业务逻辑，js方法一般都放置在methods中

render属性
创建真正的Virtual Dom

computed属性
用来计算

watch属性
watch:function(new,old){}
监听data中数据的变化
两个参数，一个返回新值，一个返回旧值，
```

## data属性

vue data中可以放函数，如av:function(){},

### watch属性

https://www.jianshu.com/p/94a850e54db4

https://blog.csdn.net/weixin_43837268/article/details/92769669

https://www.jb51.net/article/143371.htm
https://blog.csdn.net/guanguan0_0/article/details/80355029
https://www.jb51.net/article/160221.htm

vue中watch监听路由变化
http://www.luyixian.cn/javascript_show_163648.aspx

Vue 提供了一种更通用的方式来观察和响应 Vue 实例上的数据变动：侦听属性watch。**watch中可以执行任何逻辑，如函数节流，Ajax异步获取数据，甚至操作 DOM（不建议）。**

```vue

<template>
  <div class="attr">
    <h1>watch属性</h1>
    <h2>{{ $data }}</h2>
    <button @click="() => (a += 1)">修改a的值</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      a: 1,
      b: { c: 2, d: 3 },
      e: {
        f: {
          g: 4
        }
      },
      h: []
    };
  },
  watch: {
    a: function(val, oldVal) {
      this.b.c += 1;
    },
    "b.c": function(val, oldVal) {
      this.b.d += 1;
    },
    "b.d": function(val, oldVal) {
      this.e.f.g += 1;
    },
    e: {
      handler: function(val, oldVal) {
        this.h.push("浪里行舟");
      },
      deep: true //用于监听e对象内部值的变化
    }
  }
};
</script>

```

通过watch属性可以监听Model中的数据变化，只要该数据发生变化，就会调用对应的回调函数：

```javascript
watch:{
  num1:function(newValue,oldValue){
      console.log(newValue,oldValue);
  }
}

//num为属性
```

通过watch属性可以监听路由地址的变化，只要路由地址发生变化，就会自动调用对应的回调函数：

```javascript
watch:{
  "$route.path":function(newValue,oldValue){
      console.log(newValue,oldValue);
  }
}
```

### computed属性

https://segmentfault.com/a/1190000015070628?utm_source=tag-newest

https://segmentfault.com/a/1190000014478664?utm_source=tag-newest
https://www.cnblogs.com/gunelark/p/8492468.html

Vue中的 computed 属性称为 计算属性

```vue
<div id="example">
  <p>Original message: "{{ message }}"</p>
  <p>Computed reversed message: "{{ reversedMessage }}"</p>
</div>


var vm = new Vue({
  el: '#example',
  data: {
    message: 'Hello'
  },
  computed: {
    // 计算属性的 getter
    reversedMessage: function () {
      // `this` 指向 vm 实例
      return this.message.split('').reverse().join('')
    }
  }
})
```

在模板文件中，只需要写reversedMessage即可，它与message是有依赖关系的。

### method属性

在vue中created或者其他生命周期函数引用Methods，要用this

methods中的函数要用function()否则调用不了data

### computed和watch和method区别

```
当需要数据在异步变化或者开销较大时，执行更新，使用watch会更好一些；而computed不能进行异步操作；

computed可以用缓存中拿数据，而watch是每次都要运行函数计算，不管变量的值是否发生变化，而computed在值没有发生变化时，可以直接读取上次的值

在模板文件中，computed属性只需要写{{reverseMessage}}，而methods需要写成{{reverseMessage()}}，最明显的区别就是methods是方法，需要执行；

computed属性只有在依赖的data放生变化时，才会重新执行，否则会使用缓存中的值，而methods是每次进入页面都要执行的，有些需要每次进入页面都执行的方法，需要使用methods，而computed属性比较节约。
```



## vue过滤器

 Vue.js允许自定义过滤器，可被用于一些常见的文本格式化。过滤器可以用在两个地方：双花括号插值和v-bind表达式。过滤器应该被添加在JavaScript表达式的尾部，由“管道”符号指示；（借官方的来介绍下，接下来直奔主题）

https://www.cnblogs.com/qdwds/p/11564467.html

https://cn.vuejs.org/v2/guide/filters.html

### 全局过滤器

main.js中定义全局过滤器

```vue
Vue.filter('length10',(e) =>{
  return e.slice(0,10) + '...'
})
//  定义转大小写的过滤器
Vue.filter('toUpperCase',(e)=>{
 return  e.toUpperCase()
})
```

app.vue使用

```vue
// template
  <div>{{str}}</div>
  <div>{{str | length10}}</div>
  <div>{{str1 | length10 | toUpperCase}}</div>
  
//  script
data(){
    return {
      str:'公众号“前端伪大叔”，欢迎大家前来关注！',
      str1:'qianduanweidashu'
    }
  }
```

### 组件内过滤器

组件内过滤器，需要定义在filtets这个对象中，对象中定义的都是方法；

```vue
//  template
  <div>{{str | length(9) }}</div>
  <div>{{str1 | length(9) | toUpperCase}}</div>
  
//  script
 data() {
    return {
      str: "公众号“前端伪大叔”，欢迎大家前来关注！",
      str1:'qianduanweidashu'
    };
  },
//  这里filters是这个对象
  filters: {
//  自行输入长度
    length(e, num) {
      return e.slice(0, num) + "...";
    },
//  转为大写
    toUpperCase(e) {
      return e.toUpperCase();
    }
  }
```

## vue生命周期

https://cn.vuejs.org/v2/guide/instance.html

https://segmentfault.com/a/1190000020173042?utm_source=tag-newest

https://segmentfault.com/a/1190000014640577

vue周期函数中的mounted是代表已经渲染完了虚拟DOM，即VUE中的<templete></templete>

```
beforeCreate
created
beforeMount
mounted
beforeUpdate
updated
beforeDestroy
destroyed
```

```
- 什么是生命周期：从Vue实例创建、运行、到销毁期间，总是伴随着各种各样的事件，这些事件，统称为生命周期！
- [生命周期钩子](https://cn.vuejs.org/v2/api/#选项-生命周期钩子)：就是生命周期事件的别名而已；
- 生命周期钩子 = 生命周期函数 = 生命周期事件
- 主要的生命周期函数分类：

- 创建期间的生命周期函数：

- beforeCreate：实例刚在内存中被创建出来，此时，还没有初始化好 data 和 methods 属性
- created：实例已经在内存中创建OK，此时 data 和 methods 已经创建OK，此时还没有开始 编译模板
- beforeMount：此时已经完成了模板的编译，但是还没有挂载到页面中
- mounted：此时，已经将编译好的模板，挂载到了页面指定的容器中显示

- 运行期间的生命周期函数：

- beforeUpdate：状态更新之前执行此函数， 此时 data 中的状态值是最新的，但是界面上显示的 数据还是旧的，因为此时还没有开始重新渲染DOM节点
- updated：实例更新完毕之后调用此函数，此时 data 中的状态值 和 界面上显示的数据，都已经完成了更新，界面已经被重新渲染好了！

- 销毁期间的生命周期函数：

- beforeDestroy：实例销毁之前调用。在这一步，实例仍然完全可用。
- destroyed：Vue 实例销毁后调用。调用后，Vue 实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁。
```

## vue中的请求与接受

### 发送请求和接受

vue中发ajax在什么周期的create阶段

可以用jquery的ajax，或者axios，或者vue-resource

### vue-resource

ue-resource是Vue.js的一款插件，它可以通过XMLHttpRequest或JSONP发起请求并处理响应。也就是说，$.ajax能做的事情，vue-resource插件一样也能做到

https://www.cnblogs.com/chenhuichao/p/8308993.html

https://www.cnblogs.com/goloving/p/8665421.html

使用实例

```javascript
var demo = new Vue({
    el: '#app',
    data: {
        gridColumns: ['customerId', 'companyName', 'contactName', 'phone'],
        gridData: [],
        apiUrl: 'http://192.168.118.221:8080/api/customers'
    },
    mounted: function() {
        this.getCustomers()
    },
    methods: {
        getCustomers: function() {
            this.$http.get(this.apiUrl).then((response) => {
                this.$set('gridData', response.data)
            },(response) => {
                console.log("出错了");
            }).catch(function(response) {
                console.log(response)
            })
        }
    }
});
```

这段程序的then方法里提供了`successCallback`，`errorCallback`。catch方法用于捕捉程序的异常，catch方法和`errorCallback`是不同的，`errorCallback`只在响应失败时调用，而catch则是在整个请求到响应过程中，只要程序出错了就会被调用。

   在then方法的回调函数内，你也可以直接使用this，this仍然是指向Vue实例的。为了减少作用域链的搜索，建议使用一个局部变量来接收this。

## vue的动画

### 动画介绍

https://www.runoob.com/vue2/vue-transitions.html

```html
<transition name = "fade">
    <p v-show = "show" v-bind:style = "styleobj">动画实例</p>
</transition>
```



```vue
<div id = "databinding">
<button v-on:click = "show = !show">点我</button>
<transition name = "fade">
    <p v-show = "show" v-bind:style = "styleobj">动画实例</p>
</transition>
</div>
<script type = "text/javascript">
var vm = new Vue({
el: '#databinding',
    data: {
        show:true,
        styleobj :{
            fontSize:'30px',
            color:'red'
        }
    },
    methods : {
    }
});
</script>
```

```vue
<div id = "databinding">
<button v-on:click = "show = !show">点我</button>
<transition name="bounce">
    <p v-if="show">菜鸟教程 -- 学的不仅是技术，更是梦想！！！</p>
</transition>
</div>
<script type = "text/javascript">
new Vue({
    el: '#databinding',
    data: {
        show: true
    }
})
</script>
```

实例3：

```javascript
<div id="app">
    <input type="button" value="动起来" @click="myAnimate">
    <!-- 使用 transition 将需要过渡的元素包裹起来 -->
    <transition name="fade">
      <div v-show="isshow">动画哦</div>
    </transition>
  </div>
  
  
  // 创建 Vue 实例，得到 ViewModel
var vm = new Vue({
  el: '#app',
  data: {
    isshow: false
  },
  methods: {
    myAnimate() {
      this.isshow = !this.isshow;
    }
  }
});


/* css:定义进入和离开时候的过渡状态 */
    .fade-enter-active,
    .fade-leave-active {
      transition: all 0.2s ease;
      position: absolute;
    }

    /* 定义进入过渡的开始状态 和 离开过渡的结束状态 */
    .fade-enter,
    .fade-leave-to {
      opacity: 0;
      transform: translateX(100px);
    }
```

```
//vue动画添加

.v-enter,
.v-leave-to{
  /*  */
}

.v-enter-active,
.v-leave-active{
  /* transition: all 0.8s ease; */
}
```



### 使用动画钩子函数

定义 transition 组件以及三个钩子函数：

```
<div id="app">
    <input type="button" value="切换动画" @click="isshow = !isshow">
    <transition
    @before-enter="beforeEnter"
    @enter="enter"
    @after-enter="afterEnter">
      <div v-if="isshow" class="show">OK</div>
    </transition>
  </div>
```

定义三个 methods 钩子方法：

```
methods: {
        beforeEnter(el) { // 动画进入之前的回调
          el.style.transform = 'translateX(500px)';
        },
        enter(el, done) { // 动画进入完成时候的回调
          el.offsetWidth;
          el.style.transform = 'translateX(0px)';
          done();
        },
        afterEnter(el) { // 动画进入完成之后的回调
          this.isshow = !this.isshow;
        }
      }
```

定义动画过渡时长和样式：

```
.show{
      transition: all 0.4s ease;
    }
```

### v-for的列表过度

定义过渡样式：

```
<style>
    .list-enter,
    .list-leave-to {
      opacity: 0;
      transform: translateY(10px);
    }

    .list-enter-active,
    .list-leave-active {
      transition: all 0.3s ease;
    }
</style>
```

定义DOM结构，其中，需要使用 transition-group 组件把v-for循环的列表包裹起来：

```
  <div id="app">
    <input type="text" v-model="txt" @keyup.enter="add">

    <transition-group tag="ul" name="list">
      <li v-for="(item, i) in list" :key="i">{{item}}</li>
    </transition-group>
  </div>
```

定义 VM中的结构：

```
    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      data: {
        txt: '',
        list: [1, 2, 3, 4]
      },
      methods: {
        add() {
          this.list.push(this.txt);
          this.txt = '';
        }
      }
    });
```

## vue的组件

### 组件介绍

https://www.runoob.com/vue2/vue-component.html

https://cn.vuejs.org/v2/guide/components.html

https://www.cnblogs.com/penghuwan/p/7222106.html

https://www.jianshu.com/p/6dfb2d2cbc71

### 全局组件注册

https://www.cnblogs.com/zjh-study/p/10647652.html 

注册一个全局组件语法格式如下：

```
Vue.component(tagName, options)
```

tagName 为组件名，options 为配置选项。注册后，我们可以使用以下方式来调用组件：

```
<tagName></tagName>


```

```vue
<div id="app">
    <runoob></runoob>
</div>
 
<script>
// 注册
Vue.component('runoob', {
  template: '<h1>自定义组件!</h1>'
})
// 创建根实例
new Vue({
  el: '#app'
})
</script>
```

### 局部组件注册

```vue
<div id="app">
    <runoob></runoob>
</div>
 
<script>
var Child = {
  template: '<h1>自定义组件!</h1>'
}
 
// 创建根实例
new Vue({
  el: '#app',
  components: {
    // <runoob> 将只在父模板可用
    'runoob': Child
  }
})
</script>
```

### 页面引用组件

先在页面import abc from "xx",

然后在components:{

​	abc

}

### 父组件向子组件传值：Prop

无论是父传子还是子传父，父组件都运用了子组件

<child ></child>

https://blog.csdn.net/weixin_39051908/article/details/103683075
https://blog.csdn.net/weixin_38888773/article/details/81902789

https://www.jianshu.com/p/89bd18e44e73

props和data同级别

prop 是子组件用来接受父组件传递过来的数据的一个自定义属性。

父组件的数据需要通过 props 把数据传给子组件，子组件需要显式地用 props 选项声明 "prop"：



```vue
<div id="app">
    <child message="hello!"></child>
</div>
 
子组件方法：
<script>
// 注册
Vue.component('child', {
  // 声明 props
  props: ['message'],
  // 同样也可以在 vm 实例中像 "this.message" 这样使用
  template: '<span>{{ message }}</span>'
})
// 创建根实例
new Vue({
  el: '#app'
})
</script>
```

动态 Prop，父传子带参传

类似于用 v-bind 绑定 HTML 特性到一个表达式，也可以用 v-bind 动态绑定 props 的值到父组件的数据中。每当父组件的数据变化时，该变化也会传导给子组件

```vue
<div id="app">
    <div>
      <input v-model="parentMsg">
      <br>
      <child v-bind:message="parentMsg"></child>
    </div>
</div>
 
<script>
// 注册
Vue.component('child', {
  // 声明 props
  props: ['message'],
  // 同样也可以在 vm 实例中像 "this.message" 这样使用
  template: '<span>{{ message }}</span>'
})
// 创建根实例
new Vue({
  el: '#app',
  data: {
    parentMsg: '父组件内容'
  }
})
</script>
```

### 子组件向父组件传值

emit其实是向外输出一个事件x，然后接受的组件用@x = ""，进行接收


https://blog.csdn.net/weixin_38888773/article/details/81902789

简单案例：

```vue
父组件：
<template>
	<view class="content">
		<home @func="gethome"></home>
	</view>
</template>

<script>
	import home from '../home/home.vue'
	
	export default {
		data() {
			return {
			}
		},
		onLoad() {
		},
		 components:{
		        home,
		    },
		methods: {
			gethome(data){
				console.log(data)
			},
		}
	}
</script>

<style>
</style>
```

```vue
子组件
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
			this.$emit('func',"12345")
		},
		methods: {

		}
	}
</script>

<style>
</style>

```

1.原理：父组件将方法的引用，传递到子组件内部，子组件在内部调用父组件传递过来的方法，同时把要发送给父组件的数据，在调用方法的时候当作参数传递进去；

2.父组件将方法的引用传递给子组件，其中，`getMsg`是父组件中`methods`中定义的方法名称，`func`是子组件调用传递过来方法时候的方法名称

```vue
<son @func="getMsg"></son>
```

3.子组件内部通过`this.$emit('方法名', 要传递的数据)`方式，来调用父组件中的方法，同时把数据传递给父组件使用

```vue
<div id="app">
    <!-- 引用父组件 -->
    <son @func="getMsg"></son>

    <!-- 组件模板定义 -->
    <script type="x-template" id="son">
      <div>
        <input type="button" value="向父组件传值" @click="sendMsg" />
      </div>
    </script>
  </div>

  <script>
    // 子组件的定义方式
    Vue.component('son', {
      template: '#son', // 组件模板Id
      methods: {
        sendMsg() { // 按钮的点击事件
          this.$emit('func', 'OK'); // 调用父组件传递过来的方法，同时把数据传递出去
        }
      }
    });

    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      data: {},
      methods: {
        getMsg(val){ // 子组件中，通过 this.$emit() 实际调用的方法，在此进行定义
          alert(val);
        }
      }
    });
  </script>
```

### 自定义事件

- 使用 `$on(eventName)` 监听事件
- 使用 `$emit(eventName)` 触发事件

父组件是使用 props 传递数据给子组件，但如果子组件要把数据传递回去，就需要使用自定义事件！

我们可以使用 v-on 绑定自定义事件, 每个 Vue 实例都实现了事件接口(Events interface)，即：

```vue
<div id="app">
    <div id="counter-event-example">
      <p>{{ total }}</p>
      <button-counter v-on:increment="incrementTotal"></button-counter>
      <button-counter v-on:increment="incrementTotal"></button-counter>
    </div>
</div>
 
<script>
Vue.component('button-counter', {
  template: '<button v-on:click="incrementHandler">{{ counter }}</button>',
  data: function () {
    return {
      counter: 0
    }
  },
  methods: {
    incrementHandler: function () {
      this.counter += 1
      this.$emit('increment')
    }
  },
})
new Vue({
  el: '#counter-event-example',
  data: {
    total: 0
  },
  methods: {
    incrementTotal: function () {
      this.total += 1
    }
  }
})
</script>
```

!!!!!data 必须是一个函数

### 使用`flag`标识符结合`v-if`和`v-else`切换组件

```vue
<div id="app">
    <input type="button" value="toggle" @click="flag=!flag">
    <my-com1 v-if="flag"></my-com1>
    <my-com2 v-else="flag"></my-com2>
  </div>

<script>
    Vue.component('myCom1', {
      template: '<h3>奔波霸</h3>'
    })

    Vue.component('myCom2', {
      template: '<h3>霸波奔</h3>'
    })

    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      data: {
        flag: true
      },
      methods: {}
    });
  </script>
```

### $refs和ref来获取元素和组件

$refs类似document.getiid

ref则是标识

https://blog.csdn.net/lucynie/article/details/87188218

https://zhuanlan.zhihu.com/p/50638655

https://www.cnblogs.com/dengyao-blogs/p/11350292.html

https://segmentfault.com/q/1010000012922154/a-1020000012936937

如：

```vue
<div id="app">
    <div>
      <input type="button" value="获取元素内容" @click="getElement" />
      <!-- 使用 ref 获取元素 -->
      <h1 ref="myh1">这是一个大大的H1</h1>

      <hr>
      <!-- 使用 ref 获取子组件 -->
      <my-com ref="mycom"></my-com>
    </div>
  </div>

  <script>
    Vue.component('my-com', {
      template: '<h5>这是一个子组件</h5>',
      data() {
        return {
          name: '子组件'
        }
      }
    });

    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      data: {},
      methods: {
        getElement() {
          // 通过 this.$refs 来获取元素
          console.log(this.$refs.myh1.innerText);
          // 通过 this.$refs 来获取组件
          console.log(this.$refs.mycom.name);
        }
      }
    });
  </script>
```

## vue路由

### vue 如何获取路由

https://segmentfault.com/q/1010000017899565/
https://www.jb51.net/article/143371.htm

### 在 vue 中使用 vue-router

https://www.cnblogs.com/hahahakc/p/12938548.html

https://www.imooc.com/article/70052

https://www.jb51.net/article/119051.htm

1.导入 vue-router 组件类库：  

```
<!-- 1. 导入 vue-router 组件类库 -->
  <script src="./lib/vue-router-2.7.0.js"></script>
```

2.使用 router-link 组件来导航

```
<!-- 2. 使用 router-link 组件来导航 -->
<router-link to="/login">登录</router-link>
<router-link to="/register">注册</router-link>
```

3.使用 router-view 组件来显示匹配到的组件

```
<!-- 3. 使用 router-view 组件来显示匹配到的组件 -->
<router-view></router-view>
```

4.创建使用`Vue.extend`创建组件

```
    // 4.1 使用 Vue.extend 来创建登录组件
    var login = Vue.extend({
      template: '<h1>登录组件</h1>'
    });

    // 4.2 使用 Vue.extend 来创建注册组件
    var register = Vue.extend({
      template: '<h1>注册组件</h1>'
    });
```

5.创建一个路由 router 实例，通过 routers 属性来定义路由匹配规则

```
// 5. 创建一个路由 router 实例，通过 routers 属性来定义路由匹配规则
    var router = new VueRouter({
      routes: [
        { path: '/login', component: login },
        { path: '/register', component: register }
      ]
    });
```

6.使用 router 属性来使用路由规则

```
// 6. 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      router: router // 使用 router 属性来使用路由规则
    });
```

### 设置路由重定向和默认路由

路由重定向指的是，用户访问地址A的时候，强制用户跳转到地址B从而展示特定的组件页面；可以通过路由规则里的redirect属性，指定一个新的路由地址，可以很方便的设置路由重定向,具体代码演示`{path:"/",redirect:'/hone'}`

https://blog.csdn.net/weixin_46764048/article/details/105986641

https://blog.csdn.net/tangxiujiang/article/details/80145870

https://www.jb51.net/article/146755.htm

### 设置路由高亮

https://blog.csdn.net/woshidamimi0/article/details/98482701

https://blog.csdn.net/weixin_45616246/article/details/105588733?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.edu_weight&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.edu_weight

https://blog.csdn.net/icc_icc_icc/article/details/99654442

### 设置路由切换动效

https://blog.csdn.net/qq_40547061/article/details/105130058

https://www.cnblogs.com/dongdong1996/p/13364520.html?utm_source=tuicool

https://blog.csdn.net/lhban108/article/details/82528039

https://www.jb51.net/article/173279.htm

### 在路由规则中定义参数

1.在规则中定义参数：

```
{ path: '/register/:id', component: register }
```

2.通过 `this.$route.params`来获取路由中的参数：

```
var register = Vue.extend({
      template: '<h1>注册组件 --- {{this.$route.params.id}}</h1>'
    });
```

### 使用 `children` 属性实现路由嵌套

```vue
  <div id="app">
    <router-link to="/account">Account</router-link>

    <router-view></router-view>
  </div>

  <script>
    // 父路由中的组件
    const account = Vue.extend({
      template: `<div>
        这是account组件
        <router-link to="/account/login">login</router-link> | 
        <router-link to="/account/register">register</router-link>
        <router-view></router-view>
      </div>`
    });

    // 子路由中的 login 组件
    const login = Vue.extend({
      template: '<div>登录组件</div>'
    });

    // 子路由中的 register 组件
    const register = Vue.extend({
      template: '<div>注册组件</div>'
    });

    // 路由实例
    var router = new VueRouter({
      routes: [
        { path: '/', redirect: '/account/login' }, // 使用 redirect 实现路由重定向
        {
          path: '/account',
          component: account,
          children: [ // 通过 children 数组属性，来实现路由的嵌套
            { path: 'login', component: login }, // 注意，子路由的开头位置，不要加 / 路径符
            { path: 'register', component: register }
          ]
        }
      ]
    });

    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({
      el: '#app',
      data: {},
      methods: {},
      components: {
        account
      },
      router: router
    });
  </script>
```

### router-view 和 router-link 

路由出口:router-view

路由入口：router-link 

路由出口和入口为兄弟元素，页面还有其它路由，会发生子级路由不能准确匹配，无法渲染数据   

https://zhuanlan.zhihu.com/p/41368094

https://blog.csdn.net/qq_37581115/article/details/90488157

# nvue基础

## nvue是什么？

官网：

https://weex.apache.org/zh/

nvue是原生渲染，就是速度快

nvue是什么，和避开的坑：

https://www.cnblogs.com/hl1223/p/10384307.html

https://www.jianshu.com/p/6705eeb8eb3a

https://www.cnblogs.com/feng9exe/p/10907287.html

https://ask.dcloud.net.cn/question/94543

https://www.jianshu.com/p/9aff4b5f78e7

# ELECTRON-UI框架

## ELECTRON-VUE指南

教程：https://www.itying.com/category-86-b0.html?t=baidu
https://www.w3cschool.cn/electronmanual/
https://www.cnblogs.com/fqh123/p/11241280.html
https://segmentfault.com/a/1190000010648362
https://new.qq.com/omn/20181021/20181021A1218B.html?pc
https://simulatedgreg.gitbooks.io/electron-vue/content/cn/
https://electron.org.cn/vue/index.html

## ELECTRON-VUE坑

https://www.cnblogs.com/tylz/p/11813928.html
https://stackoverflow.com/questions/33922104/cannot-find-

module-electron
https://www.cnblogs.com/fqh123/p/11241280.html

# vue其他常用知识与方法技巧

## vue输入框清空

https://blog.csdn.net/QCIWYY/article/details/81059659

## 在vue加scss,less样式

https://www.cnblogs.com/ziChin/p/10272741.html

## 改变点击的元素的css

https://blog.csdn.net/katydids/article/details/83830002

## vue合并数组--`concat()`

`concat()`方法可以简单的将其理解为合并数组。

https://blog.csdn.net/qq_35192741/article/details/80655464

```javascript
var arr = [1,2];
console.log(arr); // [1, 2]
var arr2 = arr.concat();
console.log(arr2); // [1, 2]
```

## vue懒加载

当打包构建应用时，JavaScript 包会变得非常大，影响页面加载。如果我们能把不同路由对应的组件分割成不同的代码块，然后当路由被访问的时候才加载对应组件，这样就更加高效了。

https://router.vuejs.org/zh/guide/advanced/lazy-loading.html

https://segmentfault.com/a/1190000013579235

https://zhuanlan.zhihu.com/p/29433875

## 小球掉落动画

https://cubic-bezier.com/#.17,.67,.83,.67

## vuex vuex action 与mutations 的区别

https://www.cnblogs.com/0915ty/p/9626240.html
http://www.imooc.com/wenda/detail/449358
https://www.cnblogs.com/wupeng88/p/8931728.html

## vue修改css，用ref

https://blog.csdn.net/tan1071923745/article/details/81162667

## vue事件传值

https://blog.csdn.net/weixin_42467515/article/details/94621310

## vue提示框属性图标

https://www.cnblogs.com/tangwei89/p/11556887.html

## vue调用公共函数

https://blog.csdn.net/qq_32963841/article/details/84025623

## vue列表增加与删除

https://www.cnblogs.com/qiqisusu/p/11350726.html
删除
https://www.cnblogs.com/wanlibingfeng/p/9990190.html
Vue--findIndex方法的使用原理
https://www.cnblogs.com/mrszhou/p/7858992.html

## vue分页

https://blog.csdn.net/qq_41004440/article/details/89383229
https://element.eleme.cn/#/zh-CN/component/pagination
https://www.jianshu.com/p/70facd19ec55

## vue之虚拟dom

https://www.jianshu.com/p/af0b398602bc

## vue和小程序引入全局变量

https://blog.csdn.net/weixin_39051908/article/details/102841757
https://blog.csdn.net/m0_38082783/article/details/79907929

## vue引入jq,boostrap

https://blog.csdn.net/liuguiqian1/article/details/82712868
https://blog.csdn.net/qq_38945126/article/details/81510656

## router-link的样式可以通过.router-link-active改变

.router-link-active {
  text-decoration: none;
  color: #666666;
}

## vue引进css,js

https://www.cnblogs.com/luyuefeng/p/8349972.html
https://www.cnblogs.com/taohuaya/p/10651918.html

https://blog.csdn.net/weixin_41767649/article/details/82797801

## vue引入轮播图flexslider

https://blog.csdn.net/qq_32496215/article/details/81292051
https://blog.csdn.net/qq_32496215/article/details/81292051

如何使用轮播图
https://www.jianshu.com/p/bd8b27b1da8b

轮播图：

https://www.cnblogs.com/veinyin/p/9370113.html

## vue和php做前后端分离

https://www.zhihu.com/question/67171606/answer/249999064

## vue项目上线的坑

https://www.cnblogs.com/blueball/p/11328259.html
https://www.cnblogs.com/e-cat/p/9002728.html

vue上线图片加载不出来：

https://segmentfault.com/a/1190000017978188

## vue中的render，虚拟dom

https://blog.csdn.net/kkae8643150/article/details/52910389
https://www.cnblogs.com/vickylinj/p/9566474.html

## vue获取当前正在执行事件的元素

https://blog.csdn.net/webfront/article/details/80310763

## vue引入jq

https://blog.csdn.net/qq_38945126/article/details/81510656

## vue图片懒加载

http://www.jq22.com/jquery-info390
https://www.cnblogs.com/zzxuan/p/9690496.html
https://www.cnblogs.com/xyyt/p/7650539.html
https://blog.csdn.net/Mariosss/article/details/77712017
https://blog.csdn.net/weixin_38304202/article/details/78282826

动画+懒加载
https://www.cnblogs.com/axl234/p/5663153.html

## vue中的入口文件

https://blog.csdn.net/weixin_37331426/article/details/78410507

## vue的input事件

https://www.jianshu.com/p/ba141529d3c5

## 正能输入数字的正则表达式

https://blog.csdn.net/DreamFJ/article/details/94554007

# Vue各种工具

## Vue调试工具`vue-devtools`的安装步骤和使用

https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd?hl=zh-CN

## nrm

nrm 是一个 npm 源管理器，允许你快速地在 npm源间切换。

什么意思呢，npm默认情况下是使用npm官方源（使用npm config ls命令可以查看），在国内用这个源肯定是不靠谱的，一般我们都会用淘宝npm源：https://registry.npm.taobao.org/，修改源的方式也很简单，在终端输入：

如果哪天你又跑去国外了，淘宝源肯定是用不了的，又要切换回官网源，或者哪天你们公司有自己的私有npm源了，又需要切换成公司的源，这样岂不很麻烦？于是有了[nrm](https://github.com/Pana/nrm)。

https://www.cnblogs.com/Jimc/p/10280774.html

https://www.jianshu.com/p/94d084ce6834

## vue-preview

　Vue-preview是一个非常好用的移动端图片预览的组件，简单易用是它的一大特点，支持滑动换图，支持手势缩放，显示当前时第几张和总共多少张。

https://www.npmjs.com/package/vue-preview

https://www.cnblogs.com/ldq678/p/10917355.html

## vuex

https://vuex.vuejs.org/zh/guide/
https://www.cnblogs.com/chinabin1993/p/9848720.html

## mpvue

基于 Vue.js 的小程序开发框架

https://segmentfault.com/a/1190000015545555

### bootstrap 3 snippets

https://blog.csdn.net/weixin_42595418/article/details/81048083

## eliment-ui

vue的ui框架

https://blog.csdn.net/bingot/article/details/85071075
https://blog.csdn.net/pnjtvxcp/article/details/88413899
https://blog.csdn.net/Kiri_To/article/details/94402041