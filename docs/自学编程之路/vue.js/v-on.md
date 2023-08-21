# v-on
作用：注册事件 = 添加监听 + 提供处理逻辑
语法：
1. v-on：事件名=“内联语句”
2. v-on：事件名=“methods中的函数名”

```vue
<body>

    <div id="app">

      <p v-if="gender===1">性别：男</p>

      <p v-else>性别：女</p>

      <p>成绩是：{{score}}</p>

      <p>

        <button @click="change">Show不Show</button>

        <button @click="score++" v-show="isShow">修改成绩,用内联</button>

    </p>

      <p><button @click="fn">修改成绩,用methods</button></p>

      <hr />

      <p v-if="score>=90">成绩评定：A,奖励电脑一台</p>

      <p v-else-if="score>=80">成绩评定：B,奖励周末旅行一次</p>

      <p v-else-if="score>=60">成绩评定：C,奖励零食无限吃</p>

      <p v-else>成绩评定：D,奖励竹笋炒肉</p>

      <hr />

      <table>

        <tr>

          <th>Grade</th>

          <th>Count</th>

          <th>Statistic</th>

        </tr>

        <tr>

          <td>A</td>

          <td>{{A}}</td>

          <td>{{Math.ceil(A/total*100)}}%</td>

        </tr>

        <tr>

          <td>B</td>

          <td>{{B}}</td>

          <td>{{Math.ceil(B/total*100)}}%</td>

        </tr>

        <tr>

          <td>C</td>

          <td>{{C}}</td>

          <td>{{Math.ceil(C/total*100)}}%</td>

        </tr>

        <tr>

          <td>D</td>

          <td>{{D}}</td>

          <td>{{Math.ceil(D/total*100)}}%</td>

        </tr>

        <tr>

            <td>Total</td>

            <td>{{A+B+C+D}}</td>

  

        </tr>

      </table>

    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>

    <script>

      const app = new Vue({

        el: "#app",

        data: {

          gender: 2,

          score: 95,

          A: 0,

          B: 0,

          C: 0,

          D: 0,

          total:0,

          isShow:true,

        },

        methods: {

          fn() {

            this.score = Math.ceil(Math.random() * 100);

          },

          change(){

            this.isShow = !this.isShow

          }

        },

        watch: {

          score(newVal, oldVal) {

            console.log(newVal);

            if (newVal >= 90) {

              this.A++;

            } else if (newVal >= 80) {

              this.B++;

            } else if (newVal >= 60) {

              this.C++;

            } else {

              this.D++;

            };

            this.total= this.A+this.B+this.C+this.D

          },

        },

      });

    </script>

  </body>
```
v-on 的调用传参
```vue
<button @click="fn(can1,can2)">
	按钮
</button>


const app = new Vue({
	el:'#app',
	methods:{
		fn(a,b){
			do something!
		}	
	}
})
```

**小案例**
```vue
<div id="app">

      <div class="box">

        <h3>自动售货机</h3>

        <button @click="minus(5)">可乐5元</button>

        <button @click="minus(10)">咖啡10元</button>

      </div>

      <p>银行卡余额：{{amount}}元</p>

    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>

    <script>

      const app = new Vue({

        el: "#app",

        data: {

          amount:100,

        },

        methods: {

          minus(price){

            this.amount -= price

          }

        },

        watch: {

          amount(newVal, oldVal){

            if(newVal<0){

                alert('没钱了！不给买！')

                this.amount=oldVal

            }

          }

        },

      });

    </script>
```