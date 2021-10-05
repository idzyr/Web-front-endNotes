# 百度搜索框智能提示

> baiduSug.js
>
> http://www.baidu.com/js/opensug.js

效果展示；http://www.baidu.com/search/sug/demo1.html

## 使用baiduSug.js

**方法一；**

1. 给input元素添加

   `name="word"`和`baiduSug="1|2"`

    **属性。**

   - 当设置`baiduSug=1`时，用户选中sug词条时默认执行表单提交动作；
   - 当设置`baiduSug=2`时，用户选中sug词条时不执行表单提交动作。

2. 在body底部引入`<script charset="gbk" src="http://www.baidu.com/js/opensug.js"></script>`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>关键测匹配</title>
    <style>
        /* 隐藏百度的logo */
        .bdsug_copy {
            display: none;
        }
    </style>
</head>
<body>
方法一；<input type="text" style="width: 800px" placeholder="搜索" id="input" name="word" baiduSug="1">
<script charset="gbk" src="http://www.baidu.com/js/opensug.js"></script>
</body>
</html>、
```

**方法二；**

1. 引入`baiduSug.js`。

2. 在`baiduSug.js`下面编写，js脚本调用`BaiduSuggestion.bind()`方法。

   - `BaiduSuggestion.bind(inputObj|inputId,[params],[confirmCallback])` 为需要绑定搜索框提示功能的input对象或input对象的id。

     - inputObj|inputId ； input对象或input #id。

     - {params} 参数；

       'XOffset': 0, //提示框位置横向偏移量,单位px 'YOffset': 0, //提示框位置纵向偏移量,单位px 'width': 350, //提示框宽度，单位px 'fontColor': '#000', //提示框文字颜色 'fontColorHI': '#FFF', //提示框高亮选择时文字颜色 'fontSize': '12px', //文字大小 'fontFamily': '宋体', //文字字体 'borderColor': '#000', //提示框的边框颜色 'bgcolorHI': '#000', //提示框高亮选择的颜色 'sugSubmit': false //选中提示框中词条时是否提交表单

     - confirmCallback 回调函数，参数`txt`为用户选择的内容。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>关键测匹配</title>
    <style>
        /* 隐藏百度的logo */
        .bdsug_copy {
            display: none;
        }
    </style>
</head>
<body>
方法二；<input type="text" id="input1">
<script charset="gbk" src="http://www.baidu.com/js/opensug.js"></script>
<script>
    let input = document.getElementById("input1");
    let params = {}    //参数
    //绑定搜索对象
    BaiduSuggestion.bind(
        input,
        params,
        function (txt) {
            console.log("选择了" + txt);
        }
    )
</script>
</body>
</html>
```