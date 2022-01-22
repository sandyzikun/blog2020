---
title: DynamicProgramming
date: 2021-05-09 15:28:22
tags:
- Notes(代码笔记)
mathjax: true
---

稍微写一点 `dp (Dynamic Programming, 动态规划)` 相关的...

说实话，从接触dp的高一上学期，一直到现在写关于dp的大一下学期，这四年从来都没有 真⭐正⭐理⭐解 dp，所以下面只是说一个能做出来dp基础题目的人是如何把那些题目水过去的。

先说说dp的几种基础问题类型：

1. 最长增减子序贯
   * LIS: Longest Increasing Subsequence, 最长上升子序贯
   * LDS: Longest Decreasing Subsequence, 最长下降子序贯

2. 数字三角形 `(USACO1.5)` `(IOI1994)` [`(P1216)`](https://www.luogu.com.cn/problem/P1216)

3. LCS: Longest Common Subsequence, 最长公共子序贯 [`(P1439)`](https://www.luogu.com.cn/problem/P1439)

4. MSA: Maximum SubArray, 最大子段和 [`(LC0053)`](https://leetcode-cn.com/problems/maximum-subarray/)

5. 打家劫舍系列
   * 打家劫舍 [`(LC0198)`](https://leetcode-cn.com/problems/house-robber/)
   * 按摩师 [`(LC面试17-16)`](https://leetcode-cn.com/problems/the-masseuse-lcci/)
   * 打家劫舍 II [`(LC0213)`](https://leetcode-cn.com/problems/house-robber-ii/)
   * 打家劫舍 III [`(LC0337)`](https://leetcode-cn.com/problems/house-robber-iii/)

## LDS

## 数字三角形

> 观察下面的数字金字塔。
>
> 写一个程序来查找从最高点到底部任意处结束的路径，使路径经过数字的和最大。每一步可以走到左下方的点也可以到达右下方的点。
>
>                    [7]
>                   /
>                [3]      8 
>               /
>            [8]      1       0 
>               \
>         2      [7]      4       4 
>               /
>     4      [5]      2       6       5 
>
> 在上面的样例中，从 $7 \rightarrow 3 \rightarrow 8 \rightarrow 7 \rightarrow 5$ 的路径产生了最大。

### Other Info

#### Input Format

第一个行一个正整数 $r$ ，表示行的数目。

后面每行为这个数字金字塔特定行包含的整数。

#### Output Format

单独的一行，包含那个可能得到的最大的和。

#### IO Example

    In [1]:
    5
    7
    3 8
    8 1 0
    2 7 4 4
    4 5 2 6 5
    Out[1]:
    30

#### Tips

「数据范围：对于 $100\%$ 的数据， $1 \le r \le 1000$ ，所有输入在 $[0, 100]$ 范围内。

题目翻译来自 NOCOW / USACO Training Section 1.5 / IOI1994 Day1T1

### Script

```py
#!/usr/bin/env Python
# -*- coding: utf-8 -*-

import numpy as np

def dp_recursion(k, l):
    return (max(dp_recursion(k + 1, l), dp_recursion(k + 1, l + 1)) + arr[k, l]) if k < r else 0

if __name__ == "__main__":
    r = int(input())
    arr = np.zeros((r, r))
    for k in range(r):
        arr[ k , : (k + 1) ] += [ int(each) for each in input().split() ]
    print(int(dp_recursion(0, 0)))
```
