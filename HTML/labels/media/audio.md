# 音频

\<audio> 标签定义声音，比如音乐或其他音频流。

目前，\<audio> 元素支持的3种文件格式：MP3、Wav、Ogg。

| 浏览器            | MP3  | Wav  | Ogg  |
| :---------------- | :--- | :--- | :--- |
| Internet Explorer | YES  | NO   | NO   |
| Chrome            | YES  | YES  | YES  |
| Firefox           | YES  | YES  | YES  |
| Safari            | YES  | YES  | NO   |
| Opera             | YES  | YES  | YES  |

## 最好的 HTML 解决方法

下面的例子使用了两个不同的音频格式。HTML5 `<audio>` 元素会尝试以 mp3 或 ogg 来播放音频。如果失败，代码将回退尝试 `<embed>` 元素。

**实例**

```html
<audio controls height="100" width="100">
  <source src="horse.mp3" type="audio/mpeg">
  <source src="horse.ogg" type="audio/ogg">
  <embed height="50" width="100" src="horse.mp3">
</audio>
```





## 属性

HTML5 中的新属性。

| 属性                                                         | 值                 | 描述                                                        |
| :----------------------------------------------------------- | :----------------- | :---------------------------------------------------------- |
| [autoplay](https://www.runoob.com/tags/att-audio-autoplay.html)**New** | autoplay           | 如果出现该属性，则音频在就绪后马上播放。                    |
| [controls](https://www.runoob.com/tags/att-audio-controls.html)**New** | controls           | 如果出现该属性，则向用户显示音频控件（比如播放/暂停按钮）。 |
| [loop](https://www.runoob.com/tags/att-audio-loop.html)**New** | loop               | 如果出现该属性，则每当音频结束时重新开始播放。              |
| [muted](https://www.runoob.com/tags/att-audio-muted.html)**New** | muted              | 如果出现该属性，则音频输出为静音。                          |
| [preload](https://www.runoob.com/tags/att-audio-preload.html)**New** | auto metadata none | 规定当网页加载时，音频是否默认被加载以及如何被加载。        |
| [src](https://www.runoob.com/tags/att-audio-src.html)**New** | *URL*              | 规定音频文件的 URL。                                        |



