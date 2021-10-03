# 属性

## 简便属性

| 属性   | 作用     |
| ------ | -------- |
| width  | 设置宽度 |
| height | 设置高度 |

## 复杂属性

**复合属性常用方位词**；

top 上（顶）

right 右

bottom 下（底）

left 左

**顺序；**

top——right——bottom——left

### 什么是复合属性

复杂属性也叫复合属性其有两种形式其一通过拆分的属性来指定值，如常见的属性名加方位词组合实现为标签的某一方位上来指定属性样式，另一种形式就是通过一个大属性来，指定其所有拆分属性的值。

如 `border`属性，我们可以通过这个属性来一次指定大小，样式，颜色，每个值之间使用空格分割。

```css
border:2px solid blue; /*复合属性*/

/* 拆分指定 */
border-width: 2px;
border-style: solid;
border-color: blue;
```

