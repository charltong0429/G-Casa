# v-if
作用：控制元素的隐藏与显示
**与v-show的区别：v-if，是干脆不渲染这个元素**，而v-show是通过css语句`display:none`来控制元素的显示与隐藏的。
语法：`v-if="true/false"`
```vue
<div id="app">
    <h2>{{message}}</h2> //这个会变
    <h2 v-if="true">{{message}}</h2> //这个不会变
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

# v-else 和 v-else-if
```vue
<body>

    <div id="app">

        <p v-if="gender===1">性别：男</p>

        <p v-else>性别：女</p>

        <hr>

        <p v-if="score>=90">成绩评定：A,奖励电脑一台</p>

        <p v-else-if="score>=80">成绩评定：B,奖励周末旅行一次</p>

        <p v-else-if="score>=60">成绩评定：C,奖励零食无限吃</p>

        <p v-else>成绩评定：D,奖励竹笋炒肉</p>

    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>

    <script>

        const app = new Vue({

            el:'#app',

            data:{

                gender:2,

                score:95

            }

        })

    </script>

</body>

</html>
```