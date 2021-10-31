# HTNL规范

## DOCTYPE 声明

HTML文件必须加上 DOCTYPE 声明，并统一使用 HTML5 的文档声明：

```html
<!DOCTYPE html>
```

**HTML5标准模版**

```html
<!DOCTYPE html>
  <html lang="zh-CN">
  <head>
  <meta charset="UTF-8">
  <title>HTML5标准模版</title>
  </head>
  <body>

  </body>
</html>
```

### 页面语言lang

推荐使用属性值 `cmn-Hans-CN`（简体, 中国大陆），但是考虑浏览器和操作系统的兼容性，目前仍然使用 `zh-CN` 属性值

```
<html lang="zh-CN">
```

更多地区语言参考：

```
zh-SG 中文 (简体, 新加坡)   对应 cmn-Hans-SG 普通话 (简体, 新加坡)
zh-HK 中文 (繁体, 香港)     对应 cmn-Hant-HK 普通话 (繁体, 香港)
zh-MO 中文 (繁体, 澳门)     对应 cmn-Hant-MO 普通话 (繁体, 澳门)
zh-TW 中文 (繁体, 台湾)     对应 cmn-Hant-TW 普通话 (繁体, 台湾)
```

### charset 字符集合

一般情况下统一使用 “UTF-8” 编码

```
<meta charset="UTF-8">
```

由于历史原因，有些业务可能会使用 “GBK” 编码

```
<meta charset="GBK">
```

请尽量统一写成标准的 “UTF-8”，不要写成 “utf-8” 或 “utf8” 或 “UTF8”。根据 [IETF对UTF-8的定义](http://www.ietf.org/rfc/rfc3629)，其编码标准的写法是 “UTF-8”；而 UTF8 或 utf8 的写法只是出现在某些编程系统中，如 .NET framework 的类 System.Text.Encoding 中的一个属性名就叫 UTF8。

## 书写风格

### HTML代码大小写

HTML标签名、类名、标签属性和大部分属性值统一用小写

*推荐：*

```
<div class="demo"></div>
```

*不推荐：*

```
<div class="DEMO"></div>

<DIV CLASS="DEMO"></DIV>
```

### 类型属性

不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含

*推荐：*

```
<link rel="stylesheet" href="" >
<script src=""></script>
```

*不推荐：*

```
<link rel="stylesheet" type="text/css" href="" >
<script type="text/javascript" src="" ></script>
```

### 元素属性

- 元素属性值使用双引号语法
- 元素属性值可以写上的都写上

*推荐：*

```
<input type="text">
<input type="radio" name="name" checked="checked" >
```

*不推荐：*

```
<input type=text>    
<input type='text'>
<input type="radio" name="name" checked >
```

### 特殊字符引用

文本可以和字符引用混合出现。这种方法可以用来转义在文本中不能合法出现的字符。

在 HTML 中不能使用小于号 “<” 和大于号 “>”特殊字符，浏览器会将它们作为标签解析，若要正确显示，在 HTML 源代码中使用字符实体

*推荐：*

```
<a href="#">more&gt;&gt;</a>
```

*不推荐：*

```
<a href="#">more>></a>
```

### 代码缩进

统一使用四个空格进行代码缩进，使得各编辑器表现一致（各编辑器有相关配置）

```
<div class="jdc">
    <a href="#"></a>
</div>
```

### 代码嵌套

元素嵌套规范，每个块状元素独立一行，内联元素可选

*推荐：*

```
<div>
    <h1></h1>
    <p></p>
</div>    
<p><span></span><span></span></p>
```

*不推荐：*

```
<div>
    <h1></h1><p></p>
</div>    
<p> 
    <span></span>
    <span></span>
</p>
```

段落元素与标题元素只能嵌套内联元素

*推荐：*

```
<h1><span></span></h1>
<p><span></span><span></span></p>
```

*不推荐：*

```
<h1><div></div></h1>
<p><div></div><div></div></p>
```

