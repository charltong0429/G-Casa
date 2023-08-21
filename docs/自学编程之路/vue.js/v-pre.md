# v-pre

```vue
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
            <meta content="width=device-width, initial-scale=1.0" name="viewport">
                <title>
                    测试
                </title>
            </meta>
        </meta>
    </head>
    <body>
        <div id="app">
            <h2>
                {{message}}
            </h2>
            <h2 v-pre>
                {{message}} //原封不动的展示
            </h2>
            <h2 v-text="message">
            </h2>
        </div>
    </body>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js">
    </script>
    <script>
        const app = new Vue({
        el:'#app',
        data:{
            message:"我在这里"
        }
    });
    </script>
</html>
```