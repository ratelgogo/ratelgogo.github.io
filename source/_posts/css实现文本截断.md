---
title: css实现文本截断
date: 2016-12-14 17:09:35
tags:
  - css
---

`text-overflow: clip|ellipsis|string`

值 | 描述
---|---
clip | 修剪文本直接截断
ellipsis | 用省略号代替截断的字符串
string | 使用给出的字符串来代替截断的字符串([兼容性差,只有火狐支持]("https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow"))

here we go

{% jsfiddle b08zsgqd/2 %}

> * clip 会比 ellipsis 显示更多的字符
> * `display`需要是`block`
> * 配合`white-space: nowrap` 强制不换行来使用
