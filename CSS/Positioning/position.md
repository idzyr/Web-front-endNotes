# position 【设置定位类型】

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
