# 布局

## 布局流程

为了提高网页制作的效率，布局时通常有以下的布局流程，具体如下：

1、必须确定页面的版心（可视区）， 我们测量可得知。

2、分析页面中的行模块，以及每个行模块中的列模块。其实页面布局，就是一行行罗列而成

3、制作HTML结构。我们还是遵循，先有结构，后有样式的原则。结构永远最重要。

4、然后开始运用盒子模型的原理，通过DIV+CSS布局来控制网页的各个模块。



## 页面的版心

页面可视区主要展示给用户观看的内容，通常是**居中显示**网页被缩放依然如此。有**单独的盒子承载**。包含版心内容的盒子往往都会有以下class属性。

```css
.w {
    width: 1200px;
    margin: auto;
}
```

![image-20211018231158607](layout-images/image-20211018231158607.png)

## 多个a标签排列

为了避免因大量链接连续出现导致的网站被搜索引擎降权。

通常是将a放到`li` 无需列表中列表外面套盒子，如，常见导航或页脚中的链接

导航

```html
<nav>
        <ul>
            <li><a href="">首页</a></li>
            <li><a href="">课程</a></li>
            <li><a href="">职业规划</a></li>
        </ul>
</nav>
```

页脚链接

```html
  <dl>
                <dt>合作伙伴</dt>
                <dd><a href="">合作机构</a></dd>
                <dd><a href="">合作导师</a></dd>
   </dl>
```



## banner 横幅

![image-20211018213113438](layout-images/image-20211018213113438.png)



- 在指定background属性时通常会设置底色，这个底色是以banner图主色来定义,图片定位也在中心。

  ```css
  background: #1c036c url("./images/banner2.jpg") no-repeat top center;
  ```

  

## 自定义列表 dl

自定义列表 常用用于制作页脚中的链接模块。

![image-20211019224632488](layout-images/image-20211019224632488.png)

```html
  <dl>
                <dt>合作伙伴</dt>
                <dd><a href="">合作机构</a></dd>
                <dd><a href="">合作导师</a></dd>
            </dl>
```



## 其它做法

- 想导航栏中的链接，文本个数不确定那么就不要指定其width，我们使用padding来撑开其宽度

- 如果设计图中没有给定每个列表项大小列表行与行之间的距离测量也就是行高，从上一个盒子的文本底部到当前盒子文本的底部。然后为盒子设置这个得到的高度，设置了高度列表之间的距离就自然拉开了最后设置文本垂直居中即可。

  <img src="layout-images/image-20211019155913954.png" alt="image-20211019155913954" style="zoom:50%;" />

- 版心盒子内的内容盒子是可以版心盒子宽的

  ![image-20211019214457897](layout-images/image-20211019214457897.png)

- 想这种效果可以使用span包含`|` 给span加margin让其撑开a标签

  ![image-20211102214212572](layout-images/image-20211102214212572.png)

  ```html
  <p class="mod_copyright_links">
                  <a href="#">关于我们</a>
                  <span>|</span>
                  <a href="#">联系我们</a>
                  <span>|</span>
                  <a href="#">联系客服</a>
  </p>
  ```

  ````css
  .mod_copyright_links span{
      margin: 0 10px;
  }
  ````

  

## 图片使用

- 商品图片等使用插入图片，也就是img标签

- 图标等使用background设置图片



## 侧边栏贴靠版心

![image-20211030161151013](layout-images/image-20211030161151013.png)



1. 先让侧边栏往左50%到达浏览器视图一般
2. 在往右移动版心宽度的一般，到达版心边缘
3. 在往左移动同侧边栏宽度的距离。margin-left
4. 其它方向移动也是如此类推

![image-20211030194540978](layout-images/image-20211030194540978.png)



## 网页布局总结

一个完整的网页，有标准流 、 浮动 、 定位 一起完成布局的。每个都有自己的专门用法。

### 标准流

可以让盒子上下排列 或者 左右排列的

### 浮动

可以让多个块级元素一行显示 或者 左右对齐盒子 浮动的盒子就是按照顺序左右排列

### 定位

定位最大的特点是有层叠的概念，就是可以让多个盒子 前后 叠压来显示。 但是每个盒子需要测量数值。



## 浮动盒子边框不重叠

![image-20211030222507485](layout-images/image-20211030222507485.png)

我们虽然可以去除一些边框来达到清除的目的，我们有更简单的方法给盒子设置负的margin值让其盖住重叠部分的边框

因为盒子使用了浮动会紧贴在一起所以不会出现原地踏步现象。

![image-20211030222829139](layout-images/image-20211030222829139.png)

如果要设置hover边框样式需要这样写

![image-20211031140510306](layout-images/image-20211031140510306.png)



## logo优化

- logo 里面 首先放一个 h1 标签 ，目的是为了提权，告诉搜索引擎，这个地方很重要
- h1里面在放一个连接，可以返回首页的， 给连接一个 大小 和 logo 的背景图片
- 连接 里面要放文字（网站名称），为了搜索引擎收录我们。 但是文字不要显示出来
  - 要用 text-indent 移到盒子外面 （text-indent: -9999px) 然后overflow:hidden 淘宝的做法
  - 直接给font-size: 0; 就看不到文字了， 京东的做法。
- 最后给 连接一个 title 这样鼠标放到logo 上， 就可以看到提示文字了

```html
<div class="logo">
        <h1>
            <a href="index.html" title="品优购">品优购</a>
        </h1>
    </div>
```

````css
.logo h1 a {
    display: block;
    width: 171px;
    height: 61px;
    font-size: 0;
    background-image: url("../img/logo.png");
}
````



## 提醒小红点

- count 统计部分 不要给宽度，因为可能买的件数比较多，让件数撑开就好了 给一个高度
- 一定注意左下角 不是圆角 其余三个是圆角

![image-20211101164225322](layout-images/image-20211101164225322.png)

````html
<i class="count">8</i>
````

````css
.count {
    position: absolute;
    top: -5px;
    /*文本增多时我们应该让其往左走所以要使用左偏移而非右偏移*/
    left: 105px;
    height: 14px;
    padding: 0 3px;
    line-height: 14px;
    text-align: center;
    color: #fefefe;
    background-color: #e60012;
    border-radius: 5px 5px 5px 0;
}
````



## 侧边导航

![image-20211101204924079](layout-images/image-20211101204924079.png)

划分，一个大盒子包含两个子盒子

![img](layout-images/9.png)

![image-20211101205137894](layout-images/image-20211101205137894.png)

