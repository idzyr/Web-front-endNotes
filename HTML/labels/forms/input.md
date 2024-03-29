# 输入标签

| 属性                                                         | 值                                                           | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| [accept](https://www.runoob.com/tags/att-input-accept.html)  | audio/* video/* image/* *MIME_type*                          | 规定通过文件上传来提交的文件的类型。 (只针对type="file")     |
| [align](https://www.runoob.com/tags/att-input-align.html)    | left right top middle bottom                                 | HTML5已废弃，不赞成使用。规定图像输入的对齐方式。 (只针对type="image") |
| [alt](https://www.runoob.com/tags/att-input-alt.html)        | *text*                                                       | 定义图像输入的替代文本。 (只针对type="image")                |
| [autocomplete](https://www.runoob.com/tags/att-input-autocomplete.html)**New** | on off                                                       | autocomplete 属性规定 \<input> 元素输入字段是否应该启用自动完成功能。 |
| [autofocus](https://www.runoob.com/tags/att-input-autofocus.html)**New** | autofocus                                                    | 属性规定当页面加载时\<input> 元素应该自动获得焦点。          |
| [checked](https://www.runoob.com/tags/att-input-checked.html) | checked                                                      | checked 属性规定在页面加载时应该被预先选定的 \<input> 元素。 (只针对 type="checkbox" 或者 type="radio") |
| [disabled](https://www.runoob.com/tags/att-input-disabled.html) | disabled                                                     | disabled 属性规定应该禁用的 \<input> 元素。                  |
| [form](https://www.runoob.com/tags/att-input-form.html)**New** | *form_id*                                                    | form 属性规定 \<input> 元素所属的一个或多个表单。            |
| [formaction](https://www.runoob.com/tags/att-input-formaction.html)**New** | *URL*                                                        | 属性规定当表单提交时处理输入控件的文件的 URL。(只针对 type="submit" 和 type="image") |
| [formenctype](https://www.runoob.com/tags/att-input-formenctype.html)**New** | application/x-www-form-urlencoded multipart/form-data text/plain | 属性规定当表单数据提交到服务器时如何编码(只适合 type="submit" 和 type="image")。 |
| [formmethod](https://www.runoob.com/tags/att-input-formmethod.html)**New** | get post                                                     | 定义发送表单数据到 action URL 的 HTTP 方法。 (只适合 type="submit" 和 type="image") |
| [formnovalidate](https://www.runoob.com/tags/att-input-formnovalidate.html)**New** | formnovalidate                                               | formnovalidate 属性覆盖 \<form> 元素的 novalidate 属性。     |
| [formtarget](https://www.runoob.com/tags/att-input-formtarget.html)**New** | _blank _self _parent _top *framename*                        | 规定表示提交表单后在哪里显示接收到响应的名称或关键词。(只适合 type="submit" 和 type="image") |
| [height](https://www.runoob.com/tags/att-input-height.html)**New** | *pixels*                                                     | 规定 \<input>元素的高度。(只针对type="image")                |
| [list](https://www.runoob.com/tags/att-input-list.html)**New** | *datalist_id*                                                | 属性引用 \<datalist> 元素，其中包含 \<input> 元素的预定义选项。 |
| [max](https://www.runoob.com/tags/att-input-max.html)**New** | *number date*                                                | 属性规定 \<input> 元素的最大值。                             |
| [maxlength](https://www.runoob.com/tags/att-input-maxlength.html) | *number*                                                     | 属性规定 \<input> 元素中允许的最大字符数。                   |
| [min](https://www.runoob.com/tags/att-input-min.html)**New** | *number date*                                                | 属性规定 \<input>元素的最小值。                              |
| [multiple](https://www.runoob.com/tags/att-input-multiple.html)**New** | multiple                                                     | 属性规定允许用户输入到 \<input> 元素的多个值。               |
| [name](https://www.runoob.com/tags/att-input-name.html)      | *text*                                                       | name 属性规定 \<input> 元素的名称。                          |
| [pattern](https://www.runoob.com/tags/att-input-pattern.html)**New** | *regexp*                                                     | pattern 属性规定用于验证 \<input> 元素的值的正则表达式。     |
| [placeholder](https://www.runoob.com/tags/att-input-placeholder.html)**New** | *text*                                                       | placeholder 属性规定可描述输入 \<input> 字段预期值的简短的提示信息 。 |
| [readonly](https://www.runoob.com/tags/att-input-readonly.html) | readonly                                                     | readonly 属性规定输入字段是只读的。                          |
| [required](https://www.runoob.com/tags/att-input-required.html)**New** | required                                                     | 属性规定必需在提交表单之前填写输入字段。                     |
| [size](https://www.runoob.com/tags/att-input-size.html)      | *number*                                                     | size 属性规定以字符数计的 \<input> 元素的可见宽度。          |
| [src](https://www.runoob.com/tags/att-input-src.html)        | *URL*                                                        | src 属性规定显示为提交按钮的图像的 URL。 (只针对 type="image") |
| [step](https://www.runoob.com/tags/att-input-step.html)**New** | *number*                                                     | step 属性规定 \<input> 元素的合法数字间隔。                  |
| [type](https://www.runoob.com/tags/att-input-type.html)      | button checkbox color date datetime datetime-local email file hidden image month number password radio range reset search submit tel text time url week | type 属性规定要显示的 \<input> 元素的类型。                  |
| [value](https://www.runoob.com/tags/att-input-value.html)    | *text*                                                       | 指定 \<input> 元素 value 的值。                              |
| [width](https://www.runoob.com/tags/att-input-width.html)**New** | *pixels*                                                     | width 属性规定 \<input> 元素的宽度。 (只针对type="image")    |

- `autocomplete="off"` 是否根据以前提交输入的内容进行自动匹配填充。on=开（默认）/off=关 **需要指定name属性**
- `required` 属性规定必需在提交表单之前填写输入字段。也就是表单内容不可以为空
- `autofocus` 属性规定当页面加载时\<input> 元素应该自动获得焦点。
- `multiple` 允许用户输入到 \<input> 元素的多个值。如input type="file" 可以支持选择多个文件



## type 属性

**New**为HTML5新镇

| 值                    | 描述                                                         |
| :-------------------- | :----------------------------------------------------------- |
| button                | 定义可点击的按钮（通常与 JavaScript 一起使用来启动脚本）。   |
| checkbox              | 定义复选框。                                                 |
| color**New**          | 定义拾色器。                                                 |
| date**New**           | 定义 date 控件（包括年、月、日，不包括时间）。               |
| datetime**New**       | 定义 date 和 time 控件（包括年、月、日、时、分、秒、几分之一秒，基于 UTC 时区）。 |
| datetime-local**New** | 定义 date 和 time 控件（包括年、月、日、时、分、秒、几分之一秒，不带时区）。 |
| email**New**          | 定义用于 e-mail 地址的字段。                                 |
| file                  | 定义文件选择字段和 "浏览..." 按钮，供文件上传。              |
| hidden                | 定义隐藏输入字段。                                           |
| image                 | 定义图像作为提交按钮。                                       |
| month**New**          | 定义 month 和 year 控件（不带时区）。                        |
| number**New**         | 定义用于输入数字的字段。                                     |
| password              | 定义密码字段（字段中的字符会被遮蔽）。                       |
| radio                 | 定义单选按钮。                                               |
| range**New**          | 定义用于精确值不重要的输入数字的控件（比如 slider 控件）。   |
| reset                 | 定义重置按钮（重置所有的表单值为默认值）。                   |
| search**New**         | 定义用于输入搜索字符串的文本字段。                           |
| submit                | 定义提交按钮。                                               |
| tel**New**            | 定义用于输入电话号码的字段。                                 |
| text                  | 默认。定义一个单行的文本字段（默认宽度为 20 个字符）。       |
| time**New**           | 定义用于输入时间的控件（不带时区）。                         |
| url**New**            | 定义用于输入 URL 的字段。                                    |
| week**New**           | 定义 week 和 year 控件（不带时区）。                         |
