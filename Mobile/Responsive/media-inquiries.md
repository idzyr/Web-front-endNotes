# 媒体查询

## 方式一

link标签

[media](http://www.w3school.com.cn/tags/att_link_media.asp)判断条件加载css样式

**语法**

```html
<link 再引用css样式前加判断条件 media=“规定显示设备 and （具体限制如最小宽度或高度）”>
```

## 方法二

 css文件样式内

[@media](http://www.runoob.com/cssref/css3-pr-mediaquery.html)

 **语法**

```css
@media 设备 （判断条件可以是最小屏幕大小等）{

     代码块

}
```

**注意；**

   判断条件可是多个

（条件1）and【并且的意思】（条件2）or（条件3）
