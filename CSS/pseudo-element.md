# 伪元素

## 元素列表

| 伪元素         | 说明                                      |
| -------------- | ----------------------------------------- |
| ::after        | 与content属性一起使用，定义在标签后的内容 |
| ::before       | 与content属性一起使用，定义在标签前的内容 |
| ::first-letter | 定义对象内第一个字符的样式                |
| ::first-line   | 定义对象内第一行的样式                    |

> 书写时建议使用两个冒号`::before` 格式这样比较容易和伪类选择器区分。

## 示例代码

```css
#user input{

  width: 200px;

  height: 30px;

  margin: 0px;

  padding: 0px;

  vertical-align: middle;

  border:none;

}

#user::before{

  content: '';

  width: 31px;

  height: 24px;

  display: inline-block;    /*默认是行内显示，没有高度的，要通过display属性来使得宽高起作用*/

  background: url("icon1.PNG") no-repeat;

  vertical-align: middle;

  margin: 0 2px 0 5px;  /*上右下左*/

 

}
```

