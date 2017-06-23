---
title: vim插件之surround.vim
date: 2017-06-21 17:08:27
categories: code
tags:
 - vim
 - surround
---

# SURROUND.VIM
[surround.vim](https://github.com/tpope/vim-surround) 可以快速的选择修改在包围里面的字符串，例如冒号，引号，大括号等

### 主要命令
+ `cs` 修改
+ `ds` 删除
+ `ys` 添加

### 常用例子
废话不多说，上代码:
假设有一段字符: `"hello vim!"`

输入`cs"'`
变成`'hello vim!'`

`cs'<q>`
=> `<q>hello vim!</q>`

`cst"`(当包围是多个字符时)
=> `"hello vim!"`

`ds"`去除"
=> `hello vim!`

`ysiw[`iw是一个单词，这里可以使用任何选择
=> `[ hello ] vim!`

在选择模式下输入S+你需要包围的字符串

### 补充
+ [和{ 是带空格的，]和}不带空格
+ 如果你需要使用到`.`命令来重复上面的命令，则需要再添加一个插件[vim-repeat](https://github.com/tpope/vim-repeat)
