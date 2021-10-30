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



## visibility

| 值       | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| visible  | 默认值。元素是可见的。                                       |
| hidden   | 元素是不可见的。                                             |
| collapse | 当在表格元素中使用时，此值可删除一行或一列，但是它不会影响表格的布局。被行或列占据的空间会留给其他内容使用。如果此值被用在其他的元素上，会呈现为 "hidden"。 |
| inherit  | 规定应该从父元素继承 visibility 属性的值。                   |

## 堆叠顺序（z-index）

在使用**定位**布局时，可能会**出现盒子重叠的情况**。

加了定位的盒子，默认**后来者居上**， 后面的盒子会压住前面的盒子。

应用 `z-index` 层叠等级属性可以**调整盒子的堆叠顺序**。如下图所示：

![zindex示意图](positioning-attributes-images/12_zindex%E7%A4%BA%E6%84%8F%E5%9B%BE.png)

`z-index` 的特性如下：

1. **属性值**：**正整数**、**负整数**或 **0**，默认值是 0，数值越大，盒子越靠上；
2. 如果**属性值相同**，则按照书写顺序，**后来居上**；
3. **数字后面不能加单位**。

**注意**：`z-index` 只能应用于**相对定位**、**绝对定位**和**固定定位**的元素，其他**标准流**、**浮动**和**静态定位**无效。



