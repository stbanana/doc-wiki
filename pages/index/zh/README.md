---
title: 土星环的图书馆
keywords: 哈喽~欢迎光临
desc: yono 的 wiki 文档站
id: home_page
---

<div>
    <!-- <script src="/static/js/scrolloverflow.min.js"></script> -->
    <script src="/static/js/jquery.fullpage.min.js"></script>
    <link rel="stylesheet" href="/static/css/jquery.fullpage.min.css" type="text/css" />
</div>

<div id="fullpage">
    <div class="section" style="height: 70vh;">
        <div>
            <h1><span>wiki</span></h1>
        </div>
        <div>
            <a>好耶~ 我们找到了！</a>
        </div>
        <!-- <div class="big_btn_wrapper">
            <div class="big_btn">
                <a href="/modbusX/zh_hans/">modbusX</a>
            </div>
        </div> -->
    </div>
</div>


<canvas id="backgroundCanvas" style="top:0; bottom:0; left:0; right:0; position:fixed; z-index: -99;">
</canvas>

<canvas id="backgroundCanvas" style="top:0; bottom:0; left:0; right:0; position:fixed; z-index: -99;">
</canvas>
<script>
    var isDark = false;
    function createCanvas(dark = null) {
        var c = document.getElementById("backgroundCanvas");
        c.height = document.body.clientHeight;
        c.width = document.body.clientWidth;
        var ctx = c.getContext("2d");
        if (dark == null) {
            if (getTheme() == "dark") {
                dark = true;
            } else {
                dark = false;
            }
        }
        if (dark) {
            ctx.fillStyle = "#171717";
            isDark = true;
        } else {
            ctx.fillStyle = "#f6f6f6";
            isDark = false;
        }
        var rect = [
            [0.05, 0.3, 0.05, 0.03],
            [0.1, 0.6, 0.05, 0.03],
            [0.12, 0.4, 0.05, 0.13],
            [0.22, 0.35, 0.13, 0.12],
            [0.05, 0.8, 0.1, 0.1],
            [0.18, 0.7, 0.16, 0.14],
            [0.95, 0.2, 0.05, 0.03],
            [0.9, 0.6, 0.05, 0.03],
            [0.7, 0.5, 0.05, 0.13],
            [0.78, 0.35, 0.13, 0.12],
            [0.8, 0.8, 0.16, 0.14],
            [0.6, 0.7, 0.1, 0.24],
        ];
        rect.forEach(function (v, index, array) {
            ctx.fillRect(v[0] * c.width, v[1] * c.height, v[2] * c.width, v[3] * c.height);
        });
    }
    $(window).resize(function () {
        createCanvas();
    });
    $("#themes").on("click", function () {
        createCanvas(!isDark);
    });
    $().ready(function () {
        createCanvas();
    });
</script>