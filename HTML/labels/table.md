# 表格

```html
<table border="1">    
     <!-- 定义表格标题 -->
  <caption>表格标题</caption>
    <!-- 定义行 -->
  <tr>
      <!-- 定义表头 --->
    <th>表头1</th>
    <th>表头2</th>
  </tr>
  <tr>
      <!--  定义单元格及定义列 -->
    <td>单元格1</td>
    <td>单元格1</td>
  </tr>
  <tr>
    <td>单元格2</td>
    <td>单元格2</td>
  </tr>
</table>
```



- `<thead>`定义表格的页眉

- `<tbody>`定义表格的主体

- `<tfoot>`定义表格的页脚

- `<col>`定义表格的列属性



**预览；**

<table border="1">
  <caption>表格标题</caption>  
    <!-- 定义行 -->
  <tr>
      <!-- 定义表头 --->
    <th>表头1</th>
    <th>表头2</th>
  </tr>
  <tr>
      <!--  定义单元格 -->
    <td>单元格1</td>
    <td>单元格1</td>
  </tr>
  <tr>
    <td>单元格2</td>
    <td>单元格2</td>
  </tr>
</table>



**属性**

- `cellpadding=“大小”`单元格边距table标签内写
- `cellspacing=“大小”`单元格内的边距使用方法同上
- `bgcolor`表格背景颜色，background背景图片
-  `border` 表格边距
- `border-collapse` 折叠边框
- 单元格合并
  - `colspan`=“个数” 跨列
  - `rowspan` 跨行




> **注意；**
>
> 1. 不要给除**table，th，td**以外的表格元素加样式
> 2. table的标签特性就是`display：table`属性
> 3. 单元格默认平分table的宽度
> 4. th（表头）里面的内容默认加粗并且上下左右居中显示
> 5. td默认内容上下居中,左右居左显示
> 6. table大小决定了整个表格的宽度
> 7. table里面的单元格宽度都会转换为百分比
> 8. 表格里面的每一列必须有宽度
> 9. 表格同一竖列继承最大宽度
> 10. 表格同行继承最大高度
> 11. 内容撑开表格的高度
> 12. **单元格合并**；一定要把被合并的内容去除

