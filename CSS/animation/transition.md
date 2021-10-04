# transition 【过度】

> 复合属性

| 属性                                                         | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [transition](https://www.runoob.com/cssref/css3-pr-transition.html) | 此属性是 transition-property、transition-duration、transition-timing-function、transition-delay 的简写形式。 |
| [transition-property](https://www.runoob.com/cssref/css3-pr-transition-property.html) | 设置用来进行过渡的 CSS 属性。                                |
| [transition-duration](https://www.runoob.com/cssref/css3-pr-transition-duration.html) | 设置过渡进行的时间长度。                                     |
| [transition-timing-function](https://www.runoob.com/cssref/css3-pr-transition-timing-function.html) | 设置过渡进行的时序函数。                                     |
| [transition-delay](https://www.runoob.com/cssref/css3-pr-transition-delay.html) | 指定过渡开始的时间。                                         |

## transition-property【过度css属性】

> https://www.runoob.com/cssref/css3-pr-transition-property.html

```css
div
{
transition-property:width;
-moz-transition-property: width; /* Firefox 4 */
-webkit-transition-property:width; /* Safari and Chrome */
-o-transition-property:width; /* Opera */
}

div:hover {width:300px;}
```

**属性值；**

none——没有属性会获得过渡效果。

all——所有属性都将获得过渡效果。

property ——定义应用过渡效果的 CSS 属性名称列表，列表以逗号分隔。

## transition-duration【动画持续时间】

> https://www.runoob.com/cssref/css3-pr-transition-duration.html

```css
transition-duration: 5s;
-webkit-transition-duration: 5s; /* Safari */
```

**属性值；**

- 数字默认值为0；
- 单位以秒（s）或毫秒（ms）

## transition-timing-function【动画速度】

> https://www.runoob.com/cssref/css3-pr-transition-timing-function.html

```css
transition-timing-function: linear;
-webkit-transition-timing-function: linear; /* Safari and Chrome */
```

**属性值；**

- `linear` 规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。
- `ease` 规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。
- `ease-in` 规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
- `ease-out` 规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
- `ease-in-out` 规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
- `cubic-bezier(n,n,n,n)` 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。

## transition-delay【动画开始时间】

> https://www.runoob.com/cssref/css3-pr-transition-delay.html

```css
transition-delay: 2s;
-webkit-transition-delay: 2s; /* Safari */
```

**属性值；**

- 默认值为0；（及立刻开始）
- 数字，加单位为秒（s）或毫秒（ms）

