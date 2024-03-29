# CSS规范

## 代码格式化

样式书写一般有两种：一种是紧凑格式 (Compact)

```
.jdc{ display: block;width: 50px;}
```

一种是展开格式（Expanded）

```
.jdc {
    display: block;
    width: 50px;
}
```

**团队约定**

统一使用展开格式书写样式

### 代码大小写

样式选择器，属性名，属性值关键字全部使用小写字母书写，属性字符串允许使用大小写。

```
/* 推荐 */
.jdc{
    display:block;
}

/* 不推荐 */
.JDC{
    DISPLAY:BLOCK;
}
```

### 选择器

- 尽量少用通用选择器 `*`
- 不使用 ID 选择器
- 不使用无具体语义定义的标签选择器

```css
/* 推荐 */
.jdc {}
.jdc li {}
.jdc li p{}

/* 不推荐 */
*{}
#jdc {}
.jdc div{}
```

### 代码缩进

统一使用四个空格进行代码缩进，使得各编辑器表现一致（各编辑器有相关配置）

```
.jdc {
    width: 100%;
    height: 100%;
}
```

### 分号

每个属性声明末尾都要加分号；

```
.jdc {
    width: 100%;
    height: 100%;
}
```

### 代码易读性

左括号与类名之间一个空格，冒号与属性值之间一个空格

*推荐：*

```
.jdc { 
    width: 100%; 
}
```

*不推荐：*

```
.jdc{ 
    width:100%;
}
```

逗号分隔的取值，逗号之后一个空格

*推荐：*

```
.jdc {
    box-shadow: 1px 1px 1px #333, 2px 2px 2px #ccc;
}
```

*不推荐：*

```
.jdc {
    box-shadow: 1px 1px 1px #333,2px 2px 2px #ccc;
}
```

为单个css选择器或新申明开启新行

*推荐：*

```css
.jdc, 
.jdc_logo, 
.jdc_hd {
    color: #ff0;
}
.nav{
    color: #fff;
}
```

*不推荐：*

```css
.jdc,jdc_logo,.jdc_hd {
    color: #ff0;
}.nav{
    color: #fff;
}
```

颜色值 `rgb()` `rgba()` `hsl()` `hsla()` `rect()` 中不需有空格，且取值不要带有不必要的 0

*推荐：*

```
.jdc {
    color: rgba(255,255,255,.5);
}
```

*不推荐：*

```
.jdc {
    color: rgba( 255, 255, 255, 0.5 );
}
```

属性值十六进制数值能用简写的尽量用简写

*推荐：*

```
.jdc {
    color: #fff;
}
```

*不推荐：*

```css
.jdc {
    color: #ffffff;
}
```

不要为 `0` 指明单位

*推荐：*

```css
.jdc {
    margin: 0 10px;
}
```

*不推荐：*

```css
.jdc {
    margin: 0px 10px;
}
```

### 属性值引号

css属性值需要用到引号时，统一使用单引号

```css
/* 推荐 */
.jdc { 
    font-family: 'Hiragino Sans GB';
}

/* 不推荐 */
.jdc { 
    font-family: "Hiragino Sans GB";
}
```



## 属性

### 书写顺序(重点)

建议遵循以下顺序：

1. 布局定位属性：display / position / float / clear / visibility / overflow（建议 display 第一个写，毕竟关系到模式）
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

```css
.jdc {
    display: block;
    position: relative;
    float: left;
    width: 100px;
    height: 100px;
    margin: 0 10px;
    padding: 20px 0;
    font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
    color: #333;
    background: rgba(0,0,0,.5);
    -webkit-border-radius: 10px;
    -moz-border-radius: 10px;
    -o-border-radius: 10px;
    -ms-border-radius: 10px;
    border-radius: 10px;
}
```



## 样式文件分类

- 初始化css (css reset) 让浏览器风格统一，把常用的初始化语句放入 base.css里面。

- 我们把一些公共的样式 放入common.css里面。如浮动和版心等

  