# Background【背景】

| [background-attachment](https://www.runoob.com/cssref/pr-background-attachment.html) | 设置或检索背景图像是随对象内容滚动还是固定的。必须先指定background-image属性。 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [background-color](https://www.runoob.com/cssref/pr-background-color.html) | 设置或检索对象的背景颜色。                                   |
| [background-image](https://www.runoob.com/cssref/pr-background-image.html) | 设置或检索对象的背景图像。                                   |
| [background-position](https://www.runoob.com/cssref/pr-background-position.html) | 设置或检索对象的背景图像位置。必须先指定background-image属性。 |
| [background-repeat](https://www.runoob.com/cssref/pr-background-repeat.html) | 设置或检索对象的背景图像如何铺排填充。必须先指定background-image属性。 |
| [background-clip](https://www.runoob.com/cssref/css3-pr-background-clip.html) | 指定对象的背景图像向外裁剪的区域。                           |
| [background-origin](https://www.runoob.com/cssref/css3-pr-background-origin.html) | S设置或检索对象的背景图像计算background-position时的参考原点(位置)。 |
| [background-size](https://www.runoob.com/cssref/css3-pr-background-size.html) | 检索或设置对象的背景图像的尺寸大小。                         |

## background-repeat

- `no-repeat;`——不重复
- `repeat-x;`——横向重复
- `repeat-y;`——纵向重复、
- `no-repeat 10px 50px`——控制图片的位置数值为0可以不加单位
- `center`——中间可以控制box里的图片剧中（左右居中）
- `center center`——左右居中并且上下居中

## background-attachement

| 值     | 描述                                       |
| ------ | ------------------------------------------ |
| scroll | 背景图片随着页面的滚动而滚动，这是默认的。 |
| fixed  | 背景图片不会随着页面的滚动而滚动。         |
| local  | 背景图片会随着元素内容的滚动而滚动。       |

## background-size

**值；**

cover——等比放大填充元素

contain——等比缩小填充元素

百分比；宽高

## background-position 

背景图片定位

设置背景图片的起始位置，要设置两个属性

第一个属性指图片从页面那个方向显示，第二个属性指图片从那个方向显示。



**注意：**

- 必须先指定background-image属性
- position 后面是x坐标和y坐标。 可以使用方位名词或者 精确单位。
- 如果指定两个值，两个值都是方位名字，则两个值前后顺序无关，比如left top和top left效果一致
- 如果只指定了一个方位名词，另一个值默认居中对齐。
- 如果position 后面是精确坐标， 那么第一个，肯定是 x 第二的一定是y
- 如果只指定一个数值,那该数值一定是x坐标，另一个默认垂直居中
- 如果指定的两个值是 精确单位和方位名字混合使用，则第一个值是x坐标，第二个值是y坐标





## background-origin

规定背景图片的定位区域

| 值          | 描述                       |
| :---------- | :------------------------- |
| padding-box | 背景图像填充框的相对位置   |
| border-box  | 背景图像边界框的相对位置   |
| content-box | 背景图像的相对位置的内容框 |

## background-clip

规定背景的绘制区域

| 值          | 说明                                             |
| :---------- | :----------------------------------------------- |
| border-box  | 默认值。背景绘制在边框方框内（剪切成边框方框）。 |
| padding-box | 背景绘制在衬距方框内（剪切成衬距方框）。         |
| content-box | 背景绘制在内容方框内（剪切成内容方框）。         |
