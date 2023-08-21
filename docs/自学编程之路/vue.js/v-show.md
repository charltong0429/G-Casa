# v-show
作用：控制元素的隐藏与显示
语法：`v-show="true/false"`
```vue
<div id="app">
    <h2>{{message}}</h2> //这个会变
    <h2 v-show="true">{{message}}</h2> //这个不会变
</div>
<script src="../js/vue.js"></script>
<scrpt>
    const app = new Vue({
    	el:"#app",
    	data:{
    		message:"你好呀"
    	}
    })
</scrpt>
```










vue 2 和3 有很大的不同