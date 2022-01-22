---
title: VB入门
date: 2019-05-02 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

# [Visual Basic](https://baike.baidu.com/item/Visual%20Basic/287852) 入门教程

没错这是VB的入门教程

## 四个基本控件

| 控件 | 类名 |
|-|-|
| 窗体 | `Form` |
| 命令按钮 | `CommandButton` |
| 标签 | `Label` |
| 文本框 | `TextBox` |

## 控件的四大属性

| 属性 | 成员名称 | 作用 |
|-|-|-|
| 名称 | `Name` | 相当于变量名 |
| 显示内容 | `Caption` | 在控件中显示的文字内容 |
| 高度 | `Height` | 控件的纵向尺寸 |
| 宽度 | `Width` | 控件的横向尺寸 |

## 常量变量定义

### 定义常量

```vb
Const 常量名 = 常量值
Const NUM_CONSTANT = 1926.0817
```

### 定义变量

```vb
Dim 变量名 As 变量类型 = 初始值
Dim var1 As Integer = 1024
```

### 变量类型

也就这么几种

| 变量类型 | 名称 |
|-|-|
| 整数 | `Integer` |
| 字符 | `Char` |
| 长整数 | `Long` |
| 单精度 | `Single` |
| 双精度 | `Double` |
| 字符串 | `String` |
| 二值布尔 | `Boolean`(可以为`True`或者`False`) |
| 日期 | `Date` |

## 运算符和函数

* 算术运算符
  * 加法 `+`
  * 减法 `-`
  * 乘法 `*`
  * 除法 `/`
    * 整除 `\`
  * 取模 `Mod`
  * 乘方 `^`

* 关系运算符
  * 相等 `=`(对就是很麻烦, 和赋值是一个符号)
  * 不等 `<>`(一种被批评的写法)
  * 小于 `<`
  * 大于 `>`
  * 小于等于 `<=`
  * 大于等于 `>=`

* 逻辑运算符
  * 与 `And`
    * 与(短路式快速求值) `AndAlso`
  * 或 `Or`
    * 或(短路式快速求值) `OrElse`
  * 非 `Not`
  * 异或 `Xor`
  * 为真 `IsTrue`
  * 为假 `IsFalse`

## 条件控制

* `If`条件控制

```vb
If 条件1 Then
    语句1
ElseIf 条件2 '这里不用加Then
    语句2
ElseIf 条件3
    语句3
Else
    其他语句
End If '结束选择结构
```

* `Select`条件控制

```vb
Select 标准
    Case 条件1
        语句1
    Case 条件2
        语句2
    Case 条件3
        语句3
    Case Else
        其他语句
End Select '结束选择结构
```

## 循环控制

* `For`循环

```vb
For 变量名 As 变量类型 = 初始值 To 终值 Step 步长
    循环语句
End For
```

到此为止你们会考要用到的应该都够用了, 更多的请见 https://blog.csdn.net/u011054333/article/details/78984118/
