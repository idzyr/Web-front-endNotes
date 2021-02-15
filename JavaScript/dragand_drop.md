# 拖放



## 步骤

**流程；** 鼠标长按开始拖放=>拖放到目标元素上=>松开鼠标拖放结束

> **注意；**
>
> ​	默认元素是不可以接收元素之间的拖拽处理。也就是说将A元素拖拽到B元素上是不受支持的。

1. 设置被拖动元素为可拖放

   ```css
   draggable="true"
   ```

   

2. `ondragstart(event)` 设置当元素开始拖动时处理那些数据被传递到目标元素。

   ```javascript
      function ondragstartHandle(ev){
               /*
                   dataTransfer设置数据传输
                   setData(类型,数据源) 设置被传输数据。
                   下面的代码就是将发生拖动元素的id属性会被传输到接收拖放的元素。
               */
               ev.dataTransfer.setData("Text",ev.target.id);
           }
   
   ```

   

   

3. `ondragover(event)`当有被拖放的元素，被拖拽到此元素上时处理。

   ```javascript
    function ondragoverHandle(ev){
               //阻止浏览器对此事件的默认处理。
               ev.preventDefault();
        		//因为元素之间是无法相互接收被拖拽元素的。当我们禁用了默认事件处理就可以接收了。
           }
   ```

   

   

4. `ondrop(enent)`设置接受拖放元素的拖放结束事件处理函数

```javascript
function ondropHandle(ev){
            //阻止浏览器对此事件的默认处理。
            ev.preventDefault();
    		//获取被拖放元素传递的数据
            let data = ev.dataTransfer.getData("Text");
    		//对数据处理
            ev.target.appendChild(document.getElementById(data));
        }
```

**完整代码；**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #box{
           width: 200px; 
           height: 300px;
           border: 1px solid red;
        }
    </style>
</head>
<body>

    <div id="box" ondragover="ondragoverHandle(event)" ondrop="ondropHandle(event)"></div>
    <img id="img" draggable="true" ondragstart="ondragstartHandle(event)" src="https://www.runoob.com/wp-content/uploads/2013/07/pic_html5.gif">
    
    <script>
        function ondragstartHandle(ev){
            /*
                dataTransfer设置数据传输
                setData(类型,数据源) 设置被传输数据。
                下面的代码就是将发生拖动元素的id属性会被传输到接收拖放的元素。
            */
            ev.dataTransfer.setData("Text",ev.target.id);
        }

        function ondragoverHandle(ev){
            //阻止浏览器对此事件的默认处理。
            ev.preventDefault();
        }

        function ondropHandle(ev){
            //阻止浏览器对此事件的默认处理。
            ev.preventDefault();
            let data = ev.dataTransfer.getData("Text");
            ev.target.appendChild(document.getElementById(data));
        }
    </script>

</body>
</html>
```



