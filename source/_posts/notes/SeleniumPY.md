---
title: Selenium Python 学习笔记
date: 2019-04-04 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

## I. 安装`Selenium`

用我们的`CONDA`, 或者`PIP`也行, 在终端控制台输入:

```sh
> conda install selenium
```

即可, 没什么特别的。

## II. 初试(**有巨坑警告**)

按照官网的说法, 你下完`Selenium`就可以直接开始这样控制浏览器了:

```py
>>> from selenium import webdriver
>>> browser = webdriver.Firefox()
>>> browser.get("https://www.bilibili.com/")
```

**知道吗, 这么一搞你就离报错不远了!!!**

然后解释器就会提示你要把`GeckoDriver`什么的给放到环境变量(一般而且这里也就是`PATH`)里面,

而有些同学可能连`GeckoDriver`是什么都不知道,

### 这里先普及一下`Webdriver`的概念:

很简单, 如果你要~~假冒~~**模拟**一个浏览器去网上浪的话, 必须有一个驱动程序, 我们称之为`Webdriver`, 而`Firefox`的叫做`GeckoDriver`, `Chrome`的叫做`ChromeDriver`, `Opera`的叫做等等等等......

所以**你需要先下载一个`Webdriver`**, 而模拟这个浏览器不仅仅需要`Webdriver`, 还需要这个浏览器本身, 所以这个东西还是得看你计算机上有哪个浏览器(我们一如既往地推荐使用`Google`的`Chrome`), 你再去找, 下完之后, 需要解压, 然后把它移动到`Anaconda3\Scripts`文件夹下,

搞完上面这一套神乎其技的操作, 你就可以(正式)开始用`Selenium`~~搞事情~~**做测试**了, 撒花!!!

## III. 常见浏览器对应驱动下载地址

| Browser | Webdriver Downloading URL |
| - | - |
| `Chrome` | ~~https://sites.google.com/a/chromium.org/chromedriver/downloads/~~ |
| `Opera` | https://github.com/operasoftware/operachromiumdriver/releases/ |
| `Firefox` | https://github.com/mozilla/geckodriver/releases/ |
| `Edge` | https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/ |
| `Safari` | https://webkit.org/blog/6900/webdriver-support-in-safari-10/ |

你们可以看到, `Chrome`的那一行被划掉了, 毕竟 google.com 被墙掉了除非你科学上网否则做梦都不一定能上去,

所以我们找到了两个用于替代的地址, 便于你不用办理签证去美国也可以用`Selenium`来驱动`Chrome`。

## IV. `ChromeDriver`下载地址

* `Google`官方API: https://chromedriver.storage.googleapis.com/index.html
* 淘宝镜像: https://npm.taobao.org/mirrors/chromedriver/

## V. `ChromeDriver`对应浏览器版本一览

| Webdriver Version | Chrome Version |
| ----- | ------ |
| v2.45 | v70-72 |
| v2.44 | v69-71 |
| v2.43 | v69-71 |
| v2.42 | v68-70 |
| v2.41 | v67-69 |
| v2.40 | v66-68 |
| v2.39 | v66-68 |
| v2.38 | v65-67 |
| v2.37 | v64-66 |
| v2.36 | v63-65 |
| v2.35 | v62-64 |
| v2.34 | v61-63 |
| v2.33 | v60-62 |
| v2.32 | v59-61 |
| v2.31 | v58-60 |
| v2.30 | v58-60 |
| v2.29 | v56-58 |
| v2.28 | v55-57 |
| v2.27 | v54-56 |
| v2.26 | v53-55 |
| v2.25 | v53-55 |
| v2.24 | v52-54 |
| v2.23 | v51-53 |
| v2.22 | v49-52 |
| v2.21 | v46-50 |
| v2.20 | v43-48 |
| v2.19 | v43-47 |
| v2.18 | v43-46 |
| v2.17 | v42-43 |
| v2.13 | v42-45 |
| v2.15 | v40-43 |
| v2.14 | v39-42 |
| v2.13 | v38-41 |
| v2.12 | v36-40 |
| v2.11 | v36-40 |
| v2.10 | v33-36 |
| v2.9  | v31-34 |
| v2.8  | v30-33 |
| v2.7  | v30-33 |
| v2.6  | v29-32 |
| v2.5  | v29-32 |
| v2.4  | v29-32 |
