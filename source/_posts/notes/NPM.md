---
title: NPM学习笔记
date: 2019-03-21 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

## I. 换源

如果你只想使用一次新的`NPM`源的话可以进行一次性换源, 在每次用`NPM`下东西的时候在最后加上一句`--registry=https://registry.npm.taobao.org`即可, 但如若要永久换源的话可以采用以下手段(以淘宝的`NPM`源( https://registry.npm.taobao.org )为例):

1. 在终端控制台中输入:

```sh
> npm config set registry https://registry.npm.taobao.org
```

其中 https://registry.npm.taobao.org 为`NPM`源的url, 你也可以改为自己喜欢的`NPM`源, 虽然国内最大的`NPM`源也就是它了。

2. 进入`nodejs\node_modules\npm\npmrc`文件添加下面一行代码:

```
registry=https://registry.npm.taobao.org
```

3. 体验阿里官方手工制作的淘宝`NPM`, 也就是传说之中的`CNPM`

在终端控制台中输入:

```sh
> npm install -g cnpm --registry=https://registry.npm.taobao.org
```

然后以后用`NPM`下什么东西的时候就把`npm`改成`cnpm`好了

## II. 删源

到`nodejs\node_modules\npm\npmrc`文件文件中把`registry`一行删去即可。

## III. 审查所有`NPM`源

在终端控制台中输入:

```sh
> npm config get registry
```

即可。
