---
title: GIT学习笔记
date: 2019-03-14 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

## I. 初次使用之前进行的准备

这些都是为了便于确认你的身份

```sh
> git config --global user.email "you@example.com"          #你的邮箱地址
> git config --global user.name "Your Name"                 #你的名字
```

## II. 克隆一个仓库

```sh
> git clone "https://github.com/username/repository.git"    #你的仓库地址
```

## III. 确认并提交一个仓库中的改动

```sh
> git add --all                                             # --all 添加所有改动
> git commit -m "Commit Message"                            #确认提交改动时的备注和提交信息
> git push -u origin master                                 # origin 原始仓库, master 默认分支
```
