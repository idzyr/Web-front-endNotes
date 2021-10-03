# 定位（Positioning） 属性

| 属性                                                         | 说明                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [bottom](https://www.runoob.com/cssref/pr-pos-bottom.html)   | 设置定位元素下外边距边界与其包含块下边界之间的偏移   |
| [clear](https://www.runoob.com/cssref/pr-class-clear.html)   | 规定元素的哪一侧不允许其他浮动元素                   |
| [clip](https://www.runoob.com/cssref/pr-pos-clip.html)       | 剪裁绝对定位元素                                     |
| [cursor](https://www.runoob.com/cssref/pr-class-cursor.html) | 规定要显示的光标的类型（形状）                       |
| [display](https://www.runoob.com/cssref/pr-class-display.html) | 规定元素应该生成的框的类型                           |
| [float](https://www.runoob.com/cssref/pr-class-float.html)   | 规定框是否应该浮动                                   |
| [left](https://www.runoob.com/cssref/pr-pos-left.html)       | 设置定位元素左外边距边界与其包含块左边界之间的偏移   |
| [overflow](https://www.runoob.com/cssref/pr-pos-overflow.html) | 规定当内容溢出元素框时发生的事情                     |
| [position](https://www.runoob.com/cssref/pr-class-position.html) | 规定元素的定位类型                                   |
| [right](https://www.runoob.com/cssref/pr-pos-right.html)     | 设置定位元素右外边距边界与其包含块右边界之间的偏移   |
| [top](https://www.runoob.com/cssref/pr-pos-top.html)         | 设置定位元素的上外边距边界与其包含块上边界之间的偏移 |
| [visibility](https://www.runoob.com/cssref/pr-class-visibility.html) | 规定元素是否可见                                     |
| [z-index](https://www.runoob.com/cssref/pr-pos-z-index.html) | 设置元素的堆叠顺序                                   |

## position 【设置定位类型】

| 值                                                           | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [absolute](https://www.runoob.com/css/css-positioning.html#position-absolute) | 生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 |
| [fixed](https://www.runoob.com/css/css-positioning.html#position-fixed) | 生成固定定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 |
| [relative](https://www.runoob.com/css/css-positioning.html#position-relative) | 生成相对定位的元素，相对于其正常位置进行定位。因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。 |
| [static](https://www.runoob.com/css/css-positioning.html#position-static) | 默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。 |
| [sticky](https://www.runoob.com/css/css-positioning.html#position-sticky) | 粘性定位，该定位基于用户滚动的位置。它的行为就像 position:relative; 而当页面滚动超出目标区域时，它的表现就像 position:fixed;，它会固定在目标位置。**注意:** Internet Explorer, Edge 15 及更早 IE 版本不支持 sticky 定位。 Safari 需要使用 -webkit- prefix (查看以下实例)。 |

- relative（相对定位）

  偏移量；top，right，bottom，left

  A、 不影响元素本身的特性

  B、 不使元素脱离文档流

  C、 如果没有给元素加相对定位则设置的偏移量无效。

- absolute（绝对定位）

  A、 使元素完全脱离文档流

  B、 使内嵌元素支持宽高

  C、 块属性标签内容撑开宽度

  D、 绝对定位的偏移量是根据文档来定位的关系表；body<html<整个文档

  E、 如果有定位父级则相对于父级偏移，如果没有则相对于整个文档偏移

  F、 相对定位一般配合绝对定位使用

- 定位元素的层级关系；

  默认元素后者层级高于前者

  - 层级关系控制；

    z-index：（具体数字谁的数值大就优先显示）

## overflow 【内容溢出】

| 值      | 描述                                                     |
| ------- | -------------------------------------------------------- |
| visible | 默认值。内容不会被修剪，会呈现在元素框之外。             |
| hidden  | 内容会被修剪，并且其余内容是不可见的。                   |
| scroll  | 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。 |
| auto    | 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。 |

- `auto`——溢出显示滚动条
- `scroll`——默认显示滚动条
- `hidden`——溢出隐藏
- `overflow`可以检测浮动元素的溢出

## float【浮动】

| 值    | 描述                                                 |
| ----- | ---------------------------------------------------- |
| left  | 元素向左浮动。                                       |
| right | 元素向右浮动。                                       |
| none  | 默认值。元素不浮动，并会显示在其在文本中出现的位置。 |

### 浮动的特点

1. 解决了inline-block的缺点同时有继承了inline-block的优点

2. 脱离文档流 不占用空间

3. 元素加了浮动后会脱离文档流，会按指定方向移动直到碰到父级的边界或者另一个浮动元素

4. 提升层级半层，元素浮起的高度只够另一个元素挤进去元素上面的内容会被挤掉

   `clear：left/right/both/none`——元素的某个方向上不能有浮动元素

### 清浮动

1. 加浮动后父级保不住子级

2. 同样给父级加浮动

3. 给父级加display：inline-block

4. 给浮动元素下加一个空的div并且设置一下样式

   高度0px 字体大小0px clear：both

5. 在浮动元素下加
   all=both 不符合w3c标准

6. 给浮动元素的父级加（zoom：1）再加上一下样式

   After{content：“”；display：block；clear：both；}

7. 给浮动元素父级加overflow：auto 一定要配合zoom1



## display【元素的显示方式 】

| 值                 | 描述                                                         |
| :----------------- | :----------------------------------------------------------- |
| none               | 此元素不会被显示。                                           |
| block              | 此元素将显示为块级元素，此元素前后会带有换行符。             |
| inline             | 默认。此元素会被显示为内联元素，元素前后没有换行符。         |
| inline-block       | 行内块元素。（CSS2.1 新增的值）                              |
| list-item          | 此元素会作为列表显示。                                       |
| run-in             | 此元素会根据上下文作为块级元素或内联元素显示。               |
| compact            | CSS 中有值 compact，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| marker             | CSS 中有值 marker，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| table              | 此元素会作为块级表格来显示（类似 \<table>），表格前后带有换行符。 |
| inline-table       | 此元素会作为内联表格来显示（类似 \<table>），表格前后没有换行符。 |
| table-row-group    | 此元素会作为一个或多个行的分组来显示（类似 \<tbody>）。      |
| table-header-group | 此元素会作为一个或多个行的分组来显示（类似 \<thead>）。      |
| table-footer-group | 此元素会作为一个或多个行的分组来显示（类似 \<tfoot>）。      |
| table-row          | 此元素会作为一个表格行显示（类似 \<tr>）。                   |
| table-column-group | 此元素会作为一个或多个列的分组来显示（类似 \<colgroup>）。   |
| table-column       | 此元素会作为一个单元格列显示（类似 \<col>）                  |
| table-cell         | 此元素会作为一个表格单元格显示（类似 \<td> 和 \<th>）        |
| table-caption      | 此元素会作为一个表格标题显示（类似 \<caption>）              |


- block；显示为块
- inline；显示为内嵌