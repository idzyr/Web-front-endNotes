# @规则

> https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule#nested

**@规则**是指示 CSS 如何表现的CSS 语句。它们以 @符号( `U+0040 COMMERCIAL AT`) 开头，后跟一个标识符，包括直到下一个分号 ' `;`' ( `U+003B SEMICOLON`) 或下一个CSS 块的所有内容，以先到者为准。

## 句法

### 常规的

```css
/* 一般结构 */
@标识符 (规则);

/* 示例：告诉浏览器使用 UTF-8 字符集 */
@charset "utf-8";
```



## 其它标识符

### 常规的

- `@charset` — 定义样式表使用的字符集。
- `@import` — 告诉 CSS 引擎包含一个外部样式表。
- `@namespace` — 告诉 CSS 引擎，它的所有内容都必须被视为以 XML 命名空间为前缀。

### 嵌套

```css
@标识符 (RULE) {

}
```



- `@media`— 如果设备满足使用*媒体查询*定义的条件的标准，则将应用其内容的条件组规则。
- `@supports` — 如果浏览器满足给定条件的标准，则将应用其内容的条件组规则。
- `@document` — 如果应用样式表的文档满足给定条件的标准，则将应用其内容的条件组规则。*（推迟到 CSS 规范的第 4 级）*
- `@page` — 描述打印文档时将应用的布局更改方面。
- `@font-face` — 描述要下载的外部字体的方面。
- `@keyframes` — 描述 CSS 动画序列中中间步骤的方面。
- `@viewport` — 描述小屏幕设备视口的各个方面。*（目前处于工作草案阶段）*
- `@counter-style`— 定义不属于预定义样式集的特定计数器样式。*（在候选推荐阶段，但在撰写本文时仅在 Gecko 中实现）*
- `@font-feature-values`(plus `@swash`, `@ornaments`, `@annotation`, `@stylistic`, `@styleset`and `@character-variant`) -`font-variant-alternates`为在 OpenType中以不同方式激活的功能定义通用名称。*（在候选推荐阶段，但在撰写本文时仅在 Gecko 中实现）*
- `@property` — 描述自定义属性和变量的方面。*（目前处于工作草案阶段）*
- `@color-profile` — 允许定义颜色配置文件以供[`color()`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color())函数使用。



## @import

> https://developer.mozilla.org/zh-CN/docs/Web/CSS/%40import#compat-desktop

**`@import `**CSS@规则，**用于从其他样式表导入样式规则**。**这些规则必须先于所有其他类型的规则**，`@charset` 规则除外; 因为它不是一个嵌套语句，@import不能在条件组的规则中使用。

因此，用户代理可以避免为不支持的媒体类型检索资源，作者可以指定依赖媒体的@import规则。这些条件导入在URI之后指定逗号分隔的媒体查询。**在没有任何媒体查询的情况下，导入是无条件的。指定所有的媒体具有相同的效果。**

**语法**

```css
@import url;
@import url list-of-media-queries;
```

*url*

是一个表示要引入资源位置 这个 URL 可以是绝对路径或者相对路径。 要注意的是这个 URL 不需要指明一个文件； 可以只指明包名，然后合适的文件会被自动选择 (e.g. **chrome://communicator/skin/**). [See here](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/Tutorial/The_Chrome_URL) 了解更多。

*list-of-media-queries*

是一个逗号分隔的 [媒体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) 条件列表，决定通过URL引入的 CSS 规则 在什么条件下应用。如果浏览器不支持列表中的任何一条媒体查询条件，就不会引入URL指明的CSS文件。

**示例**

```css
@import url("fineprint.css") print;
@import url("bluish.css") projection, tv;
@import 'custom.css';
@import url("chrome://communicator/skin/");
@import "common.css" screen, projection;
@import url('landscape.css') screen and (orientation:landscape);

```

