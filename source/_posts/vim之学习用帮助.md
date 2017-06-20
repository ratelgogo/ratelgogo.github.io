---
title: vim之学习用帮助
date: 2017-06-20 15:09:30
categories: code
tags:
    - vim
    - help
---

## 开始使用

* 在命令模式下输入`:help`开始使用帮助
* 输入`:h pattern`查看pattern的使用帮助

### 链接
* <kbd>Ctrl + ]</kbd> 进行超链接跳转
* <kbd>Ctrl + o</kbd> 跳转到较旧的光标的位置
* <kbd>Ctrl + T</kbd> 跳转到上一个链接处

### 上下文

每个帮助主题都有上下文

|前缀|例子|上下文|
|:---:|:---:|:---:|
|`:`|`:h :r`|命令模式下以冒号开始的命令|
|无|`:h r`|normal mode|
|`v_`|`:h v_r`|visual mode|
|`i_`|`:h i_CTRL-W`|insert mode|
|`c_`|`:h c_CTRL-R`|ex command line|
|`/`|`:h /\r`|正则搜索帮助|
|`'`|`:h 'ro'`|选项，这里表示以readonly的方式打开|
|`-`|`:h -r`|参数|

如果你知道 <kbd>ctrl+r</kbd> ，只要在命令行中输入`:h ctrl-r`,然后再按<kbd>ctrl+d</kbd>,vim 会列出所有不同上下文的关键字
