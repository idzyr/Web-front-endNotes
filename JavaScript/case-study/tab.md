# Tab选项卡

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>选项卡</title>
    <style>
        div {
            width: 200px;
            height: 100px;
            border: 1px solid red;
            display: none;
        }
    </style>
</head>
<body>
<input type="button" value="选择一" style="background: deeppink">
<input type="button" value="选择二">
<input type="button" value="选择三">
<div style="display: block">内容1</div>
<div>内容2</div>
<div>内容3</div>
<script>
    /*
    * 实现概要；
    * 1. 找到上次被点击的input对象。
    * 2. 去除上次被点击input的background和隐藏其对应的div。
    * 3. 改变当前被点击input的background和显示对应的div。
    * */
    let inputs = document.querySelectorAll("input");
    let divs = document.querySelectorAll("div");

    //默认被选中的input相对于用户要点击的一个input来说就是上一个被点击的input
    let lastItem = inputs[0]; //记录上一次被点击的选项对象。

    //给所有的input注册点击事件
    for (let i = 0; i < inputs.length; i++) {
        inputs[i].index = i;    //为input对象添加一个自定义属性。方便根据索引来查找对应对象。

        //为每一个input注册点击事件，处理程序。
        inputs[i].onclick = function () {
            /*
            *  了解，这里input的索引和divs的索引都是一一对应的,所以能通过input的索引来找到对应div。
            * */
            /*—————————处理上次被点击对象————————————————————*/
            inputs[lastItem.index].style.background = "";   //去除上次被点击对象的背景色。
            divs[lastItem.index].style.display = "none";

            /*———————————显示当前对象——————————————————*/
            inputs[this.index].style.background = "deeppink"; //更改当前标签为激活状态。
            divs[this.index].style.display = "block";   //显示对应标签页。

            //更新。一下上次被点击对象。
            //为啥这样写，当前被激活的对象，相对与下一个被激活的对象来说，就是其上一个被点击的对象。
            lastItem = this;

        }
    }


</script>
</body>
</html>
```