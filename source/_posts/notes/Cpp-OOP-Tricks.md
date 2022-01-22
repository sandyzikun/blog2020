---
title: 一份代码带你了解C++面向对象中的神奇操作
date: 2019-04-25 12:40:00
tags:
- Notes(代码笔记)
mathjax: true
---

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
```

一份代码带你了解`C++`面向对象中的神奇操作。

## I. 构造函数中的列表形式初始化

我们先定义一个`OIer`类来看看如何初始化一个类对象, 一个初学面向对象的朋友一般会这么做:

```cpp
class OIer {
private:
    bool gender;    // 1 for Female and 0 for Male
    int age;
    char region[16];
    char lang[8];
public:
    void setOIer(bool _gender, int _age, char _region[], char _lang[]) {
        gender = _gender;
        age = _age;
        strcpy(region, _region);
        strcpy(lang, _lang);
        return;
    }
};
```

事实上`C++`设计了一种**专门用于初始化和销毁类对象的机制——构造函数和析构函数**, 每一个新建的类对象用`类名`作为构造函数, 用`~类名`作为析构函数, 而且构造函数和析构函数的参数也可以赋初值, 于是上面的代码就可以改写如下:

```cpp
class OIer {
private:
    /* ...... */;
public:
    OIer(bool _gender, int _age, char _region[], char _lang[]) {
        gender = _gender;
        age = _age;
        strcpy(region, _region);
        strcpy(lang, _lang);
        return;
    }
};
```

而且可以使用`构造函数() : 类成员(初始化值), 类成员(初始化值)`的形式来初始化各项成员:

```cpp
class OIer {
private:
    /* ...... */;
public:
    OIer(bool _gender, int _age, char _region[], char _lang[]) : gender(_gender), age(_age), region(_region), lang(_lang) {}
};
```

## II. 成员常量&常成员函数

成员常量和我们熟知常量大同小异, 都是用`const`进行修饰的, **但是必须在构造函数中赋初值**:

```cpp
class OIer {
private:
    /* ...... */;
    const int beginYear;    // 这个OIer入坑入队的时间
public:
    OIer(bool _gender, int _age, char _region[], char _lang[], int _begin = 2015) : gender(_gender), age(_age), region(_region), lang(_lang), beginYear(_begin) {}
};
```

常成员函数也用`const`进行修饰, **它不能改变成员的值, 而且很鬼畜的是它的形式为**:

    函数类型 函数名称() const {}

现在添加一个常成员函数:

```cpp
class OIer {
private:
    /* ...... */;
public:
    OIer(/* ...... */) { /* ...... */ }
    int timeExperience() const {
        return 2018 - beginYear;    // 例如今年是2018年
    }
};
```

## III. 虚拟函数, 尤其是虚·析构函数

虚拟函数的意义在于**由该类派生出来的子类不会覆盖虚拟函数**, 这一点主要用在虚·析构函数上:

```cpp
class OIer {
private:
    /* ...... */;
public:
    /* ...... */;
    virtual ~OIer() { printf("This OIer Has Gone...\n"); }
};

class ACMer : public OIer {
public:
    ~ACMer() { printf("This ACMer Has Gone...\n"); }
}
```

比如我们新建一个`ACMer`的实例:

```cpp
ACMer ptx(true, 16, "ShanDong", "cpp", 2017);
```

这样在程序结束时会有如下输出:

    This OIer Has Gone...
    This ACMer Has Gone...

否则只会调用它本身的析构函数, 也就是只会输出第二行的文字:

    This ACMer Has Gone...

如果使用纯·虚·析构函数, 则该基类便会成为一个抽象类, 这样一来**即使子类没有它自己的析构函数编译器也可以给它提供一个默认析构函数**:

```cpp
class OIer {
private:
    /* ...... */;
public:
    /* ...... */;
    virtual ~OIer() = 0;    // 纯·虚·析构函数在类内声明并"赋值为0", 且在类外定义
};

virtual OIer::~OIer() {
    printf("This OIer Has Gone...\n");
}
```
