<!DOCTYPE html>
<html>

<head>
    <title>v-on指令</title>
    <script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
</head>

<body>
    <div id="app">
        <!-- 添加style样式进行居中展示 -->
        <div style="text-align: center;">
            <!-- 灯泡图片 -->
            <img :src="imgSrc" />
            <!-- 开关按钮 -->
            <button v-on:click="switchBulb">开关</button>
            <!-- 上一行代码可以简写为 -->
            <button @click="switchBulb">开关</button>
        </div>
    </div>
    <script>
        var vm = new Vue({
            el: '#app',
            data: {
                isUp: false,// 灯泡是否亮起
                lightUp: '../img/light-up.gif',  // 灯泡亮起的图片
                lightOut: '../img/light-out.gif',// 灯泡熄灭的图片
                imgSrc: '../img/light-out.gif'   // 绑定到img标签的src属性
            },
            methods: {
                // 开关灯
                switchBulb: function () {
                    if (this.isUp) {
                        // 如果灯是亮的，切换到熄灯状态
                        this.isUp = false;
                        // 并将灯的图片切换为熄灯图片
                        this.imgSrc = this.lightOut;
                    } else {
                        this.isUp = true;
                        this.imgSrc = this.lightUp;
                    }
                }
            }
        });
    </script>
</body>

</html>