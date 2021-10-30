# 精灵图（sprite) 重点

##  为什么需要精灵技术

一个网页中往往会应用很多小的背景图像作为修饰，当网页中的图像过多时，服务器就会频繁地接受和发送请求，这将大大降低页面的加载速度。**为了有效地减少服务器接受和发送请求的次数，提高页面的加载速度。**

## 精灵技术讲解

CSS 精灵其实是将网页中的一些背景图像整合到一张大图中（精灵图），然而，各个网页元素通常只需要精灵图中不同位置的某个小图，要想精确定位到精灵图中的某个小图。

![img](sprite-images/jds.png)

这样，当用户访问该页面时，只需向服务发送一次请求，网页中的背景图像即可全部展示出来。

我们需要使用CSS的

- background-image、
- background-repeat
- background-position属性进行背景定位，
- 其中最关键的是使用background-position 属性精确地定位。

## 精灵技术使用的核心总结

首先我们知道，css精灵技术主要针对于背景图片，插入的图片img 是不需要这个技术的。

1. 精确测量，每个小背景图片的大小和 位置。
2. 给盒子指定小背景图片时， 背景定位基本都是 负值。

## 制作精灵图(了解)

CSS 精灵其实是将网页中的一些背景图像整合到一张大图中（精灵图），那我们要做的，就是把小图拼合成一张大图。

大部分情况下，精灵图都是网页美工做。

- 我们精灵图上放的都是小的装饰性质的背景图片。 插入图片不能往上放。
- 我们可以横向摆放也可以纵向摆放，但是每个图片之间留有适当的空隙
- 在我们精灵图的最低端，留一片空隙，方便我们以后添加其他精灵图。

结束语： 小公司，背景图片很少的情况，没有必要使用精灵技术，维护成本太高。 如果是背景图片比较多，可以建议使用精灵技术。

## 滑动门出现的背景

> 如同Android中的九妹图。



为了使各种特殊形状的背景能够自适应元素中文本内容的多少，出现了CSS滑动门技术。它从新的角度构建页面，使各种特殊形状的背景能够**自由拉伸滑动，**以适应元素内部的文本内容，可用性更强。 最常见于各种导航栏的滑动门。

核心技术就是利用CSS精灵（主要是背景位置）和 盒子padding撑开宽度, 以便能适应不同字数的导航栏。

一般的经典布局都是这样的：

```html
<li>
   <!-- 设置盒子左侧背景 （左门） -->
  <a href="#">
     <!-- 设置盒子右侧背景 （右门） -->
    <span>导航栏内容</span>
  </a>
</li>
```

css样式

```css
* {
      padding:0;
      margin:0;

    }
    body{
      background: url(images/wx.jpg) repeat-x;
    }
    .father {
      padding-top:20px;
    }
    li {
      padding-left: 16px;
      height: 33px;
      float: left;
      line-height: 33px;
      margin:0  10px;
      background: url(./images/to.png) no-repeat left ;
    }
    a {
      padding-right: 16px;
      height: 33px;
      display: inline-block;
			 /*因为我们是滑动门，左右推拉 跟文字内容多少有关系，此时需要用文字撑开盒子， 就要用到行内块*/
      color:#fff;
      background: url(./images/to.png) no-repeat right ;
      text-decoration: none;
    }
    li:hover,
     li:hover a {
      background-image:url(./images/ao.png);
    }
```

