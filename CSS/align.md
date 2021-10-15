# 对齐方式

## vertical-align 垂直对齐

- 有宽度的块级元素居中对齐，是margin: 0 auto;
- 让文字居中对齐，是 text-align: center;

但是我们从来没有讲过有垂直居中的属性。

vertical-align 垂直对齐，它只针对于**行内元素**或者**行内块元素**，

![img](align-images/xian.jpg)



```css
vertical-align : baseline |top |middle |bottom 
```

设置或检索对象内容的垂直对其方式。

**注意：**

vertical-align 不影响块级元素中的内容对齐，它只针对于**行内元素**或者**行内块元素**，

特别是行内块元素， **通常用来控制图片/表单与文字的对齐**。

q