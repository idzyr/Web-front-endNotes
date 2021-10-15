# 盒模型

我们的网页本质是有大大小小的盒子组成。这些盒子叫做**标准盒子模型**

**标准盒子模型组成**

![img](box-model-images/%E6%A0%87%E5%87%86%E7%9B%92%E5%AD%90%E6%A8%A1%E5%9E%8B.png)

- margiin
- border
- padding



## 盒子尺寸计算

当为盒子指定padding和border属性后盒子尺寸会变大与实际尺寸不符。要想盒子尺寸不变那么只需要在指定盒子尺寸时去除border和padding的值。

### padding不影响盒子大小情况

> 如果没有给一个盒子指定宽度， 此时，如果给这个盒子指定padding， 则不会撑开盒子。

## 块级盒子水平居中

- 可以让一个块级盒子实现水平居中必须：
  - 盒子必须指定了宽度（width）
  - 然后就给**左右的外边距都设置为auto**，

实际工作中常用这种方式进行网页布局，示例代码如下：

```css
.header{ width:960px; margin:0 auto;}
```

常见的写法，以下下三种都可以。

- margin-left: auto; margin-right: auto;
- margin: auto;
- margin: 0 auto;

### 文字居中和盒子居中区别

1. 盒子内的文字水平居中是 text-align: center, 而且还可以让 行内元素和行内块居中对齐
2. 块级盒子水平居中 左右margin 改为 auto

```css
text-align: center; /*  文字 行内元素 行内块元素水平居中 */
margin: 10px auto;  /* 块级盒子水平居中  左右margin 改为 auto 就阔以了 上下margin都可以 */
```