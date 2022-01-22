---
title: 阿里云编码规范
date: 2019-04-18 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

前两天看了阿里巴巴写的《阿里巴巴Java开发手册》, 个人再次认为统一一个`Code Style`的规范真的很重要, 从以下网站:

* https://www.jianshu.com/p/0d296596a74c/
* https://yq.aliyun.com/download/2719/
* https://baike.baidu.com/item/阿里巴巴Java开发手册/22264188

获得资源之后, 在这里稍微讲讲编码的规范问题。事实上, 这个规范并不是只有`Java`才需要的, **无论是什么语言, 编码规范将会直接影响到你的开发效率!**

## O. `Code Style`的三大基本问题

1. 前后大括号是否换行
   **\[强制\]** 代码块的前大括号不换行, 后大括号需要换行。

2. 缩进使用`Space`还是`Tab`
   **\[强制\]** 所有缩进一律使用`Space*4`, 禁止~~`Space*2`~~或长度不定的~~`Tab`~~。

3. 单句流程控制语句是否使用大括号
   **\[强制\]** 单句流程控制语句使用大括号。

示例(以`C/C++`为例):

```cpp
#include <stdio.h>

int a = 0, b = 0;

int main(int argc, char const *argv[]) {
    scanf("%d %d", &a, &b);
    printf("%d", a + b);
    if (a + b == 0) {
        printf("Sharing the World!\n");
    }
    return 0;
}
```
