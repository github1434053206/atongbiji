

# 简介



https://vuex.vuejs.org/zh/guide/
https://www.cnblogs.com/chinabin1993/p/9848720.html

# 使用

在store中创建一个index.js文件

```
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)



export default new Vuex.Store({
	state:{
		
	
	},
	
	getters:{
		
	},
	mutations:{
		
	},
	actions:{
		
	}
	
	
})
```

main.js文件

```
import Vue from 'vue'
import App from './App'
import store from "./store/index.js"

Vue.prototype.$store = store


Vue.config.productionTip = false

App.mpType = 'app'

const app = new Vue({
	store,
    ...App
})
app.$mount()
```

# mutations

和vue的methods差不多

# actions

把异步方法写在这里

# vuex的模块化

因为不能全部都写在同一个index.js文件中，所以拆分为多个目录管理，比如购物车的，可以弄一个目录里面放一个care.js文件。里面存放购物车的数据，统计总数，修改等方法。index.js作为主模块，类似于main.js看95章和97章

# modules:引入模块



# vuex与reactx比较：

https://www.jianshu.com/p/0ee7b413d4ff

