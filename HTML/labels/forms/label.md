# label

```html
<form action="demo_form.php">
  <label for="male">Male</label>
  <input type="radio" name="sex" id="male" value="male"><br>
  <label for="female">Female</label>
  <input type="radio" name="sex" id="female" value="female"><br><br>
  <input type="submit" value="提交">
</form>
```

label 元素不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果您在 label 元素内点击文本，就会触发此控件。就是说，**当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上**



| 属性                                                         | 值           | 描述                                  |
| :----------------------------------------------------------- | :----------- | :------------------------------------ |
| [for](https://www.runoob.com/tags/att-label-for.html)        | *element_id* | 规定 label 与哪个表单元素绑定。       |
| [form](https://www.runoob.com/tags/att-label-form.html)**New** | *form_id*    | 规定 label 字段所属的一个或多个表单。 |

-  for 属性应当与相关元素的 id 属性相同。

