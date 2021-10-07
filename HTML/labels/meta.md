# 元信息

用来声明网页的一些信息，如编码，关键词，描述等。

| 属性                                                         | 值                                                           | 描述                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------------------------- |
| [charset](https://www.runoob.com/tags/att-meta-charset.html)**New** | 常用的值：<br/><br/>UTF-8 - Unicode 字符编码<br/>ISO-8859-1 - 拉丁字母表的字符编码 | 定义文档的字符编码。                         |
| [content](https://www.runoob.com/tags/att-meta-content.html) | *text*                                                       | 定义与 http-equiv 或 name 属性相关的元信息。 |
| [http-equiv](https://www.runoob.com/tags/att-meta-http-equiv.html) | content-type default-style refresh                           | 把 content 属性关联到 HTTP 头部。            |
| [name](https://www.runoob.com/tags/att-meta-name.html)       | application-name author description generator* *keywords     | 定义一个 HTML 文档的描述、关键词、作者：     |



## name属性值

| 值               | 描述                                                         |
| :--------------- | :----------------------------------------------------------- |
| application-name | 规定页面所代表的 Web 应用程序的名称。                        |
| author           | 规定文档的作者的名字。  实例： <meta name="author" content="Hege Refsnes"> |
| description      | 规定页面的描述。搜索引擎会把这个描述显示在搜索结果中。  实例： <meta name="description" content="Free web tutorials"> |
| generator        | 规定用于生成文档的一个软件包（不用于手写页面）。  实例： <meta name="generator" content="FrontPage 4.0"> |
| keywords         | 规定一个逗号分隔的关键词列表 - 相关的网页（告诉搜索引擎页面是与什么相关的）。  **提示：**总是规定关键词（对于搜索引擎进行页面分类是必要的）。  实例： <meta name="keywords" content="HTML, meta tag, tag reference"> |

为搜索引擎定义关键词:

```css
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
```

为网页定义描述内容:

```css
<meta name="description" content="免费 Web & 编程 教程">
```



定义网页作者:

```css
<meta name="author" content="Runoob">
```



## http-equiv

每30秒钟刷新当前页面:

```css
<meta http-equiv="refresh" content="30">
```

| content-type  | 规定文档的字符编码。  实例：  `<meta http-equiv="content-type"  content="text/html; charset=UTF-8">` |
| ------------- | ------------------------------------------------------------ |
| default-style | 规定要使用的预定义的样式表。  实例：  `<meta http-equiv="default-style" content="*the document's preferred  stylesheet*">`  **注释：**上面 content 属性的值必须匹配同一文档中的一个 link 元素上的 title 属性的值，或者必须匹配同一文档中的一个 style 元素上的 title 属性的值。 |
| refresh       | 定义文档自动刷新的时间间隔。  实例：  `<meta http-equiv="refresh"  content="300">`  注释：值 "refresh" 应该慎重使用，因为它会使得页面不受用户控制。在 [W3C's   Web 内容可访问性指南](http://www.w3.org/WAI/intro/wcag.php) 中使用 "refresh" 会到导致失败。 |

