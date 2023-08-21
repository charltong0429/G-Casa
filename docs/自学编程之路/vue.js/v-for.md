# v-for

循环遍历

```vue
<div id="app">
    <ul>
        <li v-for="book in book_list">{{book}}</li>
    </ul>
</div>
<script src="../js/vue.js"></script>
<scrpt>
    const app = new Vue({
    	el:"#app",
    	data:{
    		book_list=['雪山飞狐','侠客行','射雕英雄传']
    	}
    })
</scrpt>
```