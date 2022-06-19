# 序列帧动画

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [@keyframes](https://www.runoob.com/cssref/css3-pr-animation-keyframes.html) | 定义一个动画,@keyframes定义的动画名称用来被animation-name所使用。 |
| [animation](https://www.runoob.com/cssref/css3-pr-animation.html) | 复合属性。检索或设置对象所应用的动画特效。                   |

## @keyframes 【定义关键帧动画】

> https://www.runoob.com/cssref/css3-pr-animation-keyframes.html

```css
@keyframes mymove
{
from {top:0px;}
to {top:200px;}
}

@keyframes my_anin {
            0% {
                height: 300px;
                background-color: red;
            }

            50% {
                background-color: burlywood;
            }

            to {
                height: 400px;
            }

        }

@-webkit-keyframes mymove /* Safari and Chrome */
{
from {top:0px;}
to {top:200px;}
}
```

**注意；**

动画会覆盖元素，以有的相同属性的属性值。

**语法；**

```
@keyframes animationname {keyframes-selector {css-styles;}}
```

| 值                   | 说明                                                         |
| -------------------- | ------------------------------------------------------------ |
| *animationname*      | 必需的。定义动画的名称。                                     |
| *keyframes-selector* | 必需的。动画持续时间的百分比。合法值：0-100% from (等价于0%) to (等价于100%）注**意：** 您可以用一个动画keyframes-selectors。 |
| *css-styles*         | 必需的。一个或多个合法的CSS样式属性                          |



## animation 【使用动画】

> animation复合属性

| 属性/值                                                      | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| *[animation-name](https://www.runoob.com/cssref/css3-pr-animation-name.html)* | 指定要绑定到选择器的关键帧的名称                             |
| *[animation-duration](https://www.runoob.com/cssref/css3-pr-animation-duration.html)* | 动画指定需要多少秒或毫秒完成                                 |
| *[animation-timing-function](https://www.runoob.com/cssref/css3-pr-animation-timing-function.html)* | 设置动画将如何完成一个周期                                   |
| *[animation-delay](https://www.runoob.com/cssref/css3-pr-animation-delay.html)* | 设置动画在启动前的延迟间隔。                                 |
| *[animation-iteration-count](https://www.runoob.com/cssref/css3-pr-animation-iteration-count.html)* | 定义动画的播放次数。                                         |
| *[animation-direction](https://www.runoob.com/cssref/css3-pr-animation-direction.html)* | 指定是否应该轮流反向播放动画。                               |
| [animation-fill-mode](https://www.runoob.com/cssref/css3-pr-animation-fill-mode.html) | 规定当动画不播放时（当动画完成时，或当动画有一个延迟未开始播放时），要应用到元素的样式。 |
| *[animation-play-state](https://www.runoob.com/cssref/css3-pr-animation-play-state.html)* | 指定动画是否正在运行或已暂停。                               |
| initial                                                      | 设置属性为其默认值。 [阅读关于 *initial*的介绍。](https://www.runoob.com/cssref/css-initial.html) |
| inherit                                                      | 从父元素继承属性。 [阅读关于 *initinherital*的介绍。](https://www.runoob.com/cssref/css-inherit.html) |

```css
div
{
    animation:mymove 5s infinite; /* 使用动画名为mymove的动画，持续时间5秒，重复次数为一直重复 */
    -webkit-animation:mymove 5s infinite; /* Safari 和 Chrome */
}
```

- animation-name：动画序列名——绑定动画序列

- animation-duration：秒或毫秒——指定动画多长时间完成

- animation-timing-function——规定动画完成一个周期的曲线

  ![1498445454760](keyframes-images/1498445454760.png)

  | 值                    | 说明                                                         |
  | --------------------- | ------------------------------------------------------------ |
  | linear                | 动画从头到尾的速度是相同的。                                 |
  | ease  **默认**        | 动画以低速开始，然后加快，在结束前变慢                       |
  | ease-in               | 动画以低速开始。                                             |
  | ease-out              | 动画以低速结束。                                             |
  | ease-in-out           | 动画以低速开始和结束。                                       |
  | steps(int,start\|end) | 指定了时间函数中的间隔数量（步长）。有两个参数，第一个参数指定函数的间隔数，该参数是一个正整数（大于 0）<br/> start：表示直接开始。<br/> end：默认值，表示戛然而止 可以实现png序列背景动画播放 |
  | cubic-bezier(n,n,n,n) | 在 cubic-bezier 函数中自己贝塞尔曲线的值。可能的值是从 0 到 1 的数值。 |

- animation-delay——设置一个动画延迟多少秒或毫秒开始

- animation-iteration-count——动画播放次数数字或`infinite`循环

- animation-direction——设置动画是否反向播放，

  | 值                  | 说明                                                         |
  | ------------------- | ------------------------------------------------------------ |
  | normal   **默认值** | 动画按正常播放                                               |
  | reverse             | 动画反向播放。                                               |
  | alternate           | 动画的播放次数在奇数次（1、3、5...）正向播放，在偶数次（2、4、6...）反向播放。 让动画反向播放 |
  | alternate-reverse   | 动画的播放次数在奇数次（1、3、5...）反向播放，在偶数次（2、4、6...）正向播放。 |

- animation-play-state——指定动画运行还是暂停

  | 值      | 说明           |
  | ------- | -------------- |
  | paused  | 暂停动画       |
  | running | 正在运行的动画 |

- animation-fill-mode——规定动画完成后的状态

  | 值              | 说明                                                         |
  | --------------- | ------------------------------------------------------------ |
  | none **默认值** | 使动画不会对动画等待和动画完成的元素样式产生改变             |
  | backwards       | 如果设置为这个值，那么在动画等待的那段时间内，元素的样式将设置为动画第一帧的样式； |
  | forwards        | 如果设置为这个值，那么在动画结束后，元素的样式将设置为动画的最后一帧的样式； |
  | both            | 相当于同时配置了backwards和forwards，意味着在动画等待和动画结束状态，元素将分别应用动画第一帧和最后一帧的样式。 |

**动画简写常用顺序；**

animation：动画名称 动画时间 运动曲线  何时开始  播放次数  是否反方向  动画等待或者结束的状态;

```css
animation: myfirst 5s linear 2s infinite alternate;
```



**总结；**

- 盒子动画结束后，停在结束位置：  animation-fill-mode  ：   forwards 
- 想要动画走回来 ，而不是直接跳回来：animation-direction   ：  alternate  
- 暂停动画：animation-play-state:   puased;   窗体给弄乱了，怎么办

