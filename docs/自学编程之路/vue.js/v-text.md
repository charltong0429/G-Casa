# v-text

```vue
<div id="app">
    <h2>{{message}}</h2>
    <h2 v-text="message">我会被覆盖</h2>
</div>
<script src="../js/vue.js"></script>
<scrpt>
    const app = new Vue({
    	el:"#app",
    	data:{
    		message:"我在这里"
    	}
    })
</scrpt>
```

这个不够灵活。