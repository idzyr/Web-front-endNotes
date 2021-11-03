# 文本输入框

- placeholder 设置提示信息。

```html
<input type="text" placeholder="提示文件">
```

设置placeholder颜色

```css
input::-webkit-input-placeholder { /* WebKit, Blink, Edge */

    color : red;

}

:-moz-placeholder { /* Mozilla Firefox 4 to 18 */

   color : red;

}

::-moz-placeholder { /* Mozilla Firefox 19+ */

   color : red;

}

input:-ms-input-placeholder { /* Internet Explorer 10-11 */

   color : red;

}

input::-ms-input-placeholder { /* Microsoft Edge */

   color : red;

}
```



**预览；**

<input type="text" placeholder="提示文件">

