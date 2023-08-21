# v-html

```vue
<div id="app">
    <ul>
        <li v-for="book in book_list">{{book}}</li>
    </ul>
    <h2>
        {{url}}
    </h2>
</div>
<script src="../js/vue.js"></script>
<scrpt>
    const app = new Vue({
    	el:"#app",
    	data:{
    		book_list=['雪山飞狐','侠客行','射雕英雄传'],
    		url = "<a href='www.baidu.com'>百度一下</a>"
    	}
    })
</scrpt>
```