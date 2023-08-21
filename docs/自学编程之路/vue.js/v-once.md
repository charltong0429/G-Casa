# v-once

```vue
<div id="app">
    <h2>{{message}}</h2> //这个会变
    <h2 v-once>{{message}}</h2> //这个不会变
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

适用场景：当某值发生改变时，某些展示这个值的地方不发生改变

可以在console里，使用`app.massage="XXXX"`来改变值，用以测试。