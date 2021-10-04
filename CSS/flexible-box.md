# 弹性盒子（伸缩布局）

## 指定弹性盒子步骤

1. 对div的display属性，设置为flex
2. 设置对应的盒模型属性。

**注意；**

盒子水平方向叫**横轴**垂直叫**侧轴**

## 新旧盒模型属性

### Flexible Box 属性(新)

| 属性                                                         | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [flex](https://www.runoob.com/cssref/css3-pr-flex.html)      | 复合属性。设置或检索弹性盒模型对象的子元素如何分配空间。     |
| [flex-grow](https://www.runoob.com/cssref/css3-pr-flex-grow.html) | 设置或检索弹性盒的扩展比率。                                 |
| [flex-shrink](https://www.runoob.com/cssref/css3-pr-flex-shrink.html) | 设置或检索弹性盒的收缩比率。                                 |
| [flex-basis](https://www.runoob.com/cssref/css3-pr-flex-basis.html) | 设置或检索弹性盒伸缩基准值。                                 |
| [flex-flow](https://www.runoob.com/cssref/css3-pr-flex-flow.html) | 复合属性。设置或检索弹性盒模型对象的子元素排列方式。         |
| [flex-direction](https://www.runoob.com/cssref/css3-pr-flex-direction.html) | 该属性通过定义flex容器的主轴方向来决定felx子项在flex容器中的位置。 |
| [flex-wrap](https://www.runoob.com/cssref/css3-pr-flex-wrap.html) | 该属性控制flex容器是单行或者多行，同时横轴的方向决定了新行堆叠的方向。 |
| [align-content](https://www.runoob.com/cssref/css3-pr-align-content.html) | 在弹性容器内的各项没有占用交叉轴上所有可用的空间时对齐容器内的各项（垂直）。 |
| [align-items](https://www.runoob.com/cssref/css3-pr-align-items.html) | 定义flex子项在flex容器的当前行的侧轴（纵轴）方向上的对齐方式。 |
| [align-self](https://www.runoob.com/cssref/css3-pr-align-self.html) | 定义flex子项单独在侧轴（纵轴）方向上的对齐方式。             |
| [justify-content](https://www.runoob.com/cssref/css3-pr-justify-content.html) | 设置或检索弹性盒子元素在主轴（横轴）方向上的对齐方式。       |
| [order](https://www.runoob.com/cssref/css3-pr-order.html)    | 设置或检索弹性盒模型对象的子元素出现的順序。                 |

### Flexible Box 属性(旧)

| 属性                                                         | 说明                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [box-align](https://www.runoob.com/cssref/css3-pr-box-align.html) | 指定如何对齐一个框的子元素                           |
| [box-direction](https://www.runoob.com/cssref/css3-pr-box-direction.html) | 指定在哪个方向，显示一个框的子元素                   |
| [box-flex](https://www.runoob.com/cssref/css3-pr-box-flex.html) | 指定一个框的子元素是否是灵活的或固定的大小           |
| [box-flex-group](https://www.runoob.com/cssref/css3-pr-box-flex-group.html) | 指派灵活的元素到Flex组                               |
| [box-lines](https://www.runoob.com/cssref/css3-pr-box-lines.html) | 每当它在父框的空间运行时，是否指定将再上一个新的行列 |
| [box-ordinal-group](https://www.runoob.com/cssref/css3-pr-box-ordinal-group.html) | 指定一个框的子元素的显示顺序                         |
| [box-orient](https://www.runoob.com/cssref/css3-pr-box-orient.html) | 指定一个框的子元素是否在水平或垂直方向应铺设         |
| [box-pack](https://www.runoob.com/cssref/css3-pr-box-pack.html) | 指定横向盒在垂直框的水平位置和垂直位置               |

## Flexible 属性详解

### flex-direction 【设置盒子方向】

> https://www.runoob.com/cssref/css3-pr-flex-direction.html

```css
div
{
    display:flex;
    flex-direction:row-reverse;
}
```

**属性值；**

- `row`——水平显示（默认）
- `row-reverse`——水平反向显示
- `column`——垂直显示
- `column-reverse`——垂直反向显示

### justify-content【子元素在主轴方向上的对齐方式】

> 横轴 https://www.runoob.com/cssref/css3-pr-justify-content.html

```css
div
{
    display: flex;
    justify-content: space-around;
}
```

**属性值；**

- `flex-start`——位于盒子开头
- `flex-end`——位于盒子结尾
- `center`——位于中心
- `space-between`——各内容之间保留有空白
- `space-around`——各内容之间保留空白且首位也保留

### align-items（子元素在侧轴方向上的对齐方式）

> 垂直 https://www.runoob.com/cssref/css3-pr-align-items.html

```css
div
{
    display: flex;
    align-items:center;
}
```

**属性值；**

- `stretch`——拉伸适应容器（默认）
- `center`——位于容器的中心
- `flex-start`——位于容器的开头
- `flex-end`——位于容器的结尾
- `baseline`——内容基线就是行高来对齐

### flex-wrap【子元素是否要换行】

> https://www.runoob.com/cssref/css3-pr-flex-wrap.html

```css
div{
    display: flex;
    flex-wrap: wrap;
}
```

**属性值；**

- nowarp——不换行（默认值）
- warp——换行

### align-content【子元素强制换行后对齐方式的调节】

> https://www.runoob.com/cssref/css3-pr-align-content.html

```css
div
{
    display: flex;
    flex-flow: row wrap;    // 是flex-direction 和 flex-wrap 的简写。
    align-content:space-around;
}
```

**属性值；**

- `flex-start`——位于盒子开头
- `flex-end`——位于盒子结尾
- `center`——位于中心
- `space-between`——各内容之间保留有空白
- `space-around`——各内容之间保留空白且首位也保留

### flex 【子元素如何分配弹性盒子内的空间】

> https://www.runoob.com/cssref/css3-pr-flex.html

```css
#main div
{
    flex:1;
}
```

**属性值；**

flex：数字比例/或百分比。

**注意；**

此分配的是弹性盒子**剩余**的空间

### order 【改变子元素的顺序】

```css
div#myRedDIV {order:2;}
div#myBlueDIV {order:4;}
div#myGreenDIV {order:3;}
div#myPinkDIV {order:1;}
```

**属性值；**

order：数字；——数值越大越靠前