# 下拉列表

- selected 默认被选中

```html
<select>
  <option selected>下拉列表项 </option>
</select>
```



**预览；**

<select>
  <option selected>选项一 </option>
  <option>选项二</option>
</select>

## 下拉列表输入智能匹配

dataList——数据列表

```html
<datalist id="">

 <option value=""></option>

   ………

</datalist>

/j
<input list="browsers">
<datalist id="browsers">
  <option value="Internet Explorer">
  <option value="Firefox">
  <option value="Chrome">
  <option value="Opera">
  <option value="Safari">
</datalist>
```

使用方法要和input通过id来绑定实现下拉列表输入智能匹配