# 伪类

> 基本所有元素都有的伪类

`hover`——鼠标悬停(鼠标划过)

`active`——鼠标点击（鼠标按下

`after`——访问后

## 触发伪类设置样式

### 为自身

```css
/*
选择器::伪类名{
    样式……
}

*/

div:hover{
    background-color: red;
}
```

### 子级

**格式；**

`父元素:伪类 子级元素{}`

````css
classA:hover classB{ 
	display:none; 
} 
````

### 兄弟关系,

**格式；**

`父元素:伪类+兄弟元素{}`

````css
classA: hover+classB{ 
	display:none; 
} 
````

