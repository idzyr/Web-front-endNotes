# 视频



```html
<video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    您的浏览器不支持 video 标签。
</video>
```

目前，<video> 元素支持三种视频格式：MP4、WebM、Ogg。

| 浏览器            | MP4                                                     | WebM | Ogg  |
| :---------------- | :------------------------------------------------------ | :--- | :--- |
| Internet Explorer | YES                                                     | NO   | NO   |
| Chrome            | YES                                                     | YES  | YES  |
| Firefox           | YES 从 Firefox 21 版本开始 Linux 系统从 Firefox 30 开始 | YES  | YES  |
| Safari            | YES                                                     | NO   | NO   |
| Opera             | YES 从 Opera 25 版本开始                                | YES  | YES  |

- MP4 = MPEG 4文件使用 H264 视频编解码器和AAC音频编解码器
- WebM = WebM 文件使用 VP8 视频编解码器和 Vorbis 音频编解码器
- Ogg = Ogg 文件使用 Theora 视频编解码器和 Vorbis音频编解码器

## 属性

- `poster=“url”`设置视频播放前的海报

HTML5 中的新属性。

| 属性                                                         | 值                 | 描述                                                         |
| :----------------------------------------------------------- | :----------------- | :----------------------------------------------------------- |
| [autoplay](https://www.runoob.com/tags/att-video-autoplay.html)**New** | autoplay           | 如果出现该属性，则视频在就绪后马上播放。                     |
| [controls](https://www.runoob.com/tags/att-video-controls.html)**New** | controls           | 如果出现该属性，则向用户显示控件，比如播放按钮。             |
| [height](https://www.runoob.com/tags/att-video-height.html)**New** | *pixels*           | 设置视频播放器的高度。                                       |
| [loop](https://www.runoob.com/tags/att-video-loop.html)**New** | loop               | 如果出现该属性，则当媒介文件完成播放后再次开始播放。         |
| [muted](https://www.runoob.com/tags/att-video-muted.html)**New** | muted              | 如果出现该属性，视频的音频输出为静音。                       |
| [poster](https://www.runoob.com/tags/att-video-poster.html)**New** | *URL*              | 规定视频正在下载时显示的图像，直到用户点击播放按钮。         |
| [preload](https://www.runoob.com/tags/att-video-preload.html)**New** | auto metadata none | 如果出现该属性，则视频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。 |
| [src](https://www.runoob.com/tags/att-video-src.html)**New** | *URL*              | 要播放的视频的 URL。                                         |
| [width](https://www.runoob.com/tags/att-video-width.html)**New** | *pixels*           | 设置视频播放器的宽度。                                       |

## 最好的 HTML 解决方法

以下实例中使用了 4 种不同的视频格式。HTML 5 `<video>` 元素会尝试播放以 mp4、ogg 或 webm 格式中的一种来播放视频。如果均失败，则回退到 `<embed>` 元素。

```html
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.webm" type="video/webm">
  <object data="movie.mp4" width="320" height="240">
    <embed src="movie.swf" width="320" height="240">
  </object>
</video>
```





## 视频的兼容

https://html5media.info/运用第三方库轻松兼容

