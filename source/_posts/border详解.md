---
title: border详解
date: 2016-11-24 20:39:52
tags:
  - border
  - css
---
### border-width
> `border-width` 因为边框的语义决定了宽度不能用百分比表示，类似`box-shadow`

#### 关键字
* `thin` : `1px`
* `medium`: `2px`
* `thick`: `5px`
<!--more-->

### border-style
常用的有`solid`(实线)， `dashed`(虚线)， `double`(双线，3px才有效果,双线宽度永远相等，中间间隔+-1), `dotted`(点线比虚线更密)
> 由于border的兼容性比较好，经常用作一些图形的替代方案

三条杠
```css
  {
    width: 120px;
    height: 20px;
    border-top: 60px double;
    border-bottom: 20px solid;
  }
```

### border-color
> 当没有制定border-color时会使用color作为边框颜色

### 应用

三角形：利用容器宽高为0时每个边框由三角形组成一个正方形，两边透明就变成了一个规则的三角形，可以有各种组合
```css
.triangle {
  width: 0px;
  height: 0px;
  border: 100px solid;
  border-color: transparent red red transparent;
}
```
梯形：隐藏另外三边，给容器增加宽度就能得到梯形

```css
.trapezoid {
  width: 50px;
  border: 4px solid;
  border-color: transparent transparent red;
}
```
布局的应用： 等高布局
```css
.box {
  border-left: 300px solid #c3c3c3;
}

.left {
  width: 300px;
  margin-left: -300px;
  float: left;
}

```
