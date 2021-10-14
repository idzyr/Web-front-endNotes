# CSS介绍

> css格式为i键值对形式编写

```css
@charset "utf-8"; /* 指定文件编码 */
div{
    width: 200px;
    /* 注释 */
}

/* css格式
选择器{
    属性： 值;
    ……
}




*/
```

1. 多个选择器，使用一个样式，使用逗号分割选择。



## 引入样式

### 内联/行内样式

> 适合为某一个元素设置样式

通过元素的style属性设置，多个属性使用分号分割

```html
<div style="width:100px;height:100px">

</div>
```



### 内部样式表（内嵌样式表）

是将CSS代码集中写在HTML文档的head头部标签中，并且用style标签定义

```html
<head>
<style type="text/CSS">
    选择器（选择的标签） { 
      属性1: 属性值1;
      属性2: 属性值2; 
      属性3: 属性值3;
    }
</style>
</head>
<style>
     div {
         color: red;
         font-size: 12px;
     }
</style>
```

### 外部样式表（外链式）

 称链入式 是将所有的样式放在一个或多个以**.CSS**为扩展名的外部样式表文件中， 通过link标签将外部样式表文件链接到HTML文档中

```html
<head>
  <link rel="stylesheet" type="text/css" href="css文件路径">
</head>
```

link标签需要放在head头部标签中，并且指定link标签的三个属性

## 团队约定-代码风格

样式书写一般有两种：

- 一种是紧凑格式 (Compact)

```css
h3 { color: deeppink;font-size: 20px;}
```

- 一种是展开格式（推荐）

```css
h3 {
    color: deeppink;
    font-size: 20px;    
}
```

## 团队约定-代码大小写

样式选择器，属性名，属性值关键字全部使用小写字母书写，属性字符串允许使用大小写。

```css
/* 推荐 */
h3{
    color: pink;
}

/* 不推荐 */
H3{
    COLOR: PINK;
}
```



## 样式的优先级

> 不同设置样式方法的优先级

1. 同级默认后者覆盖前者
2. class选择器设置的样式优先级是比id小一级

**样式优先级公式；**

元素选择器 < class选择器 < id选择器 < style行间样式 < JavaScript



## 语句权重

在语句后面添加 !important

```css
#example {
  font-size: 14px !important; 
}
 
#container #example {
  font-size: 10px;
}       
```

 **解释**

在上面的代码示例中，由于使用了`!important`，id为“example”的元素字号将被设置为14px。

如果不使用`!important`，第二个样式声明的代码块很自然地比第一个的权重要大，原因有二：在样式表中第二个代码块要比第一个出现的晚（即，它位列第二）；第二个代码块有更大的权重（是由两个id，#container #example组合而成，而不是只有一个id，#example。但是因为第一个代码块里面包含了`!important`，所以对于字号设置来说它有更大的权重。

