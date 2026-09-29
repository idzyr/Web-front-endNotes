# 旋转木马

![rotate](carousel-images/rotate.gif)

## 思路

1. 默认图片都是叠在一起的
2. 调整每个图片的z轴位置拉开距离。
3. 调整每个图片的角度使其构成一个环形。
4. 第一张正对着我们的图片不用为其设置角度。
5. 旋转角度= 360deg 除以 6张图片

```html
 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>旋转木马</title>
    <style type="text/css">
        @keyframes rotate {
            from {
                transform: rotateY(0);
            }
            to {
                transform: rotateY(360deg);
            }
        }
        body {
            perspective: 800px;

        }
        section {
            position: relative;
            width: 300px;
            height: 212px;
            margin: 100px auto;
            transform-style: preserve-3d;
            animation: rotate 15s linear infinite;
        }
        section:hover{
            animation-play-state: paused;
        }
        section div {
            position: absolute;
            top: 0;
            left: 0;
            background: url(img/wk.png) no-repeat;
            width: 100%;
            height: 100%;
        }
        section div:nth-child(1){
            transform: translateZ(300px);
        }
        section div:nth-child(2){
            transform: rotateY(60deg) translateZ(300px);
        }
        section div:nth-child(3){
            transform: rotateY(120deg) translateZ(300px);
        }
        section div:nth-child(4){
            transform: rotateY(180deg) translateZ(300px);
        }
        section div:nth-child(5){
            transform: rotateY(240deg) translateZ(300px);
        }
        section div:nth-child(6){
            transform: rotateY(300deg) translateZ(300px);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </section>
</body>
</html>
```

