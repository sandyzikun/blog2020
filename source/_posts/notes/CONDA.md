---
title: CONDA学习笔记
date: 2019-03-07 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

## I. 搜索扩展模块

```sh
> anaconda search -t conda [PKG_NAME]
> conda search [PKG_NAME]
```

`PKG_NAME` 是你要找的扩展模块的名称, 如`keras`或者`tensorflow-gpu`等,

两者皆可, 前者的范围比后者要大一些, 信息更全面, 时间也更长。

## II. 换源

```sh
> conda config --add channels [CHANNEL_URL]
```

`CHANNEL_URL` 是你要加入的`CONDA`源的url, 删除所有的外部`CONDA`源可以使用:

```sh
> conda config --remove-key channels
```

附上常见的`CONDA`源(`源名称` 加粗的为 **官方源** , 斜体的为 *第三方源*):

| 源名称 | 清华镜像 | 科大镜像 |
|--------|---------|---------|
| **`FREE`** | https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/ | https://mirrors.ustc.edu.cn/anaconda/pkgs/free/ |
| **`MAIN`** | https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ | https://mirrors.ustc.edu.cn/anaconda/pkgs/main/ |
| *`conda-forge`* | https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/ | https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/ |
| *`msys2`* | https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/ | https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/ |
| *`bioconda`* | https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/ | https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/ |
| *`menpo`* | https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/ | https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/ |

## III. 查看所有已下载扩展模块

```sh
> conda list
```

## IV. 在下载新扩展模块的时候查看其所在的源

```sh
> conda config --set show_channel_urls yes
```

## V. 直接安装`.whl`文件

`.whl`是`Python`扩展模块的安装文件, 你们下载的一切扩展模块都是由一个又一个`.whl`解压编译而来的, 所以有的时候我们直接安装`.whl`文件比让`CONDA`在网上现找来得快得多。

在网上手动下载下来`.whl`之后直接用`conda install`就行了, 这里附上一个可以免费下载`.whl`的网址:

https://www.lfd.uci.edu/~gohlke/pythonlibs/

没错, 是`UCI`组织公开的一个资源库。
