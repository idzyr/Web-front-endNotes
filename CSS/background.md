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

