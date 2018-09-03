---
typora-copy-images-to: p
---

# README

## ★资料

**➹：**[前端每日实战：1# 视频演示如何用纯 CSS 创作一个按钮文字滑动特效 - 前端每日实战 - SegmentFault 思否](https://segmentfault.com/a/1190000014534572)

## ★小结

## ★Q&A

### ①BUTTON的空隙来源？

BUTTON的每个字母都是用span元素打包的，而span元素之间存在一个换行符等，总之看不见的空白都被压缩成一个空格了**✎：**

![1535993687445](p/1535993687445.png)

那么如何消除空隙呢？——让各个span元素紧挨着即可

可这就不利于阅读了啊！

所以可以使用jQuery来搞这事儿，**✎：**

1. 引入jQuery（我直接使用最新的）

2. demo，**✎：**

   ```js
   $('.removeTextNodes').contents().filter(function() {
       return this.nodeType === 3;
       }).remove();
   ```


理解一下这个demo？

### ②常用的nodeType？

**➹：**[Node.nodeType - Web API 接口 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/nodeType)

- `Node.ELEMENT_NODE`： 1

  > 一个 元素 节点，例如 `<p>` 和 `<div>`。

- `Node.TEXT_NODE`： 3

  > `Element` 或者 `Attr` 中实际的  **文字**

### ③jQuery——contents()、not()、wrap()

contents()，**✎：**

**➹：**[contents() | jQuery API 3.2 中文文档 | jQuery API 在线手册](http://jquery.cuishifeng.cn/contents.html)

> 查找匹配元素内部所有的子节点（包括文本节点）。如果元素是一个iframe，则查找文档内容

筛选类！

1. 查找所有文本节点并加粗
2. 往一个空框架中加些内容

not()，**✎：**

**➹：**[not(expr|ele|fn) | jQuery API 3.2 中文文档 | jQuery API 在线手册](http://jquery.cuishifeng.cn/not.html)

- 概述

  > 从匹配元素的集合中删除与指定表达式匹配的元素

- Type

  筛选类

- 参数

  1. expr：一个选择器字符串——String
  2. element：一个DOM元素——DOMElement
  3. function(index)：一个用来检查集合中每个元素的函数。this是当前的元素。——Function

- 返回值

  jQuery对象

- case

  1. 从p元素中删除带有 select 的ID的元素

wrap(html|element|fn)，**✎：**

**➹：**[wrap(html|ele|fn) | jQuery API 3.2 中文文档 | jQuery API 在线手册](http://jquery.cuishifeng.cn/wrap.html)

- 概述

  > 把所有匹配的元素用其他元素的结构化标记包裹起来

- Type

  文档处理类

- 参数

  | key     | Type     | value                                              |
  | ------- | -------- | -------------------------------------------------- |
  | html    | String   | HTML标记代码字符串，用于动态生成元素并包裹目标元素 |
  | element | Element  | 用于包装目标元素的DOM元素                          |
  | fn      | Function | 生成包裹结构的一个函数                             |

- 返回值

  jQuery对象

- case

  1. 把所有的段落用一个新创建的div包裹起来



