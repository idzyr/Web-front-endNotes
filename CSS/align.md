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

### 图片、表单和文字对齐

所以我们知道，我们可以通过vertical-align 控制图片和文字的垂直关系了。 默认的图片会和文字基线对齐。

![img](align-images/%E5%9F%BA%E7%BA%BF%E5%AF%B9%E9%BD%90.jpg)

![1498467742995](file:///E:/%E6%95%99%E7%A8%8B/%E9%BB%91%E9%A9%AC%E5%89%8D%E7%AB%AF2019/%E3%80%9027%E3%80%91%E6%BA%90%E7%A0%81+%E8%AF%BE%E4%BB%B6+%E8%BD%AF%E4%BB%B6/01-03%20%E5%89%8D%E7%AB%AF%E5%BC%80%E5%8F%91%E5%9F%BA%E7%A1%80/02-CSS%E8%B5%84%E6%96%99/02-CSS%E8%B5%84%E6%96%99/CSS-Day07/%E7%AC%94%E8%AE%B0/media/1498467742995.png)