# 默认样式重置

> 目的为了兼容大部分浏览器

- body标签默认有一个8像素的外边框（margin）
- p标签也有一个16像素的上下外边距
- h标题标签也有外边距
- ol和ul都有样式（list-style:none），内外边距也有（padding和margin）
- dl 和 dd都有外边距（margin）
- font-family XX（字体样式）
- inmg（border:none边框）
- th，td{ padding：0px} 表头和单元格
- Form；margin:0
- Input；margin：0 padding：0
- select；margin：0
- textarea；margin：0 padding：0

##  去除图片底侧空白缝隙

![img](default-style-reset-images/35vertical.png)



**原因：**

图片或者表单等行内块元素，他的底线会和父级盒子的基线对齐。

就是图片底侧会有一个空白缝隙。

**解决的方法就是：**

- `给img vertical-align:middle | top| bottom`等等。 让图片不要和基线对齐。
- 给img 添加 display：block; 转换为块级元素就不会存在问题了。

## Normalize.css

> 第三方的css样式初始化库

https://necolas.github.io/normalize.css/

