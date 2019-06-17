---
typora-copy-images-to: p
---

# 如何用纯 CSS 创作一个容器厚条纹边框特效

## ★资源

**➹：**[前端每日实战：3# 视频演示如何用纯 CSS 创作一个容器厚条纹边框特效 - 前端每日实战 - SegmentFault 思否](https://segmentfault.com/a/1190000014576519)

**➹：** <https://scrimba.com/c/cPvn6tE>

## ★源码

**➹：**<https://github.com/comehope/front-end-daily-challenges/tree/master/003-diagonal-stripe-border-effects>

## ★预览效果



## ★知识点



## ★总结



## ★Q&A

### ①linear-gradient？

关于渐变，它是**一种应用于平面的视觉效果**，可以从**一种颜色逐渐地转变成另外一种颜色**，故可以创建类似于彩虹的效果渐变可以应用在**任何可以使用图片的地方**。

举例来说，你可以指定这么一个渐变：

顶部的颜色是红色，中间的是蓝色，底部为黄色来作为div的背景色。

那么我们该如何实现渐变呢？——很简单，CSS给了我们以下这几种方式实现（它们都是渐变函数，是`background`这位魔法师可以使用的其中一门魔法，而使用这类魔法之后，显而易见的就是，我们**不用再写背景图片的URL**，总之，**渐变函数可以用来代替图片URL**）：

1. `background: linear-gradient(#f69d3c, #3f87a6);`：线性渐变

   ![1560785873997](p/1560785873997.png)

2. `background: radial-gradient(#f69d3c, #3f87a6);`：径向渐变

   ![1560785914043](p/1560785914043.png)

3. `background: repeating-linear-gradient(#f69d3c, #3f87a6 50px);`：重复的线性渐变

   ![1560785944633](p/1560785944633.png)

4. `background: repeating-radial-gradient(#f69d3c, #3f87a6 50px);`：重复的径向渐变

   ![1560785961160](p/1560785961160.png)

   这看起来有锯齿呀！一点也不圆润

5. `background: conic-gradient(#f69d3c, #3f87a6);`：圆锥形渐变

   ![1560785978667](p/1560785978667.png)

   这个真是奇葩……

需要注意的是：

1. **`<gradient>`** （[CSS数据类型](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types)的一种）是 `<image>` 的一种特殊类型，简单来说，就是它的子类型，表示由**两种或多种颜色**之间的渐进式的过渡组成，总之，就是你使用了渐变函数，那么你就**不能只写一个颜色参数值，毕竟你不能抢了背景色的活儿啊**！
2. 具体尺寸将与其（CSS渐变）**所应用的元素的尺寸相匹配**，总之CSS渐变它没有没有[内在尺寸](https://developer.mozilla.org/en-US/docs/CSS/image#no_intrinsic)，就像个不失真的背景图片一样。

有这样一份代码：

```html
<div class="box"></div>
```

```css
.box {
    width: 300px;
    height: 300px;
    background: linear-gradient(
        -45deg,
        white 0%,
        white 25%,
        hotpink 25%,
        hotpink 50%,
        white 50%,
        white 75%,
        hotpink 75%,
        hotpink 100%);
    background-size: 10%;
}
```

它的效果是这样的：

![1560787016913](p/1560787016913.png)

而在chrome里边的效果是这样的：

![1560787062773](p/1560787062773.png)

真是奇葩的渲染啊！完全弄不明白chrome画的是什么玩意儿……

**➹：**[`<gradient>` - CSS: Cascading Style Sheets - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)

**➹：** [CSS gradient渐变之webkit核心浏览器下的使用 « 张鑫旭-鑫空间-鑫生活](https://www.zhangxinxu.com/wordpress/2010/04/css-gradient%E6%B8%90%E5%8F%98%E4%B9%8Bwebkit%E6%A0%B8%E5%BF%83%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%8B%E7%9A%84%E4%BD%BF%E7%94%A8/)

### ②background-size的百分比？

`background-size: 30%;`

这里只有一个值，表示图片的宽度为所应用元素的宽度的30%，而高度则是 `auto`

**➹：**[background-size - CSS: Cascading Style Sheets - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)

