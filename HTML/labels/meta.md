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